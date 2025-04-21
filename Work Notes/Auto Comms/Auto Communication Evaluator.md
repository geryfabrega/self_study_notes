AutoCommunicationEvaluator.cs
[Customer Impact Evaluator - Search Code - Search](https://dev.azure.com/msdata/Database%20Systems/_search?action=contents&text=Customer%20Impact%20Evaluator&type=code&lp=code-Project&filters=ProjectFilters%7BDatabase%20Systems%7DRepositoryFilters%7BSqlTelemetry%7D&pageSize=25&result=DefaultCollection/Database%20Systems/SqlTelemetry/GBR2D2//Src/MdsRunners/MdsRunners/Runners/IncidentManagement/AutoCommunicationEvaluator.cs)

This Runner is what polls the HPDB for created incidents.
It Submits Customer Impact Event to Brain


/Current NOtes 4/17/2025

AutoCommunication Runners in USSEC seems to be reaching out to public Kusto queries
This Runner should be paramterized to work in the Highside. 

Make a PR to 
1. Reach out to the correct BRAIN endpoint
2. Have it point to the correct Kusto configs
3. Create the kusto Tables in the highside for it to use. 
4. In HPDB input MaxAllowedAutoCommEvents_ 

Highside logs 
"Trying to get Kusto Connection Configuration data from"
