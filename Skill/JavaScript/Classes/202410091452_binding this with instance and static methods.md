
| id                                                         | hubs                            | source                                                                                                                  |
| ---------------------------------------------------------- | ------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| 202410091452_binding this with instance and static methods | [[hubs/JavaScript\|JavaScript]] | https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes#binding_this_with_instance_and_static_methods |
When a static or instance method is called without a value for [`this`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this), such as by assigning the method to a variable and then calling it, the `this` value will be `undefined` inside the method. This behavior is the same even if the [`"use strict"`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode) directive isn't present, because code within the `class` body is always executed in strict mode.
```js
class Animal {
  speak() {
    return this;
  }
  static eat() {
    return this;
  }
}

const obj = new Animal();
obj.speak(); // the Animal object
const speak = obj.speak;
speak(); // undefined

Animal.eat(); // class Animal
const eat = Animal.eat;
eat(); // undefined

```