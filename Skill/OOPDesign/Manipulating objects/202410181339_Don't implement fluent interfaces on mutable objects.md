
| id                                                                | hubs    | source                                                     |
| ----------------------------------------------------------------- | ------- | ---------------------------------------------------------- |
| 202410181339_Don't implement fluent interfaces on mutable objects | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=154]] |
An object has a fluent interface when its modifier methods return this. If an object has a fluent interface, you can call method after method on it, without repeating the
variable name of the object.
![[Pasted image 20241018134035.png]]
However, a fluent interface can be very confusing regarding which object a method gets called on. If QueryBuilder is immutable, then it doesn’t really matter. But who knows if it’s mutable? If you look at the method signatures of QueryBuilder in the following listing, there’s no way to find that out.
