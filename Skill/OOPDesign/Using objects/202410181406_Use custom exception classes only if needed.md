
| id                                                       | hubs    | source                                                     |
| -------------------------------------------------------- | ------- | ---------------------------------------------------------- |
| 202410181406_Use custom exception classes only if needed | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=163]] |
Adding a custom exception class can be very helpful in certain circumstances:
1, If you want to catch a specific exception type higher up
```ts
try {
		//possibily throws 'Somespecific exception'
		} catch (SomeSpecific exception){
		//...
		}
}
```
2, If there are multiple ways to instantiate a single type of exception 
```ts
final class CouldNotDeliverOrder extends RuntimeException
{
public static function itWasAlreadyDelivered():
CouldNotDeliverOrder
{
// ...
}
public static function insufficientQuantitiesInStock():
CouldNotDeliverOrder
{
// ...
}
}
```
3, If you want use named constructors for instantiating the exception
```ts
final class CouldNotFindProduct extends RuntimeException
{
public static function withId(
ProductId productId
): CouldNotFindProduct {
return new CouldNotFindProduct(
'Could not find a product with ID "{productId}"'
);
}
}
throw CouldNotFindProduct.withId(/* ... */);
```