#Correlated Crash Vulnerabilities
##Problem
Reliability is important in distributed system

Core mechanism: Replication

Replication can endure single machine crash.

THe problem is : correlated crashes (all data replicas crash at the same time) and recover together.

## How they solve the problem
Determine cuts in the distributed execution.

Generate persistent states corresponding to those cuts.

Recover based on cuts


