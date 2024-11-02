
| id                                                               | hubs    | source                                                     |
| ---------------------------------------------------------------- | ------- | ---------------------------------------------------------- |
| 202410181431_Query methods should have single-type return values | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=171]] |
|                                                                  |         |                                                            |
When a method returns a piece of information, it should return a predictable thing.
No mixed types are allowed. Most languages don’t even support mixed types, but PHP,being a dynamically typed language does. Take, for example, the following isValid() method, which omits a return type, allowing several types of things to be returned.This will be very confusing for its users.![[Pasted image 20241018143316.png]]