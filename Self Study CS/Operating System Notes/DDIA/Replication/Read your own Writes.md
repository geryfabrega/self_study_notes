Users often want to verify that their writes go through. However, when they issue reads, the reads are sent to the replica, however, the replica may have stale information.

This means the user may issue a write, but then this write is IN the primary/leader but not in the slave, meaning the data may appear to have dissapeared.

To mitigate this there must be certain edge cases or bits of logic to ensure that people that write can also do reads from the primary if its extremly recent. it really depends on the application. For istnace, if its a social media app. we cam have any profile reads from the master. before we know a user may be writting via the profile.  this will not work for other parts of the app like writing comments or doing other things.

User would be happier in the case we mitigate this.

![[Pasted image 20250322235544.png]]