Dsms shell contains commands such as RollOver and PushCredentials

to push credentials you need to give it a arguments path from the DSMS kusto cluster

When pushing credentials they are staged on the first node. 
Then after 24 hours it pushes to all the nodes on every UD.


To force an early push

run another command *RefreshNodeCertificate* on TR 78 on CAS

