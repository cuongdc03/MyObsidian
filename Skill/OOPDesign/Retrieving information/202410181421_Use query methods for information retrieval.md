
| id                                                       | hubs    | source                                                     |
| -------------------------------------------------------- | ------- | ---------------------------------------------------------- |
| 202410181421_Use query methods for information retrieval | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=168]] |
If you want to retrieve information from an object, you should use a query method. Such a method does have a specific return type, and it’s not allowed to produce any side effects.
Take a look at Counter class 
```ts
final class Counter
{
private int count = 0;
public function increment(): void
{
this.count++;
}
public function currentCount(): int
{
return this.count;
}
}
counter = new Counter();
counter.increment();

assertEquals(1, counter.currentCount());
```
According to the rules for command and query methods, it’s clear that `increment()` is a command method, because it changes the state of a Counter object. current-Count() is a `query method`, because it doesn’t change anything; it just returns the current value of count. The good thing about this separation is that given the current state of a Counter object, calling `currentCount()` will always return the same answer.
Take another look
```ts
public function increment(): int
{
this.count++;
return this.count;
}
```
This method makes a change and returns information. This is confusing from a client perspective; the object changes even if you just want to look at it.
It’s better to have safe methods that can be called any time (and, in fact, can be called any number of times), and other methods that are “unsafe” to call. There are two ways to achieve this:
- Follow the rule that a method should always be either a command or a query method. This is called the command/query separation principle (CQS).1 We applied it in the initial implementation of Counter (listing 6.1): increment() was a command method, currentCount() a query method, and none of the methods of Counter were both command and query methods at the same time.
- Make your objects immutable (as has been previously advised for almost all objects in your application).