
| id                                      | hubs                            | source                                                                                             |
| --------------------------------------- | ------------------------------- | -------------------------------------------------------------------------------------------------- |
| 202410082209_Using the arguments object | [[hubs/JavaScript\|JavaScript]] | https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#using_the_arguments_object |
The arguments of a function are maintained in an array-like object. Within a function, you can address the arguments passed to it as follows:
```
arguments[i]
```
# Example
```
function myConcat(separator) {
  let result = ""; // initialize list
  // iterate through arguments
  for (let i = 1; i < arguments.length; i++) {
    result += arguments[i] + separator;
  }
  return result;
}
console.log(myConcat(", ", "red", "orange", "blue"));
// "red, orange, blue, "

console.log(myConcat("; ", "elephant", "giraffe", "lion", "cheetah"));
// "elephant; giraffe; lion; cheetah; "

console.log(myConcat(". ", "sage", "basil", "oregano", "pepper", "parsley"));
// "sage. basil. oregano. pepper. parsley. "

```