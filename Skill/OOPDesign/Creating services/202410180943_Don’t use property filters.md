
| id                                      | hubs    | source                                                     |
| --------------------------------------- | ------- | ---------------------------------------------------------- |
| 202410180943_Don’t use property fillers | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=112]] |
Applying all the object design rules in this book will lead to objects that are in complete control of what goes into them, what stays inside, and what a client can do with them. A technique that works completely against this object design style is property filler methods, which look like the following fromArray() method.
```php
final class Position
{
private int x;
private int y;
public static function fromArray(array data): Position
{
position = new Position();
position.x = data['x'];
position.y = data['y'];
return position;
}
}
```
This kind of method could even be turned into a generic utility that would copy values from the data array into the corresponding properties using reflection. Though it may look convenient, the object’s internals are now out in the open, so always make
sure that the construction of an object happens in a way that’s fully controlled by the object itself.
# NOTE 
At the end of this chapter, we’ll look at an exception to this rule. For data transfer objects, a property filler could be a way to map, for example, form data onto an object. Such an object doesn’t need to protect its internal data as much as an entity or a value object has to.