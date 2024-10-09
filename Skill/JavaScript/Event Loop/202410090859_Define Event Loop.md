
| id                             | hubs                            | source                                                                                              |
| ------------------------------ | ------------------------------- | --------------------------------------------------------------------------------------------------- |
| 202410090859_Define Event Loop | [[hubs/JavaScript\|JavaScript]] | https://nodejs.org/en/learn/asynchronous-work/event-loop-timers-and-nexttick#what-is-the-event-loop |
# What is the Event Loop?

The event loop is what allows Node.js to perform non-blocking I/O operations — despite the fact that a single JavaScript thread is used by default — by offloading operations to the system kernel whenever possible.

Since most modern kernels are multi-threaded, they can handle multiple operations executing in the background. When one of these operations completes, the kernel tells Node.js so that the appropriate callback may be added to the **poll** queue to eventually be executed. We'll explain this in further detail later in this topic.
# Event Loop Explained
![[Pasted image 20241009142102.png]]
