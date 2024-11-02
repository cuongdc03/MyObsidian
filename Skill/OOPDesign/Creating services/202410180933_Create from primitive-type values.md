
| id                                             | hubs    | source                                                     |
| ---------------------------------------------- | ------- | ---------------------------------------------------------- |
| 202410180933_Create from primitive-type values | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=110]] |
A common case for using named constructors is constructing an object from one or more primitive-type values. This results in methods like` fromString(), fromInt(),etc`. As an example, take a look at the following Date class.
![[Pasted image 20241018093414.png]]
It’s important to add a regular, but private, constructor method, so that clients won’t be able to bypass the named constructor you offer to them, which would possibly leave the object in an invalid or incomplete state.