Variables are declared with the `var` keyword. JavaScript is dynamically typed, so you don't need to specify type. Assignment uses a single `=`
```
var someVar = 5;
```
If you leave the var keyword off, you won't get an error
```
someOtherVar = 10;
```
but your variable will be created in the global scope, not in the scope you defined it in

Variables declared without being assigned to are set to undefined
```
var someThirdVar;
```
If you want to declare a couple of variables, then you could use a comma separator 
```
var someFourthVar=2, someFifthVar=4;
```
There's shorten syntax to perform math operations
```
someVar += 5; //someVar is 10 now
someVar *= 10; //someVar is 100
someVar++; //someVars 101 now
someVar--; //back to 100
```