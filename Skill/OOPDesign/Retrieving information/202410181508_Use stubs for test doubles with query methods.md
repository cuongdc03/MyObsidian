
| id                                                         | hubs    | source                                                     |
| ---------------------------------------------------------- | ------- | ---------------------------------------------------------- |
| 202410181508_Use stubs for test doubles with query methods | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=185]] |
You can easily change the implementation details of how the answer will be found. Testing this logic will be easier too. Instead of only being able to test the `CurrencyConverter` service when an internet connection (and the remote service) is available, you can now test the logic by replacing the injected `ExchangeRates` service with one that already has the answers and will supply them in a predictable manner.
![[Pasted image 20241018150955.png]]
![[Pasted image 20241018151004.png]]

