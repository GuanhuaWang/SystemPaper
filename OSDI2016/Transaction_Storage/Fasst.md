#FaSST: Fast, Scalable and Simple Distributed Transactions with Two-sided (RDMA) Datagram RPCs

##Problem
Existing system: One sided RDMA...   FaSST: Two sided RDMA

For the hashing map read.

Two RTT for data trasmission, 1st: read (pointer). 2nd, read(value).  

1 RTT for data transmission

### why One-side RDMA is bad
cannot use lock-free I/O

One side RDMA need connection per pair (too many connections can be bad, NIC cache miss)

One side connection, the corrdination is slower.

## Changes
RPC over RDMA. RPC Involve remote CPU in the message processing, not exclude it

##Trade-off
FaSST is slower than 1 traditional RDMA read. but faster than 2 RDMA reads.

