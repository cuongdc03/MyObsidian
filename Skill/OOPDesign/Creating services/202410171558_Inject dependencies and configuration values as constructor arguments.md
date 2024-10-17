
| id                                                                                 | hubs    | source                                                    |
| ---------------------------------------------------------------------------------- | ------- | --------------------------------------------------------- |
| 202410171558_Inject dependencies and configuration values as constructor arguments | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=49]] |

A service usually needs other services to do its job. Those other services are its dependencies, and they should be injected as constructor arguments. The following File-Logger class is an example of a service with its dependency.
![[Pasted image 20241017155957.png]]
Making every dependency available as a constructor argument will make the service
ready for use immediately after instantiation. No further setup will be required, and
you can’t accidentally forget to provide a dependency.
