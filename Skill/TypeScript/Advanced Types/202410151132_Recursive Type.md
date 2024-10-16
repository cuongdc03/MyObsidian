
| id                          | hubs           | source                                                           |
| --------------------------- | -------------- | ---------------------------------------------------------------- |
| 202410151132_Recursive Type | [[TypeScript]] | https://www.basedash.com/blog/guide-to-typescript-recursive-type |
# Basic Recursive Types
A recursive type in TypeScript is a type that references itself. Consider the classic example of a linked list:
```ts
interface LinkedList{
	value:number;
	next: LinkedList | null;
}
```
# Another Use cases
## 1.TREES
Binary trees are a common data structure where each node has a value and two child nodes (left and right):
```ts
interface BinaryTreeNode {
value: number;
left: BinaryTreeNode | null;
right: BinaryTreeNode | null; }
```
## 2. Hierarchical Structures
Consider a folder structure where each folder can have many subfolders:
```ts
interface Folder{
	name: string;
	subFolder: Folder[];
}
```
## 3.JSON-LIKE DATA
```ts
type JSONValue = string | number | boolean|JSONObject;
interface JSONObject{
	[keys:string]:JSONValue;
}
```