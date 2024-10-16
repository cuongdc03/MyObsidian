
| id                            | hubs           | source                               |
| ----------------------------- | -------------- | ------------------------------------ |
| 202410111054_Abstract Classes | [[TypeScript]] | [[learning_typescript.pdf#page=119]] |
Create a base class that doesn't itself declare the implementation of some methods, nut instead expects a subclass to provide them
## Example
```ts
abstract class School {
	readonly name: string;
	constructor(name: string) {
		this.name = name;
	}
	abstract getStudentTypes(): string[];
}
class Preschool extends School {
	getStudentTypes() {
		return ["preschooler"];
	}
}
class Absence extends School { }//Error
```