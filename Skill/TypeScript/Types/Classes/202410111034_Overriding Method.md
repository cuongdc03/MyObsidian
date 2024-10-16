
| id                             | hubs           | source                                                                         |
| ------------------------------ | -------------- | ------------------------------------------------------------------------------ |
| 202410111034_Overriding Method | [[TypeScript]] | https://www.typescriptlang.org/docs/handbook/2/classes.html#overriding-methods |
A derived class can also override a base class field or property. You can use the `super.` syntax to access base class methods. Note that because JavaScript classes are a simple lookup object, there is no notion of a “super field”.
```ts
class Base {

greet() {

console.log("Hello, world!");

}

}

class Derived extends Base {
greet(name?: string) {
if (name === undefined) {
super.greet();
} else {
console.log(`Hello, ${name.toUpperCase()}`);
		}
}
}

const d = new Derived();

d.greet();//Hello World

d.greet("reader");//Hello, NAME
```
It’s important that a derived class follow its base class contract. Remember that it’s very common (and always legal!) to refer to a derived class instance through a base class reference:
```ts
const b: Base = d;

// No problem
b.greet();
// 
b.greet("reader")
```