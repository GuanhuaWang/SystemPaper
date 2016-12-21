#NetBricks: Taking the V out of NFV
## Problem 
NFV (network function virtualization) is the new trend compared with hardware-based middle box.

However, NFV introduce a lot system overhead for isolation(e.g. VMs, IPC), which decrease performance (throughput, latency).

Current solution: BESS + container, slow

## solution
NetBricks: single process, low cost.

Zero copy soft isolation(ZCSI): Use unique types to eliminate packet copy, while preserving packet isolation.

Max performance with single core of placing an entire NF chain
