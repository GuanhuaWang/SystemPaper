#FaSST: Fast, Scalable and Simple Distributed Transactions with Two-sided (RDMA) Datagram RPCs

##Problem
Existing system: One sided RDMA...   FaSST: Two sided RDMA

For the hashing map read.

Two RTT for data trasmission, 1st: read (pointer). 2nd, read(value).  

1 RTT for data transmission

## Changes
RPC over RDMA. RPC Involve remote CPU in the message processing, not exclude it

