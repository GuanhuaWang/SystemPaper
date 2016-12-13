#Graphene: Packing and Dependency-aware Scheduling for Data-Parallel Clusters

##What Graphene do
1. after generation of job DAG, it first group tasks into groups of tasks that are not troublesome. and identifies troublesome tasks. 
2. The scheduler places troublesome tasks first.

# Different from existing schedulers:
Existing: A task is scheduled after all its parents finished

Graphene: identify troublesome tasks first and place them, then place other tasks around the troupble 

# Example of different scheduling
![](graphene_eg.png)
