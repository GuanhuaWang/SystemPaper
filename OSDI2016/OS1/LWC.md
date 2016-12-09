#Light-Weight Contexts: An OS Abstraction for Safety and Performance
##Problem
switching & communication between processes cost a lot (e.g. kernel scheduler, IPC, context-switching)

##Nugget
isolation within a process

##What they do
Decouple memory, privileges from thread, and reuse thread.

*light-weight context*: within a process, maintain isolation of virtual memory mapping, file descriptor bindings etc.

lwc orthogonal to threads. a tread may start lwc a, then switch to lwc b.
