

## Comma-separated values, semi-colon when not surrounded by single or double quotes

```
[^,"']+|"([^"]*)"|'([^']*)'
[^,"']+|"([^"]*)"|'([^']*)'
```

..

## Tab-separated values when not surrounded by single or double quotes

```
[^\t"']+|"([^"]*)"|'([^']*)'

[^\s"']+|"([^"]*)"|'([^']*)'
```
