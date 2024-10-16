
| id                                        | hubs           | source                                                      |
| ----------------------------------------- | -------------- | ----------------------------------------------------------- |
| 202410110926_strictPropertyInitialization | [[TypeScript]] | https://www.typescriptlang.org/docs/handbook/2/classes.html |
The [[202410110926_strictPropertyInitialization|| strictPropertyInitialization]] setting controls whether class need to be initialized in the constructor
![[Pasted image 20241011092920.png]]
Note: the field need to be intialize in the constructor itself. [[TypeScript]] doesn't analyze method you invoke from the constructor to detect initialization because a derived class might override those methods and fail to initialize the members.

Use `!` operator to define a field without assigning a initial variable:
```ts
class OKGreeter{
	// Not initialized, but no error
	name!: string
}
```
