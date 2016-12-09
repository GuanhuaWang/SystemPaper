#Intermittent Computation without Hardware Support or Programmer Intervention 
##problem
Intermittent computation => write after read (WAR)

##Solution
* Identify WAR
* checkpointing
* optimization => reduce checkpointing times, avoid WAR violation between caller and callee code.

#strength
* WAR(caused by intermittent) correction without hardware modification, or burdening programmer
