The stack grows backwards in a the [[Address Space]] it starts at 28kb but grows in reverse. to track which direction it grows more hardware is needed than just the traditional [[Base and Bounds]]

There is a need of a register that holds the direction of travel.
![[Pasted image 20250324232607.png]]

Since the stack grows backwards we have to use a special strat to fetch lower addresses.
how is this done?

We must fetch the offset. then when translating we actually do 
Maximum Segment value - offset. That delta is what we substracr from the virtual address to translate to get the phyisical address.

