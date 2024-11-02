
| id                                               | hubs    | source                                                     |
| ------------------------------------------------ | ------- | ---------------------------------------------------------- |
| 202410181343_A template for implementing methods | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=159]] |
Whenever you design a method you, you should remember the following template:
```ts
[scope] function methodName(type name,...):void [return type]
{
	[precondition checks]
	[failure scenarios]
	[happy path]
	[postcondition checks]
	[return void|specific-return-type]
}
```
[[202410181345_Precondition checks]]
[[202410181356_Failure scenarios]]
[[202410181359_Happy path]]
[[202410181401_Postcondition checks]]
[[202410181404_Return value]]
