
| id                          | hubs                            | source                                                                                  |
| --------------------------- | ------------------------------- | --------------------------------------------------------------------------------------- |
| 202410082240_Arrow Function | [[hubs/JavaScript\|JavaScript]] | https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#arrow_functions |
An Arrow Function has shorter syntax comparered to function expressions and doesn't have its own [`this`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this), [`arguments`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments), [`super`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/super), or [`new.target`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new.target). Arrow functions are always anonymous.
Two factors influenced the introduction of arrow functions: _shorter functions_ and _non-binding_ of `this`.
# Shorter Function
In some functional patterns, shorter functions are welcome. Compare:
```
const a = ["Hydrogen", "Helium", "Lithium", "Beryllium"];

const a2 = a.map(function (s) {
  return s.length;
});

console.log(a2); // [8, 6, 7, 9]

const a3 = a.map((s) => s.length);

console.log(a3); // [8, 6, 7, 9]
```
