
| id                                    | hubs    | source                                                     |
| ------------------------------------- | ------- | ---------------------------------------------------------- |
| 202410181010_Use property when needed | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=120]] |
In the case of a DTO, this isn’t a problem because a DTO doesn’t protect its internals anyway. So, if it makes sense, you can add a property filler method to a DTO, such as to copy form data or JSON request data directly into a command object.
```php
final class ScheduleMeetup
{
public string title;
public string date;
public static function fromFormData(
array formData
): ScheduleMeetup {
scheduleMeetup = new ScheduleMeetup();
scheduleMeetup.title = formData['title'];
scheduleMeetup.date = formData['date'];
return scheduleMeetup;
}
}
```