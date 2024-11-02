
| id                                                        | hubs    | source                                                     |
| --------------------------------------------------------- | ------- | ---------------------------------------------------------- |
| 202410180936_Don't immediately add toString(),toInt(),etc | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=111]] |
When you add a named constructor that creates an object based on a primitive-type value, you may feel the need for symmetry and want to add a method that can convert the object back to the primitive-type value. For instance, having a `fromString()` constructor may lead you to automatically provide a `toString()` method too. Make sure you only do this once there is a proven need for it.