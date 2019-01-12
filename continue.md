# `\G`

E.G: [line_start 1 abc 2 def 4](https://stackoverflow.com/questions/51127479/regex-match-all-possibilities)
```
(?:\G(?!^)|^line_start)\D*\K\d+
```
Yields 3 matches: 1, 2, 4

Another example of the same type: https://stackoverflow.com/questions/4572697/continuing-at-the-end-of-the-previous-match-in-regex-pcre
```
Pig, Cow, Goat
fruit: apple, orange, peach, pear
vegetable: Carrot, Lettuce, Cellery
```

```
(?:fruit:\s*|(?<!^)\G,\s*)(\w+)
```

Yields all fruits after the preamble `fruit:` as individual match.

[Contiguous Matches: `\G` in .NET](https://docs.microsoft.com/en-us/dotnet/standard/base-types/anchors-in-regular-expressions#Contiguous)
which shows a kind of useless example since the .NET Regex engine is able to match repeated capture groups also without `\G`.
