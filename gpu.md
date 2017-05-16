
### Distributed GPU
data parallelism: SIMD BSP (e.g. Spark/Hadoop)

model parallelism:

### Poseidon (Eric Xing)

https://github.com/sailing-pmls/poseidon

data transmission: partical data transmission (partial gradient Tx/Rx in Client-Server): One layer Tx/Rx instead of all layer data transmission.

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

Full Consistency: update function has complete read-write access to its entire scope.

Edge consistency: update function has read access to adjacent vetices.

Vertex consistency: write access to central vertex data

### color step to verify edge consistency

Color step (NP-hard, thus using greedy method): 

1. edge consistency => Assign color to each vertex such taht no adjacent vetices share same color.

2. Full consistency => no vertex share same color as any of its distance two neighbors.

3. Vertex consistency => all vertics in one color.

After color step. we can synchronously executing all vertices with same color.



## My thoughts

### Data staleness v.s. networking latency
Reduce to parameter server. Hash function, guarentee M concurrent data transmission between clients and parameter server. Others using their local stale parameters.

### Using rateless code (e.g. Spinal coding) to achieve load balancing or congestion control.

## GPU shortcoming

1. small GPU memeory

2. Expensive memory copy between GPU mem and CPU mem

3. Data-parallelism has benefits, but network communications overhead quickly limited scalability.


## Why we need parameter server?

https://www.quora.com/What-is-the-Parameter-Server

In a nutshell, it is more likely to be a shared blackboard.



## my thought 04/12/2017

SplitStream tree depth == stale data clock bound

WHY not P2P over workers: small messages transmission are evil. It is very difficult to keep data consistency.

erasure code :  (m+k) data split... pick fastest top m from it.   mitigate staleness of processing.

fine scale parallelism


## rhythm

The key insight is, given an incoming stream of requests, a server could delay some requests in order to align the execution of similar requests—allowing them to execute concurrently.


# How to use parameter server
http://pmls.readthedocs.io/en/latest/installation.html


### find more application scenarios.


## Hemingway

Mini-Batch (size b) SGD will introduce (root square of b) training error, compared with sequencial one-by-one data processing.

### main idea

Window based prediction of Loss function, give 50 iteration info., predict 51 or 51-60 iteration info. When combining with Erest (by shivaram), it can map the iteration number to time.


# TPU introduction
https://cloud.google.com/blog/big-data/2017/05/an-in-depth-look-at-googles-first-tensor-processing-unit-tpu

## key concepts
1. Systolic array: hold the intermediate data into the ALU, and communicate the itermediate data among ALUs without write it back to register or memory. The data processing flow is more like Ray.

2. TPU Low clock freqency. but highly parallel computing.

Operations per cycle
CPU	                                a few

CPU (vector extension)	            tens

GPU	                                tens of thousands

TPU	                                hundreds of thousands, up to 128K
