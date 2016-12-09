#Machine-aware Atomic Broadcast Trees for Multicores
##background
`SMP`: Symmetric Multi-Processor 

all the cores are equal, and share all resources. 
If multiple requests from differnt cores on RAM => serialize access

`NUMA`: Non-Uniform Memory Access

SMP => limited scalibility (CPU :arrow_up: => conflict in Access MEM :arrow_up:)

NUMA: a group of CPU has shared local MEM. All groups are connected by crossbar.

Shortcoming: latency of remote MEM access is much longer than local MEM access

`MPP`:Massive Parallel Processing

