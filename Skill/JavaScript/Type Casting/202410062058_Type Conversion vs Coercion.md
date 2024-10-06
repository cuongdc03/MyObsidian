
| id                                       | hubs                            | source                                                            |
| ---------------------------------------- | ------------------------------- | ----------------------------------------------------------------- |
| 202410062058_Type Conversion vs Coersion | [[hubs/JavaScript\|JavaScript]] | https://developer.mozilla.org/en-US/docs/Glossary/Type_Conversion |
Type conversion means that transfer of  data from one datatype to another.Implicit conversion happens when the compiler or runtime automatically covers data types

Type coercion is the automatic or implicit coversion of values from one data type to another. Type conversion is similar to type coercion beacauce they both covert values from one data to another with one key difference - type coercion is implicit whereas type conversion can be either implicit or explicit

Examples:
```
const value1 = "5";
const value2 = 9;
let sum = value1 + value2;

console.log(sum);

```
The compiler could have coerced the `5` into a number and returned a sum of `14`, but it did not. To return this result, you'd have to explicitly convert the `5` to a number using the [`Number()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) method:
```
sum = Number(value1) + value2;
```