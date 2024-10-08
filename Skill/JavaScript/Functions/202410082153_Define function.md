
| id                           | hubs                            | source                                                                                     |
| ---------------------------- | ------------------------------- | ------------------------------------------------------------------------------------------ |
| 202410082153_Define function | [[hubs/JavaScript\|JavaScript]] | https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#defining_functions |
# Function Declarations
A **function definition** (also called a **function declaration**, or **function statement**) consists of the [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function) keyword, followed by:

- The name of the function.
- A list of parameters to the function, enclosed in parentheses and separated by commas.
- The JavaScript statements that define the function, enclosed in curly braces, `{ /* … */ }`
# Example
```
function square(number){
	return number * number;
}
```
```
function myFunc(theArr) {
  theArr[0] = 30;
}

const arr = [45];

console.log(arr[0]); // 45
myFunc(arr);
console.log(arr[0]); // 30
```
