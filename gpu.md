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


## Explore bounded staleness data in ML

* reduce communication => using stale parameters and update the parameters after X round of iteration.


## Google TPU evaluation

https://cloudplatform.googleblog.com/2017/04/quantifying-the-performance-of-the-TPU-our-first-machine-learning-chip.html

## GeePS (eurosys16)

GPU/CPU data movement in the background. (staging, pipeline) partial data movement.
