
| id                                                                            | hubs    | source                                                     |
| ----------------------------------------------------------------------------- | ------- | ---------------------------------------------------------- |
| 202410211014_Make services immutable from the outsideas well as on the inside | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=198]] |
Service containers are often designed to share all service instances once they have
been created. This saves the runtime from instantiating the same service again,
should it be reused as a dependency of some other service. However, if a service is
immutable (as it should be), this sharing isn’t really needed. You could instantiate
the service over and over again.
Of course, there are services in a service container that shouldn’t be instantiated
again every time they’re used as a dependency. For instance, a database connection
object or any other kind of reference to a resource that needs to be created once and
then shared between dependent services. In general, however, your services
shouldn’t need to be shared. If you’ve followed all of the advice so far, you’re doing
well already, because immutable services don’t need to be shared. They can, but they
don’t have to.