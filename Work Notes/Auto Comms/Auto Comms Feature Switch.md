When the infra runner [AutoCommunicationEvaluator](https://msdata.visualstudio.com/Database%20Systems/_git/SqlTelemetry?path=/Src/MdsRunners/MdsRunners/Runners/IncidentManagement/AutoCommunicationEvaluator.cs) (responsible for detecting and sending outage communication to BRAIN ) sends outage communication to BRAIN via a json payload it sets a field named ImpactAssessmentMaturityLevel in the payload indicating if outage should or should not be declared to the customer.

When ImpactAssessmentMaturityLevel is set to "ExternalAutoComms", it means outage communication should be sent to the customer and when ImpactAssessmentMaturityLevel is set to "Experimental", it means no outage communication should be sent to the customer and only the impact chart should be populated in the ICM. When initially testing your incidents for auto comm, it is recommended to set the ImpactAssessmentMaturityLevel FS value to Experimental and later when enough confidence is gained, the FS value can be changed to ExternalAutoComms.

Start by first enabling your runner for auto comm in Stage and only after it is validated, you can enable it for Prod.

Use the below insert query to insert the ImpactAssessmentMaturityLevel FS value for your runner in [Health Property Database (HPDB)](https://eng.ms/docs/cloud-ai-platform/azure-data/azure-data-azure-databases/sql-engineering/sql-telemetry/sql-db-telemetry/hpdb-infra/health-property-database-_hpdb_) .


Remember, please set to Experimental When Testing Runners Auto Comms

Remember,  this feature switch is set within HPDB

Make sure to look up the monitor ID.
Also specify is the runner is a data plane or control plane runner in the FS.


TO DO:
Check if the [[Auto Communication Evaluator]] and Alert Eval need any additional code changes or FS for it to check if any ICMs are enabled for Auto Comms.
