#Simplifying Datacenter Network Debugging with PathDump
## Problem
Network debugging is complecated and need to take all the components into consideration

### problem with existing works

HSA [NSDI’12], Anteater [SIGCOMM’11] : analysis based on statics network snapshots => hard to get the consistent network states.

NetSight [NSDI’14]: per switch logging => high bandwidth and processing overhead.

Everflow [SIGCOMM’15], Planck [SIGCOMM’14] : Selective packet sampling and mirroring => identifying packets to sample for debugging problems is complex

Pathquery [NSDI’16]: SQL-like queries on switches => need dynamically installing switch rules.



## nugget

Divide and conquer

##How PathDump works

tracing packet trajectories : embedding switchID along the packet trajectory (using sampling to reduce the header space)

On the end host: get the switchID from the packet header, records them in a local storage. This storage is used for network debuggin query.

