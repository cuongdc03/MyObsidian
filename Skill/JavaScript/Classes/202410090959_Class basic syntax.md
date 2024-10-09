
| id                              | hubs                            | source                        |
| ------------------------------- | ------------------------------- | ----------------------------- |
| 202410090959_Class basic syntax | [[hubs/JavaScript\|JavaScript]] | https://javascript.info/class |
In practice, we often need to create many objects of the same kind, like users, or goods or whatever.

As we already know from the chapter [Constructor, operator "new"](https://javascript.info/constructor-new), `new function` can help with that.

But in the modern JavaScript, there’s a more advanced “class” construct, that introduces great new features which are useful for object-oriented programming.
# The "class" syntax
```javascript
class MyClass{
//class methods
constructor(){...}
method1(){...}
method2(){...}
method3(){...}
}
```
## There are 3 way to Define a class
```js
// Declaration Much prefer
class Rectangle {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
}

// Expression; the class is anonymous but assigned to a variable
const Rectangle = class {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
};

// Expression; the class has its own name
const Rectangle = class Rectangle2 {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
};

```
## Class body
The body of a class is the part that is in curly braces `{}`. This is where you define class members, such as methods or constructor.
The body of a class can be executed in [[202410082304_Strict Mode||Strict Mode]] even without [[202410082304_Strict Mode||Strict Mode] ] 
A class element can be characterized by three aspects:

- Kind: Getter, setter, method, or field
- Location: Static or instance
- Visibility: Public or private
## Method 
Methods are defined on the prototype of each class instance and are shared by all instances. Methods can be plain functions, async functions, generator functions, or async generator functions. For more information, see [method definitions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Method_definitions).
```js
class Rectangle {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
  // Getter
  get area() {
    return this.calcArea();
  }
  // Method
  calcArea() {
    return this.height * this.width;
  }
  *getSides() {
    yield this.height;
    yield this.width;
    yield this.height;
    yield this.width;
  }
}

const square = new Rectangle(10, 10);

console.log(square.area); // 100
console.log([...square.getSides()]); // [10, 10, 10, 10]

```
