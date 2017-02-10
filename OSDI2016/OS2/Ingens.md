#Coordinated and Efficient Huge Page Management with Ingens
##Problem

High address translation cost

##Traditional solution:
Huge pages improve TLB coverage

However, it has high page fault latency, memory bloating etc.

##Ingens
![](ingen.png)

Ingens use asynchronous allocation, the page fault handler only assign base page, and put huge page allocation in background.

##What we can learn the design philosophy
* Reduce Latency => put high latency work into background
