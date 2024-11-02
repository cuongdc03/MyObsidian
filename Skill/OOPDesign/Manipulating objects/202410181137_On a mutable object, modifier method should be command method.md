
| id                                                                         | hubs    | source                                                     |
| -------------------------------------------------------------------------- | ------- | ---------------------------------------------------------- |
| 202410181137_On a mutable object, modifier method should be command method | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=118]] |
Let’s look at another example, the Player class, which has a current position, encoded as values for X and Y. It’s a mutable object: it has a moveLeft() method, which updates (replaces, actually) the player’s position. The Position object is immutable, but the Player object itself is mutable.
![[Pasted image 20241018113909.png]]
We can recognize mutability by the assignment operator in moveLeft(): the position property gets a new value if you call this method. Another sign is the void return type. These two characteristics are the trademarks of a so-called command method.
Methods that change the state of an object should always be command methods like this. They have a name in the imperative form, they’re allowed to make a change to the object’s internal data structures, and they don’t return anything.