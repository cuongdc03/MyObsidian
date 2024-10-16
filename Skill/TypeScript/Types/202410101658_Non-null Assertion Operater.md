
| id                                        | hubs           | source                                                                                                  |
| ----------------------------------------- | -------------- | ------------------------------------------------------------------------------------------------------- |
| 202410101658_Non-null Assertion Operatoer | [[TypeScript]] | https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#non-null-assertion-operator-postfix- |
TypeScript also has a special syntax for removing `null` and `undefined` from a type without doing any explicit checking. Writing `!` after any expression is effectively a type assertion that the value isn’t `null` or `undefined`:

```ts
function liveDangerously(x?: number | null) {

// No error

console.log(x!.toFixed());// 

}
```