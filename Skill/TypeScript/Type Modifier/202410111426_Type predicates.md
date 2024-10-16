
| id                          | hubs           | source                               |
| --------------------------- | -------------- | ------------------------------------ |
| 202410111426_Tye predicates | [[TypeScript]] | [[learning_typescript.pdf#page=153]] |
![[Pasted image 20241011142738.png]]
TS has special syntax for functions that return a boolean meant to indicate whether an argument is a particular type.this is referred to as a type predicate, also sometimes called a "user-defined type guard"
Type predicate’s return types can be declared as the name of a parameter, the is
keyword, and some type:
```ts
function typePredicate(input: WideType): input is NarrowType;
```
