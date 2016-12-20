#The SNOW Theorem and Latency-Optimal Read-Only Transactions
##Background
Why sharding?

1. Sharding is horizontal partitioning of a database. (split rows)
2. These partition share the same table structure.

##Problem


##SNOW theorem:
It is IMPOSSIBLE for read only transaction algorithm to provide all four desirable properties:
* Strict serializability
* Non-blocking operations
* One-response from each shard
* Compatibility with conflicting Write trasctions
