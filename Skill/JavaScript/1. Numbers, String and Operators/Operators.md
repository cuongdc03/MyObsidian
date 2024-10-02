Negation uses the ! symbol
```
!true //false
!false //true
```
Equality is ===
```
1 === 1 //true 
2 === 1 //false
```
More Comparisons
```
1 < 10; // = true
1 > 10; // = false
2 <= 2; // = true
2 >= 2; // = true
```
String can be concatenated with + 
```
"Hello " + "world!"; // = "Hello world!"
```
Some Strange case 
```
"1, 2, " + 3; // = "1, 2, 3"
"Hello " + ["world", "!"]; // = "Hello world,!"
13 + !0; // 14
"13" + !0; // '13true'
```
Type coercion is performed for comparisons with double equals...
```
"5" == 5; // = true
null == undefined; // = true
```
Unless you use 
```
"5" === 5; // = false
null === undefined; // = false
```
