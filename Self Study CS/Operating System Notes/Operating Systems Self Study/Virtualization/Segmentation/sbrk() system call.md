
Sys call used to grow heap. typically used when something like [[malloc]] needs memory that is not available on the heap.

This sys call updates the segment size register to something larger. OS could reject this sys call if the amount of memory is not available. 