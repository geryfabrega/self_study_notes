![[Pasted image 20250324231108.png]]
A portion of bits are saved to explicitaly state where the segment lies.
This way the portions of an [[Address Space]] are clearly defined and can quickly be fetched.

this as used the VAX/VMS System. 

For instnace if you have four segments then you can represent this with 2 bits. In this example we need three segmentrs. Data, [[heap]] and [[Operating Systems Self Study/Virtualization/Segmentation/Stack]]

[[Base and Bounds]] is still used to locate address space, but with particular segments being mapped via the first 2 bits

If an offset is greter than the bounds, then we have to throw a [[Segmentation]] FAULT

![[Pasted image 20250324231613.png]]

SEGMASK most likely looks like this 

00111111111111 (thats 12 ones); since we and, the result will be just the offset.

SOME system only use heap and stack, placing the code/data segment in the same category. Meaning only 1 bit is used for the segment.

