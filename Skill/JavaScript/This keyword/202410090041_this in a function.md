
| id                              | hubs                            | source                                   |
| ------------------------------- | ------------------------------- | ---------------------------------------- |
| 202410090041_this in a function | [[hubs/JavaScript\|JavaScript]] | https://www.w3schools.com/js/js_this.asp |
In a function, the **global object** is the default binding for `this`.

In a browser window the global object is `[object Window]`:
Example 
```
function myFunction() {  
  return this;  
}
```
JavaScript **strict mode** does not allow default binding.

So, when used in a function, in strict mode, `this` is `undefined`.
```
"use strict";  
function myFunction() {  
  return this;  //undefined
}
```