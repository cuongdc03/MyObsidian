
| id                                                                          | hubs    | source                                                     |
| --------------------------------------------------------------------------- | ------- | ---------------------------------------------------------- |
| 202410181453_Define an abstraction for queries that cross system boundaries | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=181]] |
As soon as an application crosses a system boundary, you should introduce an abstraction, allowing you to hide the low-level communication details of the calls that are going on behind the scenes.
Abstraction in this case means two things, and it can only be successful when you
have both ingredients:
- Using a service interface instead of a service class
- Leaving out the implementation details
By defining an interface for the existing class, we performed the first step of a successful abstraction. By hiding all the implementation details behind the interface, we also performed the second step, meaning we now have a proper abstraction for
retrieving exchange rates. This comes with two advantages:
- We can easily switch to a different params
- We can write a unit test fo function and inject a test double for function
By the way, if you know about the SOLID principles, you’ve already encountered a similar rule for abstraction of service dependencies, known as the `dependency inversion principles`