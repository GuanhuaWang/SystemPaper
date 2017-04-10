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

Parameters: shard of parameters maintain on local single machine, each machine also maintain a stale global parameter cache. (May use P2P communication)


## Exploring iterative-ness
leveraging repeat pattern of shared data (i.e. parameters in ML)

parameter server: no state update conflicts. the weights can be updated in any order within a CLOCK.

## parameter server (Mu Li)

*machine learning MapReduce parameter server*

## STRADS: A Distributed Framework for Scheduled Model Parallel Machine Learning

improve convergence speed of model parallel ML at scale

### control parameter staleness:
SSP (stale synchronous parallel): book-keeping on deviation between workers.

STRADS: control pipeline depth.

STRADS: model parallel instead of Data parallel.

Parameter server: couple data and control plan.....
Whereas STRADS decouple data and control plan. Either in Ring structure or Pipeline data processing over communication


## Distributed GraphLab (VLDB 2012)

Serializability:

![](consistency.png)
