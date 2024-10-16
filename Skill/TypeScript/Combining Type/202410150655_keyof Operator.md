
| id                          | hubs           | source                                                                           |
| --------------------------- | -------------- | -------------------------------------------------------------------------------- |
| 202410150655_keyof Operator | [[TypeScript]] | https://www.typescriptlang.org/docs/handbook/2/keyof-types.html#handbook-content |
The `keyof` operator takes an object type and produces a string or numeric literal union of its keys. The following type `P` is the same type as `type P = "x" | "y"`
```ts
type Point = { x: number; y: number };
type P = keyof Point; //x,y
```