#Speculative Execution in a Distributed File System
##Problem
each asynochonous write (e.g. client A) on distributed file system needs two steps: write and commit.

It means two RTT latency. Therefore, we need to reduce it.

If another client (client B) want to open the modified file, it need a getattr RPC (1 RTT).If the file is modified, the new client need to discards its cached data copy and reload the new modified data, which is time consuming

##How to achieve speculative execution
Client A asynchronously executes write and commit RPC, and make them in flight, speculating all modifications are up-to-date.

Client B asynchronously executes getattr, and file speculating its cached copy is up-to-date.


