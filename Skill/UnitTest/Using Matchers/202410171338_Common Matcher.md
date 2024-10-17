
| id                          | hubs          | source                                                |
| --------------------------- | ------------- | ----------------------------------------------------- |
| 202410171338_Common Matcher | [[Unit Test]] | https://jestjs.io/docs/using-matchers#common-matchers |
The Simplest way to test a value is with exact equality
```ts
test('two plus two is four', () => {
  expect(2 + 2).toBe(4);
});
```

![[Pasted image 20241017134341.png]]
`toEqual` recursively checks every field of an object or array
## You can also test for the opposite of a matcher using `not`:
```ts
test('adding positive numbers is not zero', () => {
  for (let a = 1; a < 10; a++) {
    for (let b = 1; b < 10; b++) {
      expect(a + b).not.toBe(0);
    }
  }
});
```