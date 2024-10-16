
| id                                 | hubs           | source                               |
| ---------------------------------- | -------------- | ------------------------------------ |
| 202410111119_Static Field Modifier | [[TypeScript]] | [[learning_typescript.pdf#page=148]] |
TypeScript supports using the static keyword on its own
and/or with readonly and/or with one of the visibility keywords. When combined, the visibility keyword comes first, then static, then readonly.
```ts
class Circle {

static readonly pi = 3.14;
static calculateArea(radius: number) {
return this.pi * radius * radius;
}
calculateCircumference(radius: number): number {
return 2 * Circle.pi * radius;
}
}
console.log(Circle.calculateArea(5)); // returns 78.5
let circleObj = new Circle();

console.log(circleObj.calculateCircumference(5)); // returns 31.4000000

console.log(circleObj.calculateArea(5)); // Error: <-- cannot call this
```
As you can see, the static field `pi` can be accessed in the static method using `this.pi` and in the non-static (instance) method using `Circle.pi`.