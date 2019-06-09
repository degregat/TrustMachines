# Trust Machines

We seek to implement practical mechanisms for enabling computational trust

## Wilson
### A Self-tuning, Aproximately truthful, practical mechanisms for surplus optimization, via differential privacy.

A trust machine is an agreement over what is to be optimized that is aprroximately dominant strategy and automatically implemented. It tries to created a aproximately truthful mechanism that do not require distributional knowledge about the type  structure of agents beyond that given by the mapping of types to outcome-valuations. The specification of these mappings are then a sufficient way to obtain such a mechanism in executable form.
This is done via a two step mechanism. 1) to use the reported types of agents to simulate their preferences as if those where their true types, and use this to differentially train a model that seeks to maximize a joint objective over surplus maximization and truthfulness deviation advantage minimization 2) run the found objective optimal mechanism with the reported types. 

The advantage a player might derive in deviation from truthfulnes in ways that bias the learned mechanism, 

the objective that is being optimized could be either:
-for profit (when utility is transferable)
-for a given measure of social utility (for example the surplus maximizing stable matching) 


## Binmore: small world mechanisms robustness to a large world
#### Side-effect-free guaranteed via federated learning of the mechanism: the reported types do not leak beyond the chosen outcomes.

The next is to minimize 
Reduces the trust required for the mechanism by probably limiting its side effects.
