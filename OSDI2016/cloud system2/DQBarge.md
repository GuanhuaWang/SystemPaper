#DQBarge: Improving data-quality tradeoffs in large-scale Internet services

##Problem

* Time goal

Low level component unaware of response goal, and may fail.

We want to make data-quality tradoff in a proactive way. That is not need the developer to worry about the time boundary, we can systematic do so.

## DQBarge
1. propagate critical information along the causal path of request processing.

2. Offline stage, it uses the information get previous in step 1, to generate QoS, and proactively detemine which tradeoff to make.

3. generating QoS using a small portion of data.
