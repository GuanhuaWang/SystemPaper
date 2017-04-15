# APUNet: Revitalizing GPU as Packet Processing Accelerator

APU reduce the memory copu between GPU and CPU. (Cuz GPU is embeded in CPU)

1. Reduce reduendent GPU launch and tear-down overhead => GPU persistently run threads.   Data synchronization => GPU thread group, thread group 1 process, put data to L2 cache. Thread Group using Dummy Mem I/O to enable GPU L2 Cache to push data to Main memory.

2. Zero-copy .... Traditional: (NIC,CPU using mmap) copy => GPU memory. Now mmap => Shared memory, but still copy.. They direct receive data and keep it in shared memory.

BTW, it is APU that handle the memory copy overhead
