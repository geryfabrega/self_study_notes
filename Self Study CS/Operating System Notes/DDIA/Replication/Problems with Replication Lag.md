Replication can be good for 
-Scaling (more requests handled at once)
-Latency (have more DBs closer to users)
-Redundancy (if something goes down we have fialover)

Capacity for read only data bases increases very well with this method.
We can scale read only replicas very easily/

replicas may have stale information, however if you wait they will be consistant see [[Eventual Consistancy]]