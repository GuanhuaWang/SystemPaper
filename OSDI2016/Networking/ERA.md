#Efficient Network Reachability Analysis using a Succinct Control Plane Representation

## problem

It is not easy to do network verification (e.g. whether A can talk to B or not). 

Reason: new route announcements arrivial , links fails etc.



## Previous work on reasoning control plane for network verification
Bagpipe, rcc, ARC are focus on single or limited set of routing protocol features.

Batfish analysis entire control plane. But it does so by simulating the behavior of each routing protocol to compute the data plane, which is expensive.

##ERA
Efficient reachability analysis

directly reason about the network control plane (no simulation of data plane) , and can be scaled.

1. analysis control plane by learning each router via its neighbors.
2. best routine when multiple routes to the same prefix are learned.

make trade off between expressive and abstraction level.

* a unified protocol-invariant routing abstraction.

* a compact binary decision diagram encoding the routers' control plane.
