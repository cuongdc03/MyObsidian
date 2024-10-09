
| id                            | hubs                            | source                                                                    |
| ----------------------------- | ------------------------------- | ------------------------------------------------------------------------- |
| 202410091030_Memory lifecycle | [[hubs/JavaScript\|JavaScript]] | https://developer.mozilla.org/en-US/docs/Web/JavaScript/Memory_management |
# Memory life cycle
Regardless of the programming language, the memory life cycle is pretty much always the same:

1. Allocate the memory you need
2. Use the allocated memory (read, write)
3. Release the allocated memory when it is not needed anymore
The second part is explicit in all languages. The first and last parts are explicit in low-level languages but are mostly implicit in high-level languages like JavaScript.