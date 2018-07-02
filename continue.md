# \G

E.G: [line_start 1 abc 2 def 4](https://stackoverflow.com/questions/51127479/regex-match-all-possibilities)
```
(?:\G(?!^)|^line_start)\D*\K\d+
```
Yields 3 matches: 1, 2, 4
