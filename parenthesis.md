# Parenthesis and other nested structures

## Get everything between parenthesis

```
\[(.*?)\]
```

## Get everything between C/C++ multiline comments /* */

```
\/\*[\S\s]*?\*\/
```

## Check that string CONTAINS a valid hierarchy of parenthesis or not

```
\(((?>[^()]+)|(?R))*\)
```

## Get everything between parenthesis not enclosed by double quotes

Drop-in pattern: just replace the first character, that acts as a separator
```
/\t(?=(?:[^\"]*\"[^\"]*\")*[^\"]*$)/gm;  
```

## Get everything between (double) quotes allowing escaped quotes

```
(["'])(?:(?=(\\?))\2.)*?\1
```

`([""'])` match a quote; `((?=(\\?))\2.)` if backslash exists, gobble it, and whether or not that happens, match a character; `*?` match many times (non-greedily, as to not eat the closing quote); `\1` match the same quote that was use for opening.  

## Matching 3 different types of balanced parentheses with .NET balancing groups

```
(
    [^(){}\[\]]+
    | \( (?=[^)]*  (?<Stack> \) ) )
    | \[ (?=[^\]]* (?<Stack> \] ) )
    | \{ (?=[^}]*  (?<Stack> \} ) )
    | \k<Stack> (?<-Stack>)
)+?
(?(Stack) (?!))
```
