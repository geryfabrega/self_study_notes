This investigation is regarding various stuck workflows ICM in ussec.

CreateDatabaseCopy workflow in state waitforCatchUpOnLocalSite with requreset ID <guid> is stuck

however after speaking to various people regarding this, it's due to storage accounts being deleted. I do not understand how storage accounts are related to this



Current Method Call Stack
ManagementWorkflows.cs Line 17054
CreateDatabasecopy -> StartCopyWorkFlow -> StartDatabaseCopyManagementOperation
# StartCopyWorkflow finds current workflows, it also has the ability to create workflows 

![[Pasted image 20250409140314.png]]

It is believed the storage account key may be relate to GeoDR workflows..



