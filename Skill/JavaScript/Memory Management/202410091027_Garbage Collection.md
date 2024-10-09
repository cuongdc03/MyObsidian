
| id                              | hubs                            | source                                     |
| ------------------------------- | ------------------------------- | ------------------------------------------ |
| 202410091027_Garbage Collection | [[hubs/JavaScript\|JavaScript]] | https://javascript.info/garbage-collection |
# Reachability
The main concept of memory management in JavaScript is _reachability_.
Simply put, “reachable” values are those that are accessible or usable somehow. They are guaranteed to be stored in memory.

1. There’s a base set of inherently reachable values, that cannot be deleted for obvious reasons.
    
    For instance:
    
    - The currently executing function, its local variables and parameters.
    - Other functions on the current chain of nested calls, their local variables and parameters.
    - Global variables.
    - (there are some other, internal ones as well)
    
    These values are called _roots_.
    
2. Any other value is considered reachable if it’s reachable from a root by a reference or by a chain of references.
    
    For instance, if there’s an object in a global variable, and that object has a property referencing another object, _that_ object is considered reachable. And those that it references are also reachable. Detailed examples to follow.
    