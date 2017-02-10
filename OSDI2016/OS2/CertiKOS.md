#CertiKOS: An Extensible Architecture for Building Certified Concurrent OS Kernels

##problem
There is noe way of verifying the correctness for the concurrency program on OS.

##difficulty on concurrent OS kernel verification
* interleaved execution are interdependent and hard to untangle.
* user I/O muticore are coherently working with each other.
* concurrent kernels not guarantee concurrent system call will return.
* it should be easy to reuse.

##CertiKOS
using existing certified method, build a certified abstraction layer like L1 L2 ...etc.

To support concurrency,for each layer L, they parameterize it with an active thread A. we denote EC (L,A) as its environment context.

For each EC(L,A) they use a "e" to capture a specific instance (e.g. one cpu)

In a nutshell, they use existing certified method, and design a layering structure, for each layer it use "e" unit to decribe fine-graied environemnt context of one CPU or thread.
