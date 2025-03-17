The hardware on the chip that helps with address translation, this register hold the pass address of the program being ran (the program always thinks its start at 0.) Every reference the program makes is add to the MMU value's to get the real physical location of the memory space.


Some MMU also contain the location of the end of the program's space. If a program is allocated only 4kb of memory, the MMU will contain the the address the program started at + the address space, it will always check that the program is never going past its address space.

See [[Base and Bounds]]