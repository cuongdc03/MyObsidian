
| id                          | hubs           | source                                                                     |
| --------------------------- | -------------- | -------------------------------------------------------------------------- |
| 202410111001_Class Heritage | [[TypeScript]] | https://www.typescriptlang.org/docs/handbook/2/classes.html#class-heritage |
Like other languages with object-oriented features, classes in [[hubs/JavaScript|JavaScript]] can inherit from base classes
# Implements Clauses
You can use an `implement` clause to check that a class satisfies a particular `interface`. An error will be issued if a class fails to correctly implement it:
![[Pasted image 20241011100603.png]]
Classes may also implement multiple interfaces, Example:
```ts
interface Pingable {

ping(): void;
}
interface Sonar {
sonar(): void;
}

class Duck implements Pingable, Sonar {

ping() {

console.log('Duck: ping');

}

sonar() {

console.log('Duck: sonar');

}

}
const a = new Duck();
a.ping(); // Duck: ping
a.sonar(); // Duck: sonar
```
Note: [[202410111019_Implement_Cautions]]