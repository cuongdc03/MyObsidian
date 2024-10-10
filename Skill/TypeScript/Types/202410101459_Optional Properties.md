
| id                               | hubs                            | source                                                                                 |
| -------------------------------- | ------------------------------- | -------------------------------------------------------------------------------------- |
| 202410101459_Optional Properties | [[hubs/JavaScript\|JavaScript]] | https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#optional-properties |
```ts
function printName(obj: { first: string; last?: string }) {

console.log (obj.first + " " +obj.last)

}


printName({ first: "Bob" }); //obj.last => undefined

printName({ first: "Alice", last: "Alisson" });
```

If use Optional Properties must have a logic checker to avoid some undefined case
==> 
```ts
function printName(obj: { first: string; last?: string }) {

console.log(obj.first+ " " + (obj.last? obj.last:""))

}

// Both OK

printName({ first: "Bob" });

printName({ first: "Alice", last: "Alisson" });
```