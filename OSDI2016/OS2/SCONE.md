#SCONE: Secure Linux Container Environments with Intel SGX

##Problem
both cloud provider and users are not trust each other. Previous works on cloud security are heavy and introduce high overhead.

##Design
* Enhanced C library => small TCB
* Asynchronous system call reduce No. of enclave exits
