# .NET Balancing Groups

## Matchinb nested balanced parenthesis

... still not a parser

```
(?=(\((?:(?<open>\()*[^()]+(?<-open>\))*)+\)(?(open)(?!))))
```

That isn't optimal since it "reparses" some nested gropups of parenthesis for every match.  
Using a real parser would read/parse the string only once, and would be therefore more efficient.

```
using System;
using System.Text.RegularExpressions;
public class Example
{
   public static void Main()
   {
      var re = @"(?x)  # ignore spaces and comments
(?=                    # lookahead (zero width)
  (
    \(                 # first (
    (?:
      (?<open> \( )*   # open++
      [^()]+
      (?<-open> \) )*  # open--
    )+
    \)                 # last )
    (?(open)(?!))      # fail if unblanaced: open > 0
  )
)
\(                     # eat a (, to advance the match a char";

      var str = "a + ((b + (c + d)) + (e + f)) + (x + ((y) + (z)) + x)";

      var m = Regex.Matches(str, re);

      Console.WriteLine("Matched: ");
      foreach (Match i in m)
        Console.WriteLine(i.Groups[1]);
   }
}
```

#### Backreferences To Subtracted Groups



#### [Matching Palindromes](https://www.regular-expressions.info/balancing.html)



```
^(?'letter'[a-z])+[a-z]?(?:\k'letter'(?'-letter'))+(?(letter)(?!))$
```
or more condensed

```
(?x)^(?<l>\w)+\w?
(\k<l>(?<-l>))+
(?(l)(?!))$ 
```

https://www.regular-expressions.info/refrecurse.html
