# IX: A Protected Dataplane Operating System for High Throughput and Low Latency

Contribution 1:

Seperation of data plane and control plane.


Contribution 2:

Execution pipeline between tx and rx.

Adaptive batching:

1. single pkt=> no batching, just process the pkt.

2. pkt queue build-up => Max batching, reduce system overhead.
