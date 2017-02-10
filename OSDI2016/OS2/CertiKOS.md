#CertiKOS: An Extensible Architecture for Building Certified Concurrent OS Kernels

##problem
There is noe way of verifying the correctness for the concurrency program on OS.

##difficulty on concurrent OS kernel verification
* interleaved execution are interdependent and hard to untangle.
* user I/O muticore are coherently working with each other.
* concurrent kernels not guarantee concurrent system call will return.
* it should be easy to reuse.

##CertiKOS

