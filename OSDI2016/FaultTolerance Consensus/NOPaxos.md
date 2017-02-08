#Just Say NO to Paxos Overhead: Replacing Consensus with Network Ordering

Paxos overhead is sequencial copy data (e.g. first leader replica, then second replica, then third). In a asychronous network, this sequencial copy really introduce long delay. As shown in the figure below.

![]sdf
