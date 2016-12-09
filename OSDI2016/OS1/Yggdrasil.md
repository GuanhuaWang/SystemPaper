#Push-Button Verification of File Systems via Crash Refinement

##Problem

File system verfication is hard to prove (takes manually in years)
=> Yggdrasil produce a counter example if there is a bug. No need proof.

##How it works
`Crash Refinement`: capture non-determinism bugs (e.g. reordering of writes)
`Crash Refinement` is achieved by a *satisfiablility modulo theories* (SMT) solver (Z3).
To make SMT a push-button solution => *layering*
exhausting all execution path within a layer, avoiding path explosion between layers.

##How to use it
input: `specification` , `implementation`,`consistency invariants`
Yggdrasil varify it.
If (pass): compile
else(fail): visualizer => counter example

##Strength
* counter-example based debugging is better than Proof
