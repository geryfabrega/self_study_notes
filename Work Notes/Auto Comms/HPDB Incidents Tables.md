
![[Pasted image 20250421114424.png]]

`SELECT * from Incidents WHERE EventType = 'Closed' order by DateCreatedDesc`


There is a row for each incident. Each incident contains the region, sql server, and database name. The [[Auto Communication Evaluator]] then fetches the impacted resources ids from kusto (Which Table does it use?)

The eventType Column has several states (initial, closed, etc)
The auto eval runners is always looking for 'initial', after the indicent is closed the state is changed to closed.

TODO: Look up region of the each 