
| id                                                           | hubs    | source                                                     |
| ------------------------------------------------------------ | ------- | ---------------------------------------------------------- |
| 202410180958_The exception to the rule Data transfer objects | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=118]] |
The rules described in this chapter apply to entities and value objects; we care a lot about the consistency and validity of the data that ends up inside such objects.
This special type of object is known as a data transfer object (DTO):
-  A DTO can be created using a regular constructor.
- Its properties can be set one by one.
- All of its properties are exposed.
- Its properties contain only primitive-type values.
- Properties can optionally contain other DTOs, or simple arrays of DTOs.
Rules:
- [[202410181001_Use public properties]]
- [[202410181008_Don't throw exceptions, collect validation errors]]
- [[202410181010_Use property when needed]]