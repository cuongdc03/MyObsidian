
| id                                | hubs    | source                                                     |
| --------------------------------- | ------- | ---------------------------------------------------------- |
| 202410181401_Postcondition checks | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=162]] |
Postcondition checks can be added to a method to verify that the method did what it was supposed to do. You could analyze the return value before actually returning it, or you could analyze the state of the object just before jumping out of it.
```ts
public function someVeryComplicatedCalculation():int{
	//...
	result = /* ...*/
	Assertion.greaterThan(0,result);//postcondtition check
	return result;
}
```