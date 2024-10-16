
| id                          | hubs           | source                                                                      |
| --------------------------- | -------------- | --------------------------------------------------------------------------- |
| 202410111032_extends Clause | [[TypeScript]] | https://www.typescriptlang.org/docs/handbook/2/classes.html#extends-clauses |
Classes may `extend` from a base class. A derived class has all the properties and methods of its base class, and can also define additional members.
```ts
class Animal {
move() {
console.log("Moving along!");
}
}

class Dog extends Animal {
woof(times: number) {
for (let i = 0; i < times; i++) {
console.log("woof!");
}
}
}
const d = new Dog();
// Base class method

d.move();

// Derived class method

d.woof(3);
```