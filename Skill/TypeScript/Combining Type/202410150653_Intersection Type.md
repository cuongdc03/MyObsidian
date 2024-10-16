
| id                             | hubs           | source                                                                                |
| ------------------------------ | -------------- | ------------------------------------------------------------------------------------- |
| 202410150653_Intersection Type | [[TypeScript]] | https://www.typescripttutorial.net/typescript-tutorial/typescript-intersection-types/ |
An intersection type creates a new type by combining multiple existing types. The new type has all features of the existing types.
To combine types, you use the `&` operator as follows:
```ts
type A&B = typeA & typeB
```
The `typeAB` will have all properties from both `typeA` and `typeB`.
# Example
Suppose that you have three interfaces: `BusinessPartner`, `Identity`, and `Contact`.
```ts
interface BusinessPartner { name: string; credit: number; }
interface Identity { id: number; name: string; }
interface Contact { email: string; phone: string; }

type Employee = Identity & Contact;
type Customer = BusinessPartner & Contact;
```