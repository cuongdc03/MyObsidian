
| id                                 | hubs    | source                                                     |
| ---------------------------------- | ------- | ---------------------------------------------------------- |
| 202410180930_Use named constructor | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=110]] |
For services, it’s fine to use the standard way of defining constructors (public function__construct()). However, for other types of objects, it’s recommended that you use named constructors. These are public static methods that return an instance. They could be considered object factories
[[202410180933_Create from primitive-type values]]
[[202410180936_Don't immediately add toString(),toInt(),etc]]
In summary, the using named constructors offers two main advantages:
- They can be used to offer several ways to construct an object.
- They can be used to introduce domain-specific synonyms for creating an object.
Besides creating entities and value objects, named constructors can be used to offer convenient ways to instantiate custom exceptions. We’ll discuss these later, in section 5.2.