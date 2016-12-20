#The SNOW Theorem and Latency-Optimal Read-Only Transactions
##Background
### Why sharding?

1. Sharding is horizontal partitioning of a database. (split rows)
2. These partition share the same table structure.

### Typical webpage read
loading a webpage, multiple reads over many shards are issued (100s to 1ks) in parallel.

Some reads are dependent on earlier reads (e.g. read B using the key return by earlier read A)

"One-shot" read-only transactions -- no key dependences across shards.
##Problem
SNOW theorem says there is no way to keep both low latency and high consistency for read-only transaciotns.

##SNOW theorem:
It is IMPOSSIBLE for read only transaction algorithm to provide all four desirable properties:
* Strict serializability
* Non-blocking operations
* One-response from each shard
* Compatibility with conflicting Write trasctions

## Key insight

SNOW is tight, only nay combination of 3 are possible.

To make reads as fast as possible, we need to shift as much coordiation overhead as possible to wirtes.

## What they are doing
A slightly weaker consistency `process-ordered` serializability without breaking the other three properties.

`COPS-SNOW`: add "O" to COPS (which only has "N")

`Recoco-SNOW`: add "O" to Recoco (which has "S+W")
