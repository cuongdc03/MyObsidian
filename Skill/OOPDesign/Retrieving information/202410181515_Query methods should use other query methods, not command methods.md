
| id                                                                             | hubs    | source                                                     |
| ------------------------------------------------------------------------------ | ------- | ---------------------------------------------------------- |
| 202410181515_Query methods should use other query methods, not command methods | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=188]] |
As we discussed, command methods can have side effects.If we get the division between command and query methods right in our code, a chain of calls that starts with a query won’t contain a call to a command method. This has to be true, because queries are supposed to have no side effects, and calling a command method somewhere in the chain will violate that rule.
![[Pasted image 20241018151626.png]]
There are some exceptions to this rule. Consider a controller method for a web application, which can be called to register a new user. This method will have a side effect:
somewhere down the chain of commands it will store a new user record in the data-
base. This would normally force us to use a void return type for the controller itself,
but a web application should always return an HTTP response. So the controller will
have to return at least something.
![[Pasted image 20241018151831.png]]
Technically speaking, the controller violates the command/query separation principle, but there’s no way around that. At the very least, we should return an empty 200 OK response or something like that. But that won’t be very useful for the frontend, which makes the “register user” POST request, and would like to be given a response with a JSON structure representing the newly created user.

To solve this case, you should divide the controller’s action into two parts: registering the new user and returning it. Preferably you’d also determine the new ID of the user before calling the RegisterUser service, so the service doesn’t have to returnanything at all and can be a true command method. This is demonstrated in the following listing.
![[Pasted image 20241018151932.png]]
![[Pasted image 20241018151943.png]]
