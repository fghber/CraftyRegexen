# Parenthesis and other nested structures

## Get everything between parenthesis

```
\[(.*?)\]
```

## Get everything between C/C++ multiline comments /* */

```
\/\*[\S\s]*?\*\/
```



## Get everything between parenthesis not enclosed by double quotes

```

```

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
