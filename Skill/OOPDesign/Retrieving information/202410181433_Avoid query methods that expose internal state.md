
| id                                                          | hubs    | source                                                     |
| ----------------------------------------------------------- | ------- | ---------------------------------------------------------- |
| 202410181433_Avoid query methods that expose internal state | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=152]] |
The simplest implementation for query methods is usually to return a property of the object. These methods are known as getters, and they allow clients to “get” the object’s
internal data.
A first example is the following `getItems()` method, which returns the items in a shopping basket just so the client can count them. Instead of directly exposing the items, the basket could provide a method that counts the items for the client.
### Before
```ts
final class ShoppingBasket
{
public function getItems(): array
{
return this.items;
}
}
count(basket.getItems());
// ...
```
### After
```ts
final class ShoppingBasket
{
// ...
public function itemCount(): int
{
return count(this.items);
}
}
basket.itemCount();
```


Besides no longer needing to repeat this logic at different call sites, this alternative has two more advantages. First, we can stop exposing internal data like the discount percentage and the fixed discount. Second, when the calculation changes, it can be
changed and tested in one place.
In short, always look for ways to prevent the need for query methods that expose the object’s internal data:
- Make the method smarter, and adapt it to the actual need of its clients.
- Move the call inside the object, letting it make its own decisions
![[Pasted image 20241018144249.png]]
