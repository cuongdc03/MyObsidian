
| id                             | hubs                            | source                                                                                |
| ------------------------------ | ------------------------------- | ------------------------------------------------------------------------------------- |
| 202410091450_Inheritance_Class | [[hubs/JavaScript\|JavaScript]] | https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes#inheritance |
The [`extends`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/extends) keyword is used in _class declarations_ or _class expressions_ to create a class as a child of another constructor (either a class or a function).
```js
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(`${this.name} makes a noise.`);
  }
}

class Dog extends Animal {
  constructor(name) {
    super(name); // call the super class constructor and pass in the name parameter
  }

  speak() {
    console.log(`${this.name} barks.`);
  }
}

const d = new Dog("Mitzie");
d.speak(); // Mitzie barks.

```