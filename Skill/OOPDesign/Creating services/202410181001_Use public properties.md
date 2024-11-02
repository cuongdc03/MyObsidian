
| id                                 | hubs    | source                                                     |
| ---------------------------------- | ------- | ---------------------------------------------------------- |
| 202410181001_Use public properties | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=118]] |
Since a DTO doesn’t protect its state and exposes all of its properties, there is no need for getters and setters. This means it’s quite sufficient to use public properties for them. Because DTOs can be constructed in steps and don’t require a minimum
amount of data to be provided, they don’t need constructor methods.
DTOs are often used as command objects, matching the user’s intention and containing all the data needed to fulfill their wish. An example of such a command object is the following ScheduleMeetup command, which represents the user’s wish to schedule a meetup with the given title on the given date.
![[Pasted image 20241018100408.png]]
```php
final class MeetupController
{
public function scheduleMeetupAction(Request request): Response
{
	formData= /* ...*/
	scheduleMeetup = new ScheduleMeetup();
	scheduleMeetup.title = formData['title'];
	scheduleMeetup.date = formData['date'];
	this.scheduleMeetupService.execute(scheduleMeetup);
```
The service will create an entity and some value objects and eventually persist them. When instantiated, these objects will throw exceptions if anything is wrong with the data that was
provided to them. However, such exceptions aren’t really user friendly; they can’t even be easily translated to the user’s language. Also, because they break the application’s flow,
exceptions can’t be collected and returned as a list of input errors to the user.