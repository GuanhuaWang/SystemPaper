#Clarinet: WAN-Aware Optimization for Analytics Queries 

##problem:

Geo-distributed Data Center are hard to do intra-DC queries among all DC of one company in the world.

##solution:

The key latency they claim is the network latency in WAN. It leverage some concept on SDN, which is to have a logical to physical plan abstraction, then it is easy to implement different policy fo the logical layer query optimizer.


Therefore, they did some network aware query placement and scheduling. For exmaple, they tries 
