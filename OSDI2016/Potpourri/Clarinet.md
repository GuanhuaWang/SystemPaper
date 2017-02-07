#Clarinet: WAN-Aware Optimization for Analytics Queries 

##problem:

Geo-distributed Data Center are hard to do intra-DC queries among all DC of one company in the world.

##solution:

The key latency they claim is the network latency in WAN. It leverage some concept on SDN, which is to have a logical to physical plan abstraction, then it is easy to implement different policy fo the logical layer query optimizer.


Therefore, they did some network aware query placement and scheduling. For exmaple, they tries to first schedule queries that happens between two DC with higher network throughput. And late scheduling the queires that both party/DC share low bandwidth.

For iterative jobs, previously people use shortest job first scheudling algorithm to achieve low latency. They find that some links are under-utilized with SJF. Therefore, they try to enable more parallel data communication in the netowrk to achieve overall low lantency among all the DCs.That is to identify k shorest job instead of 1, and then schedule them in parallel.


