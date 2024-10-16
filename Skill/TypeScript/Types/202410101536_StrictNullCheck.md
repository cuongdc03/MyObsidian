
| id                           | hubs           | source                                                                                  |
| ---------------------------- | -------------- | --------------------------------------------------------------------------------------- |
| 202410101536_StrictNullCheck | [[TypeScript]] | https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#strictnullchecks-off |
## StrickNullCheck off
With [[202410101536_StrictNullCheck||StrictNullCheck]] off, values that might be null of undefined can be acesses normally means that value [[202410101534_null and undefined||null and undefined]] can be assign to a property of any type.
## StrickNullCheck on 
With [`strictNullChecks`](https://www.typescriptlang.org/tsconfig#strictNullChecks) _on_, when a value is `null` or `undefined`, you will need to test for those values before using methods or properties on that value. Just like checking for `undefined` before using an optional property, we can use _narrowing_ to check for values that might be `null`:
```ts
function doSomething(x: string | null) {

if (x === null) {

// do nothing

} else {

console.log("Hello, " + x.toUpperCase());

}


```
boor sung