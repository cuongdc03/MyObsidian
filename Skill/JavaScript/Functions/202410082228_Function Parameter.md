
| id                              | hubs                            | source                                                                                      |
| ------------------------------- | ------------------------------- | ------------------------------------------------------------------------------------------- |
| 202410082228_Function Parameter | [[hubs/JavaScript\|JavaScript]] | https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#function_parameters |
There are 2 kind of parameter syntax: default parameter and rest parameters.
# Default Parameter
In JavaScript, parameters of functions default to `undefined`. However, in some situations it might be useful to set a different default value. This is exactly what default parameters do.

In the past, the general strategy for setting defaults was to test parameter values in the body of the function and assign a value if they are `undefined`.

In the following example, if no value is provided for `b`, its value would be `undefined` when evaluating `a*b`, and a call to `multiply` would normally have returned `NaN`. However, this is prevented by the second line in this example:
```
function multiply(a, b) {
  b = typeof b !== "undefined" ? b : 1;
  return a * b;
}

console.log(multiply(5)); // 5

```
With _default parameters_, a manual check in the function body is no longer necessary. You can put `1` as the default value for `b` in the function head:
```
function multiply(a, b = 1) {
  return a * b;
}

console.log(multiply(5)); // 5

```
# Rest Parameter
The [rest parameter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest_parameters) syntax allows us to represent an indefinite number of arguments as an array.
In the following example, the function `multiply` uses _rest parameters_ to collect arguments from the second one to the end. The function then multiplies these by the first argument.
```
function multiply(multiplier, ...theArgs) {
  return theArgs.map((x) => multiplier * x);
}

const arr = multiply(2, 1, 2, 3);
console.log(arr); // [2, 4, 6]
```
