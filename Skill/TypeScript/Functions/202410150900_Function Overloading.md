
| id                                | hubs           | source                                                                           |
| --------------------------------- | -------------- | -------------------------------------------------------------------------------- |
| 202410150900_Function Overloading | [[TypeScript]] | https://www.typescriptlang.org/docs/handbook/2/functions.html#function-overloads |
Some JavaScript functions can be called in a variety of argument counts and types. For example, you might write a function to produce a `Date` that takes either a timestamp (one argument) or a month/day/year specification (three arguments).
```ts
function makeDate(timestamp: number): Date;

function makeDate(m: number, d: number, y: number): Date;

function makeDate(mOrTimestamp: number, d?: number, y?: number): Date {

if (d !== undefined && y !== undefined) {

return new Date(y, mOrTimestamp, d);

} else {

return new Date(mOrTimestamp);

}

}

const d1 = makeDate(12345678);

const d2 = makeDate(5, 5, 5);

const d3 = makeDate(1, 3);//error because required 3 parameter
```