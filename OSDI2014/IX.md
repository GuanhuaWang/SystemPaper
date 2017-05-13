# IX: A Protected Dataplane Operating System for High Throughput and Low Latency

Seperation of data plane and control plane.

Adaptive batching:

1. single pkt=> no batching, just process the pkt.

2. pkt queue build-up => Max batching, reduce system overhead.
