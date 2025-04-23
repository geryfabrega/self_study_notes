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


When this Infra runner picks up an incident from HPDB, it also picks impact assessment logic. [[Custom ImpacetAssessment]] or [[Default Impact Assessment]]
For the most part, the default impact assessment logic is just a kusto query of the impacted server and database.  The auto comms eval runners looks at all incidents in the [[HPDB Incidents Tables]]

The Eval Runner then forms a [[Brain JSON Payload]] that BRAIN can accept.
Brain accepts server signals. BRAIN can do correlations and notify customers and DRIs. It can also propose mitigations and diagnostics. 


Brain will then update the impact chart in the ICM. Brian will populate the number of impacted resources. 

What else does BRAIN do?

It sends an outage notification of the outage in the outage portal. all customer will be notified of the outage  of all the effected resources.

(How can we test the auto comm?)