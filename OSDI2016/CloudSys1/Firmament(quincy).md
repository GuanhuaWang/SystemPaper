# Firmament: fast, centralized cluster scheduling at scale

## problem
Centralized scheduler: high quality task placement, latency of seconds or minutes.

Distributed scheduler: high throuput, low lantency, but poor placements.

hybrid scheduler: centralized placement on long-running tasks, distributed placement on short tasks.

## what Firmament can do
* centralized scheduler
* high placement quality (like Quincy)
* sub-second task placement latnecy
* cope with demanding situation (e.g.oversubscription)
## How they did
* relaxation [Relaxation Methods for Minimum Cost Ordinary and Generalized Network Flow Problem] of quincy

1. Terminate Min-cost Max-flow (MCMF) early to find approx. solutions => works bad
2. incremental optimization => acceptable
3.  problem specific heuristics aid

## background
* task by task placement
drawbacks: 1. commits one placement early restricts its choices for further waiting tasks 2. limited opportunity to amortize work

* batrching placement (quincy)
advantage: jointly consider task placement (optimal)

## key finding
Even relaxation has the highest computational complexty, it acturally performance best with least latency.
