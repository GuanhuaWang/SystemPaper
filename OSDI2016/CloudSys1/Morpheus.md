# Morpheus: Towards Automated SLOs for Enterprise Clusters

##problem
try to make the job performance more predictable,especially for the periods tasks. (while achieve high cluster utilization efficiency, I don't buy it)
## handle two problem of unpredictable performance
1 `sharing-induced` performance variablity caused by inconsistent allocations of resources across job runs

2 `Inherent` perforamnce variablity caused by source code, data size different,etc.


## How they did it
1. Automatic inference: Inferring SLOs and modeling job resources demands. How:  derive target SLO by analysis historical execution trace.

2. Recurring Reservation: reserve resources based on the derived SLO (handle `sharing-induced` bias/varience)

3. Dynamic REprovisioning: monitor resources allocation. If progress slower/faster than expected, sccheduler can automatically adjust reservcation (handle `Inherent` variance)
