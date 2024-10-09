
| id                      | hubs           | source                                                       |
| ----------------------- | -------------- | ------------------------------------------------------------ |
| 202410091606_Interfaces | [[TypeScript]] | https://www.typescriptlang.org/docs/handbook/interfaces.html |
There are a few key differences between interfaces and type aliases:
- interfaces can "merge" together to be augmented - feature particularly useful when working with 3rd party code such as build-in globals pr npm packages
- interfaces can be used to type check the structure of class declaration while type aliases cannot
- Interface are generally speedier for the [[TypeScript]] checker to work with
- Because interace are considered named objects rather than an alias for an unnamed object literal, their error messages are more likely to be readable in hard edge cases
For the latter two reasons and to maintain consistency, the rest of this book and its associated projects default to using interfaces over aliased object shapes. I generally recommend using interfaces whenever possible (i.e., until you need features such as
union types from type aliases).