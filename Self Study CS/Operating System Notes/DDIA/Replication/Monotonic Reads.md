When [[Replica DB]] reads from [[Primary DB]] there is some latency. If there are multiple replicas, and issue can occur where a user of the system reads from a replica DB that is laggy, then read from a replica that is even more laggy. So the data the system or application appears to go backwards in time. Monotinc reads is a guarentee that this king of anomaly does not happen.

This means that if a user does several reads to the system this will never happen. 

We can ensure that the user reads from the same replica by using some hashing to ensure the same USER ID gets reads from the same replica. however if the replica fails then we need some routing mechanism to route to a different functioning DB. 
