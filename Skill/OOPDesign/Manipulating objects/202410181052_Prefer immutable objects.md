
| id                                    | hubs    | source                                                     |
| ------------------------------------- | ------- | ---------------------------------------------------------- |
| 202410181052_Prefer immutable objects | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=132]] |
Most objects that are not entities should be implemented as immutable value objects.
![[Pasted image 20241018105729.png]]
It’ll always be safe to keep a reference to an immutable object.