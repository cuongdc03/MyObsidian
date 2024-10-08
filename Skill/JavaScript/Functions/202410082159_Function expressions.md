
| id                                | hubs                            | source                                                                                       |
| --------------------------------- | ------------------------------- | -------------------------------------------------------------------------------------------- |
| 202410082159_Function expressions | [[hubs/JavaScript\|JavaScript]] | https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#function_expressions |
While the function declaration above is syntactically a statement, functions can also be created by a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function).
Such a function can be **anonymous**; it does not have to have a name. For example, the function `square` could have been defined as:
```
const square = function (number) {
  return number * number;
};

console.log(square(4)); // 16
```
However, a name _can_ be provided with a function expression. Providing a name allows the function to refer to itself, and also makes it easier to identify the function in a debugger's stack traces:
```
const factorial = function fac(n) {
  return n < 2 ? 1 : n * fac(n - 1);
};

console.log(factorial(3)); // 6
```
In the following code, the function receives a function defined by a function expression and executes it for every element of the array received as a second argument:
```
function map(f, a) {
  const result = new Array(a.length);
  for (let i = 0; i < a.length; i++) {
    result[i] = f(a[i]);
  }
  return result;
}

const cube = function (x) {
  return x * x * x;
};

const numbers = [0, 1, 2, 5, 10];
console.log(map(cube, numbers)); // [0, 1, 8, 125, 1000]

```
