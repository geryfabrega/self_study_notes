FC Shell is the Fabric Controller Shell.

$t.Nodes -> shows states physical blades in datacenter

$t.Containers -> shows states of the virtual machines

$t.RoleInstances -> shows state of workload, I think this is effectively the SF node health

$t.Jobs -> shows all pending or executing jobs

$t.Jobs[0].FabricWorkEvents -> shows what a particular job is waiting on. In this case it says "RoleInstances: _DB_10 Node: <id> is still in an active host update grouped impact"

also, $n.events where $n is a selected node shows what all is happening on the physical node. When we look at this one that DB_10 is one, it shows it's actively getting new goal states

For shell location look at the following address
`
builds\branches\git_azure_compute_master_latest\retail-
amd64\RDTools\FcShell\installFcShell.ps1 {installDir}

