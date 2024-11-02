
| id                             | hubs    | source                                                     |
| ------------------------------ | ------- | ---------------------------------------------------------- |
| 202410181356_Failure scenarios | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=161]] |
Even if the values “look” right and therefore pass the precondition checks, things can still go wrong.Just like the client provides a positive integer, it might not match a record ID in the database.This means that things could still go wrong while running the remaining method code.
If something goes wrong in the method after the precondition checks, you should throw a different kind of exception. It won’t be an exception indicating an invalid argument. The type of the exception should indicate that an error condition occurred that could only be detected at runtime![[Pasted image 20241018135900.png]]
