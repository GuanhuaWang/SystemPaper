# Can Far Memory Improve Job Throughput?

Intersting paper, try to use RDMA achieve fast and usable memory disaggratation in simulations

Highlights:

* build two RDMA fetch queue: 1 for critical path fetch, 1 for prefetch.

* Offload memory reclaims to dedicated CPU and make it off the creitical path, [alpha] buffer for warm-up memory reclaims
