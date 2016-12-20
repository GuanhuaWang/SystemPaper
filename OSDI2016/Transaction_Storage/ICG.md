#Incremental Consistency Guarantees For Replicated Objects

##Problem 
there is a dilemma between consistency and latency for geo-distributed data replication query. 

If you want strong consistency, we have high latency & low avaiablity.

If you want low latency, we have low consistency & high avaiability.

However, neither is good.

hybrid introduce difficulty to developers.

##What they do
combining consistency models in a single operation
