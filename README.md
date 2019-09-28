# Towards trust-minimized learning mechanisms

Practical automated mechanisms for enabling computational trust, requiring only a mapping from agent types to utilities

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


#### Notes

We used TensorFlow Privacy to make the RegretNet approach of [Optimal Auctions through Deep Learning](https://github.com/saisrivatsan/deep-opt-auctions) Differentially Private (DP), resulting in Approximate Truthfulness and Collusion Resistance in the sense of “Mechanism Design via Differential Privacy" (Frank McSherry and Kunal Talwar, In FOCS, pages 94–103, 2007). This means we can relax the assumption of having prior knowledge of the valuation profiles.
   
You can find the code here:
https://github.com/degregat/deep-opt-auctions/

And examples here:
https://github.com/degregat/deep-opt-auctions#examples

(Implementation: The lagrange_update in our fork is differentially private, bounding the rate of change of the lagrange multipliers on the regret per agent. Therefore, the influence each agent has on the resulting allocation and payment functions is bounded.)

In the next steps we want to minimize the trust needed in the execution of the mechanism. 

We are currently porting the DP fork to a Federated Learner with Multiparty Computation (MPC) using tf-encrypted. This way, the gradient updates from locally DP models will be aggregated confidentially, subject to the constraints of the MPC. This will already increase the privacy budget for many useful cases. It also reduces the trust needed by the agents in the aggregator.

The next improvement will be to use a differentially private learner in the trusted curator model on MPC. Since this distributes the DP mechanism, trust in individual agents to apply it correctly can be reduced. Also, the trusted curator setup provides better robustness/accuracy tradeoffs.
