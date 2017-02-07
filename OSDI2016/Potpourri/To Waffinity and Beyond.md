#To Waffinity and Beyond: A Scalable Architecture for Incremental Parallelization of File System Code

`Classical waffinity`: unable to achieve incremental parallelization

Therefore, we have `hierarchical waffinity`, hierarchical aggregate data volume, instead of only one top aggregate.

However, sometimes we need to access two different file blocks. Traditional case can only ensure we access 1 block.

Therefore, we need `Hybrid waffinity` to combine partitioning with fine-grained locking. 1) Particular blocks are protected with locking from multiple affinities. 2) continues to allow incremental development.
