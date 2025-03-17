There are several raids set ups to help with data loss and IO support parallelization.

Raid 0 is a misnomer, there is no redundancy
Raid 1 is expensive, there is straight mirroring. 
Raid 2, nobody uses Raid 2. 

Parity is one such scheme (see Section 5.5). When a disk fails,
then you subtract all the data in the good disks from the parity
disk; the remaining information must be the missing information.
Unlike RAID 1, many disks must be read to determine the
missing data. The assumption behind this technique is that taking
longer to recover from failure but spending less on redundant
storage is a good tradeoff.


RAID 5 vs RAID 4

![[Pasted image 20240417083900.png]]