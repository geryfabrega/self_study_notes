When Allocator finds a free space in the free list and chops and address to only take what it needs.
Look below

![[Pasted image 20250331103726.png]]

Lets say our allocator only takes in 1 byte. The free list will split and turn into this

![[Pasted image 20250331103758.png]]
This is a simple example as there is still two contnious portions of free memory. 