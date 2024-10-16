
| id                             | hubs           | source                                                                                 |
| ------------------------------ | -------------- | -------------------------------------------------------------------------------------- |
| 202410151054_Conditional Types | [[TypeScript]] | https://www.typescriptlang.org/docs/handbook/2/conditional-types.html#handbook-content |
_Conditional types_ help describe the relation between the types of inputs and outputs.
```ts
interface Animal {

live(): void;

}

interface Dog extends Animal {

woof(): void;

}

type Example1 = Dog extends Animal ? number : string;

//type Example1 = number

type Example2 = RegExp extends Animal ? number : string;

//type Example2 = string
```
Conditional types take a form that looks a little like conditional expressions (`condition ? trueExpression : falseExpression`) in JavaScript:
```ts
Conditional types take a form that looks a little like conditional expressions (`condition ? trueExpression : falseExpression`) in JavaScript:

`   `
```
`   `