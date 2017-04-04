## Poseidon CMU

### Bosen (for Network efficiency)

Network bounded.

* hash table for partial output communication, which minimize lock contention.

* BSP (bulk synchronous parallel) v.s. TAP (total asynchronous parallelization): for machine learning, we use BSC (bounded staleness consistency)


## GPU Net
a socket abstraction for GPU to directly access NIC

ring buffer: 1) for queue with fixed maximum size. 2) well-suited for FIFO, whereas non-circular buffer suited for LIFO.

## Adam (MSR)

* model parallel, data parallel. 

* Try to partition data into l3 cache. 

* converlution layer: periodic checkpointing

* Fully connected layer: send activate & error gredient vector instead of Weight Matrix.


## explore bounded staleness data in ML

* reduce communication => using stale parameters and update the parameters after X round of iteration.
