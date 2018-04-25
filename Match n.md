
String length

`^.{1,35}$`


No identical consecutive characters

`^(([\w])(?!\2))+$`

No more than two identical consecutive characters, etc

`^(([\w])\2?(?!\2))+$`
