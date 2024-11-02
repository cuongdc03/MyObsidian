
| id                               | hubs    | source                                                     |
| -------------------------------- | ------- | ---------------------------------------------------------- |
| 202410181345_Precondition checks | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=160]] |
The first step is to verify that the arguments provided by the client are correct and can be used to fulfill the task at hand. Make any number of checks, and throw exceptions when anything looks off.
Precondition checks have the following shape:
```ts
if (/* Some precondition wasn't met*/){
	throw new InvalidArgumentException(/*.....*/)
}
```
To shorten, can use assertion function for these kind of checks
### Example 
```ts
Assertion.inArray(value, ['allowed', 'values']);
```
## Introduce new type to get rid of precondition checks
Most of these assertions will be made to validate primitive-type arguments (int,string, etc.). As we saw in section 3.5, it often makes sense to introduce wrapper objects for these primitive-type values and move the related assertions to the constructors of these objects.
### Before
```ts
public function sendConfirmationEmail(string emailAddress): void
{
Assertion.email(emailAddress);
//...
}
```
### After
```ts
final class EmailAddress
{
private string emailAddress;
public function __construct(string emailAddress)
{
Assertion.email(emailAddress);
this.emailAddress = emailAddress;
}
}
public function sendConfirmationEmail(
EmailAddress emailAddress
): void {
// no need to validate emailAddress anymore
}
```