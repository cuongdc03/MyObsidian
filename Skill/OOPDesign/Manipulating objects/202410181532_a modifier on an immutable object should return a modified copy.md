
| id                                                                          | hubs    | source                                                     |
| --------------------------------------------------------------------------- | ------- | ---------------------------------------------------------- |
| 202410181110_A modfier on an ummutable object should return a modified copy | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=136]] |
There are two basic templates for these methods. The first uses the (potentially private) constructor of the object, to create the desired copy, like the plus() method in the next listing.![[Pasted image 20241018111208.png]]
The other option,which can sometimes be useful for immutable objects with multiple properties, is to create an actual copy of the object using the clone operator, and then make the desired change to it
![[Pasted image 20241018111307.png]]
Instead of making the client do the calculations, you can let the Position object
do it. You only need to offer a more convenient modifier method, such as toTheLeft() in the following listing.
![[Pasted image 20241018111635.png]]