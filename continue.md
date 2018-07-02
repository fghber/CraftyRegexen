# \G

E.G: line_start 1 abc 2 def 4
```
(?:\G(?!^)|^line_start)\D*\K\d+
```
Yields 3 matches: 1, 2, 4
