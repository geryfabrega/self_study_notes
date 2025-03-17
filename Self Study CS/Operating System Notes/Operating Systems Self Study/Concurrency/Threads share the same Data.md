Dun dun dun!!!!
Threads have their own set of registers, when switching a context switch takes place. They also have their own [[Program Counters]]

With Processes we saved their state to a [[Proccess Control Block]] , but with threads we have a [[thread Control Blocks]]

When we context switch between threads, there is no longer the need to switch between [[page tables]] since they share the same memory.

![[Pasted image 20250316233313.png]]