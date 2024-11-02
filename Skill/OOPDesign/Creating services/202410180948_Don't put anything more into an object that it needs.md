
| id                                                                | hubs    | source                                                     |
| ----------------------------------------------------------------- | ------- | ---------------------------------------------------------- |
| 202410180948_Don't put anything more into an object that it needs | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=114]] |
It’s common to start designing an object by thinking about what needs to go in. For services, you may end up injecting more dependencies than you need, so you should inject dependencies only when you need them. The same is true for other types of objects: `don’t require more data than is strictly needed to implement the object’s behavior.`
One type of object that often ends up carrying around more data than needed is an event object, representing something that has happened somewhere in the application.
# Example 
![[Pasted image 20241018095028.png]]
