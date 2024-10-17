
| id                            | hubs          | source                                  |
| ----------------------------- | ------------- | --------------------------------------- |
| 202410171139_Two Jest flavors | [[Unit Test]] | [[the_art_of_unit_testing.pdf#page=70]] |
As you’ve seen, Jest supports two main ways to write tests: a terse test syntax, and a
more describe-driven (i.e., hierarchical) syntax.
The describe-driven Jest syntax can be largely attributed to Jasmine, one of the
oldest JavaScript test frameworks. The style itself can be traced back to Ruby-land and
the well-known RSpec Ruby test framework. This nested style is usually called BDD
style, referring to behavior-driven development.
You can mix and match these styles as you like (I do). You can use the test syntax
when it’s easy to understand your test target and all of its context, without going to too
much trouble. The describe syntax can help when you’re expecting multiple results
from the same entry point under the same scenario. I’m showing them both here
because I sometimes use the terse test flavor and sometimes use the describe-driven
flavor, depending on the complexity and expressiveness requirements
![[Pasted image 20241017114059.png]]
