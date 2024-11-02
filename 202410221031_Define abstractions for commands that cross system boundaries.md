
| id                                                                         | hubs    | source                                                     |
| -------------------------------------------------------------------------- | ------- | ---------------------------------------------------------- |
| 202410221031_Define abstractions for commands that cross system boundaries | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=204]] |
If a command method has code that reaches out across the application’s own boundaries (that is, if it uses a remote service, the filesystem, a system device, etc.), you
should introduce an abstraction for it.
![[Pasted image 20241022103208.png]]
