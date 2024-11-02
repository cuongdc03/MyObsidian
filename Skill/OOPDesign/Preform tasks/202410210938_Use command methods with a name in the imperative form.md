
| id                                                                  | hubs    | source                                                     |
| ------------------------------------------------------------------- | ------- | ---------------------------------------------------------- |
| 202410210938_Use command methods with a name in the imperative form | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=194]] |
We already discussed query methods and how you should use them to retrieve information. Query methods have a specific return type and no side effects, meaning that it’s safe to call them several times, and the application’s state won’t be any different
afterwards.
For performing tasks, you should always use a command method, which has a void return type. The name of such a method should indicate that the client can order the object to perform the task that the method name indicates. When looking for a good name, you should always use the imperative form. The following listing shows some examples.![[Pasted image 20241021094025.png]]
