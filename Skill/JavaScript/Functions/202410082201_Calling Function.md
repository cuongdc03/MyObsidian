
| id                            | hubs                            | source                                                                                    |
| ----------------------------- | ------------------------------- | ----------------------------------------------------------------------------------------- |
| 202410082201_Calling Function | [[hubs/JavaScript\|JavaScript]] | https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#calling_functions |

A function can call itself. For example, here is a function that computes factorials recursively:
```
function factorial(n) {
  if (n === 0 || n === 1) {
    return 1;
  } else {
    return n * factorial(n - 1);
  }
}
```
