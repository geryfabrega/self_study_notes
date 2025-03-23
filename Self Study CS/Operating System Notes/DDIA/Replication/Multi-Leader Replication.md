Single leader replication is hardly ever used as that would imply that there is only a leader at a time, meaning all write and reads will be going through a single data center. This is not a good model to follow.

In a multi-leader configuration you can have a leader in each data center. 
![[Pasted image 20250323002523.png]]

Each [[Primary DB]] replicates its changes to another leader in some other data center. 

Some DBs support multi leader configurations by default. However often implemented with external tools such as [[Tungsten Replicator]], [[BDR]] and [[GoldenGate]]

Trade off, all writes need to be processed through some write conflict process.

It is often the case that multipl leader replication is dangerous and should be avoided if possible.