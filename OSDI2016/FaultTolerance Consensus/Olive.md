#Realizing the fault-tolerance promise of cloud storage using locks with intent

#Problem
In cloud compuation over distributed file system

Application can fail => networking reorder/drop messages in underline storage. 

Lower-level API => Current storage operation can fail.

#Solution
`lock with intent` combine computation with storage operation, using lock

`Intent` code contain cloud storage operation and local computation. It ensure that when a intent complete, each step in the intent execute *exactly once*.

`Lock` provide an `intent` exclusive access to the object. And unlock when the client holding the lock crashes.

*exactly once*: store intent with ID. Introducing DAAL (distributed atomic affinity logging), colocates log entry corresponding to executing an intent step with object changed by that step.

*Concurrent execute same intent* => `Intent Collector` periodically completes unfinished intents.
