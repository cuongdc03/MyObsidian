
| id                                 | hubs    | source                                                     |
| ---------------------------------- | ------- | ---------------------------------------------------------- |
| 202410181151_Compare whole objects | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=142]] |
With mutable objects, you can write tests like the following.
![[Pasted image 20241018115750.png]]
As mentioned earlier, this kind of testing usually forces additional getters to be added to the class. These getters are only needed for writing the tests; no other client might be interested in them.
With immutable objects, you can often resort to a different kind of assertion—one that allows the object to keep its internal data and implementation details on the inside, as follows.
![[Pasted image 20241018115824.png]]
assertEquals() will use a recursive method that tests for the equality of the properties of both objects, and of the objects it keeps inside those properties, and so on.
Using assertEquals() therefore prevents value objects from having some hidden aspect that would make two objects incomparable.