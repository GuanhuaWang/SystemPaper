#XFT: Practical Fault Tolerance Beyond Crashes

##Problem
Current fault tolerent scheme are CFT (Crash fault-tolerent). Therefore they cannot deal with non-crash fault, like malicious behavior.

BFT (Byzantine fault tolerance) can deal with non-crash fault. However, its overhead is too high compared with CFT.

##XFT(cross fault tolerant)

No need assumption of BFT that the adversaries are that powerful.

Reduce latency: (totoal 2t+1 replicas) Xpaxos only synchronously replicate clienets request to only t+1 replicas `active`. the other n `passive` replicas are using *lazy replication approach*

Difference from CFT or BFT: generate views using all the t+1 active replicas instead of the primal replica. Ensure data consistency.

FD scheme (fault detection like BFT): For non-crash faulty replica, we do not allow it to transfer its latest state to a correct replica in new sync group. It can eliminite the data poisoning from the non-crash faulty replica.
