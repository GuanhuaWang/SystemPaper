#Slicer: Auto-Sharding for Datacenter Applications
## prblem
Sharding or load balancing is important for data center applications.

We can use local memory for caching data. However, apps on Data center are not using cache.

##slicer
Dynamically sharding workload.

Using small portion of memory on node for building a control plane. It has a centralized sharder on a central node, and do load balancing accordingly by transmiting messages among the slicer control plane within a data center.

##What we learn
Using small portion of memory to do something like cache important information.
