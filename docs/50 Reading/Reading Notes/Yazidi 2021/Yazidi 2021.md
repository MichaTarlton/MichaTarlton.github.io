---
type:  paper  
---


See [[Yazidi 2021 - Topics]]
See [[Yazidi 2021 - Comments]]

# Introduction
> consider the problem of load balancing (LB)
> 
> a novel stochastic learning automaton (LA) scheme, so as to attain a distribution of the load to a number of nodes, where the performance level at the different nodes is approximately equal and each user experiences approximately the same Quality of the Service
- So the idea is to distribute traffic to nodes by scoring their response time and choosing nodes with higher response time by even distribution of requests

> we prove here that there is a coupling involving LA’s probabilities and the dynamics of the rewards themselves, which renders the environments to be nonstationary
>
>Leads to the emergence of the so-called property of “stochastic diminishing rewards.”
> 
> novel LA algorithm -optimally solves the problem, and this is done by resorting to a two-time-scale-based stochastic learning paradigm. As far as we know, the results presented here are of a pioneering sort, and we are unaware of any comparable results.

> LB are considered NP-Hard problems [31].
See [[Parent 2004]]

> In order to achieve an optimal distribution of workloads to any number of hosts, several algorithms have been developed throughout the years. LB algorithms are mainly classified as being static or dynamic.
- THis one will be dynamic
> The nature of a data center or of a cloud implicitly requires dealing with a mixture of stochastic processes [40]. In contrast to static algorithms, dynamic LB algorithms do not require prior knowledge or configuration of the system.


## A. Distinctive properties of our solution
> 1) By virtue of the “fair balance” paradigm, the learning algorithm initiated by the LA proposed here is distinct from all the families of LA described in the LA-based LB literature, such as in [23]. This includes those from the previously reported families of fixed structure, variable structure, discretized, and estimator-based LA.

> 2) To achieve a fair load balance, we encounter an irony. Thus, it is, indeed, **the fact that the more often an “action” is chosen, the likelihood of the LA choosing it, even more, must subsequently decrease.** In other words, **the rewards that are received for any action must decrease as the action is chosen more frequently.** This is contrary to what the properties of absolute expedience and $\epsilon$-optimality entail, especially since, in these cases, the LA aims to converge to an absorbing barrier in the probability space. To the best of our knowledge, LA that possesses the phenomenon mentioned here has not been proposed in the literature. 

> 3) Our solution is characterized by the amazing property that as any specific pi(t) increases, the corresponding reward probability of the action in question decreases. We refer to this phenomenon as the “stochastic diminishing return property.” Informally, this means that the more an action is chosen, the less it will be rewarded. This involves the two-time-scale LA with barriers, as we shall explain presently, and also facilitates fair LB.

> 4) The analysis methods that we use here are both distinct and unique. 
> 
> The mathematical techniques used for the various families of LA described in the literature are each distinct in their own right. 
> The methodology for the family of fixed structure stochastic automata (FSSA) involves formulating the Markov chain for the LA, computing its equilibrium probabilities, and then computing the asymptotic action selection probabilities. 
> 
> The proofs of convergence for variable structure stochastic automata (VSSAs) involve the theory of small-step Markov processes, distance diminishing operators, and the theory of regular functions. The proofs for discretized LA involve the asymptotic analysis of the Markov chain that represents the LA in the discretized space, whence the total probability of convergence to the various actions is evaluated. The proof of estimator/pursuit algorithms concerns two intertwined phenomena, 
> 
> i.e., the convergence of the reward estimates and the convergence of the action probabilities themselves. The proof methodology considered in this article utilizes the theory of small-step Markov processes and distance diminishing operators, but, unlike the existing LA, they do not converge to absorbing barriers but fixed points in the corresponding probability vector space.

> 5) Historically, the metric for analyzing LA has generally been ep-optimality and absolute expedience. Indeed, the concept of the Lyapunov stability of an LA solution has been rarely used with few exceptions [9]. This is, indeed, the metric that we have invoked.