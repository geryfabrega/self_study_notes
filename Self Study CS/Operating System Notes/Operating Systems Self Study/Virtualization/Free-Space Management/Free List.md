![[Pasted image 20250331103354.png]]
Linked list Data strucutre used here

[[Free List Management]]
THere is metadata linked list, therefore memory interface will have to be intelligent and crawl over this list to find approporate amount of memory to place on the head and to give process ownership.


If there is a request for something larger than 10 bytes, it will fail.

If there is a reuqest for something larger than 10 bytes then the allocator will do a [[Split]]
