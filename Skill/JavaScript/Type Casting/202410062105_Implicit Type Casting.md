
| id                                 | hubs                            | source                                                           |
| ---------------------------------- | ------------------------------- | ---------------------------------------------------------------- |
| 202410062105_Implicit Type Casting | [[hubs/JavaScript\|JavaScript]] | https://www.tutorialspoint.com/explain-typecasting-in-javascript |
The Implicit type casting is the conversion of data type done due to the internal requirement or automatic conversion by the compiler or the runtime
To understand the implicit conversion let us consider the example of the boolean values (primitive
JavaScript expects a boolean value in a conditional expression. So JavaScript will temporarily convert the value in parentheses to a boolean to evaluate the if expression −
```
val = 1;
if (val) {
	console.log('yes,val exists');
}
```
## Implicit conversion with == operator

Type conversion is also perfomed when comparing values using the equal(= = ) and not equal(!=)
```
console.log(123=='125')
```