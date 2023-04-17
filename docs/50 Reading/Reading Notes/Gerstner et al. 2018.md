---
type: reading
citekey: gerstnerEligibilityTracesPlasticity2018
status: open
priority: p4
creationtag: 2022-09-20 09:58
infotags: [Three-Factor Learning Rule, Three-Factor, Three-Factor Learning, Three-Factor Hebbian Learning, Neo-Hebbian Learning,]
---
[[@gerstnerEligibilityTracesPlasticity2018]]
# Gerstner et al. 2018

Add md note link when you have it
> In the following, we—a group of theoreticians—review five experimental papers indicating support of eligibility traces in striatum ([Yagishita et al., 2014](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B155)), cortex ([He et al., 2015](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B54)), and hippocampus ([Brzosko et al., 2015](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B20), [2017](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B21); [Bittner et al., 2017](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B11)). We will close with a few remarks on the paradoxical nature of theoretical predictions in the field of computational neuroscience.


> From the theoretical perspective, STDP under the control of neuromodulators leads to the framework of three-factor learning rules ([Xie and Seung, 2004](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B154); [Legenstein et al., 2008](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B70); [Vasilaki et al., 2009](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B150)) where an eligibility trace represents the Hebbian idea of co-activation of pre- and postsynaptic neurons ([Hebb, 1949](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B55)) while modulation of plasticity by additional gating signals is represented generically by a “third factor” ([Crow, 1968](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B27); [Barto, 1985](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B6); [Legenstein et al., 2008](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B70)). Such a third factor could represent variables such as “reward minus expected reward” ([Williams, 1992](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B152); [Schultz, 1998](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B122); [Sutton and Barto, 1998](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B142)) or the saliency of an unexpected event ([Ljunberg et al., 1992](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B79); [Redgrave and Gurney, 2006](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B106)).

> **synaptic strength $w_{ij}$,** 
> measured as spine volume or amplitude of postsynaptic potential, 
> 
> **synapse-internal variable** $e_{ij}$ 
> which is not directly visible in standard electrophysiological experiments.
> 
> The internal variable $e_{ij}$ represents a metastable transient state of interacting molecules in the spine head or a multi-molecular substructure in the postsynaptic density which serves as a synaptic flag indicating that the synapse is ready for an increase or decrease of its spine volume ([Bosch et al., 2014](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B15)).
> 
> The precise biological nature of $e_{ij}$ is not important to understand the theories and experiments that are reviewed below. 
> 
> ***We refer to $e_{ij}$ as the “synaptic flag” or the “eligibility trace”*** 
> and to $w_{ij}$ as the “synaptic weight,” or “strength” of the synaptic contact. A change of the synaptic flag indicates a ‘candidate weight change’ ([Frémaux et al., 2010](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B39)) whereas a change of $w_{ij}$ indicates an actual, measurable, change of the synaptic weight. Before we turn to three-factor rules, let us discuss conventional models of Hebbian learning.
> 
> **the synaptic flag variable _e__ij_ is sensitive to the _combination_ of presynaptic spike arrival and a postsynaptic variable, such as the voltage at the location of the synapse.**
> 
> 
> repeated presynaptic spike arrivals at a synapse of a neuron at rest do not cause a change of the synaptic variable.
> 
> Similarly, an elevated postsynaptic potential in the absence of a presynaptic spike does not cause a change of the synaptic variable

_So there is a window! It should be center relative to PSNF (post-synaptic neuron firing) and outside that window PRN activity is null._
## Hebbian
> Hebbian learning always needs two factors for a synaptic change: a factor caused by a presynaptic signal such as glutamate; and a factor that depends on the state of the postsynaptic neuron.
> 
> We can think of the presynaptic factor as the time course of glutamate available in the synaptic cleft or bound to the postsynaptic membrane.


> According to Equation 1 the synaptic flag _e__ij_ acts as a _correlation detector_ between presynaptic activity _x__j_ and the state of the postsynaptic neuron _y__i_. In some models, there is no decay or the decay is considered negligible on the time scale of one experiment (τ_e_ → ∞).

Skipping over the other models like Clopath

> To summarize, in the theoretical literature the class of Hebbian models is a rather general framework encompassing all those models that are driven by a combination of presynaptic activity and the state of the postsynaptic neuron. In this view, Hebbian models depend on two factors related to the activity of the presynaptic and the state of the postsynaptic neuron. The correlations between the two factors can be extracted on different time scales using one or, if necessary, several flag variables. The flag variables trigger a change of the measured synaptic weight. In the following we build on Hebbian learning, but extend the theoretical framework to include a third factor.


## Three Factor Learning Rules
The more modern Idea
> We are interested in a framework where a Hebbian co-activation of two neurons leaves one or several flags (eligibility trace) at the synapse connecting these neurons. The flag is not directly visible and does not automatically trigger a change of the synaptic weight. An actual weight change is implemented only if a third signal, e.g., a phasic increase of neuromodulator activity or an additional input (signaling the occurrence of a special event) is present at the same time or in the near future.

> The basic idea of a modern eligibility trace is that a synaptic flag variable _e__ij_ is set according to Equation (1) by coincidences between presynaptic activity _x__j_ and a postsynaptic factor _y__i_. The update of the synaptic weight _w__ij_, as measured via the spine volume or the amplitude of the excitatory postsynaptic potential (EPSP), is given by **EQ. 2**

> In Equation 2, a non-zero third factor is needed to transform the eligibility trace into a weight change; cf. Figure [1Aiii](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#F1). Note that the weight change is proportional to $M^{3rd}$(_t_). Thus, the third factor influences the speed of learning. In the absence of the third factor ($M^{3rd}$(_t_) = 0), the synaptic weight is not changed. We emphasize that a positive value of the synaptic flag in combination with a negative value $M^{3rd}$ < 0 leads to a decrease of the weight. Therefore, the third factor also influences the _direction_ of change.

> In the discussion so far, $M^{3rd}$(_t_) in Equation (2) can take positive and negative values. Such a behavior is typical for a phasic signal which we may mathematically define as the deviation from a running average. We may, for example, think of the third factor as a phasic neuromodulatory signal. However, the third factor could also be biologically implemented by _positive_ excursions of the activity using two different neuromodulators with very low baseline activity. The activity of the first modulator could indicate positive values of the third factor and that of the second modulator negative ones - similar to ON and OFF cells in the retina. Similarly, the framework of neoHebbian three-factor rules is general enough to enable biological implementations with separate eligibility traces for LTP and LTD as discussed above in the context of the Clopath model ([Clopath et al., 2010](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B24)).

Skipping over eq 3 and type 2 three-factor

> One of the important differences between supervised and reinforcement learning is that in most modern supervised learning tasks, such as auto-encoders, the target is, just like the input, a high-dimensional vector. For supervised learning of high-dimensional targets, we need to generalize Equation (3) further, to three-factor learning rules of Type 3,

> Equation 4: $$\frac{d}{dt}w_{ij}=e_{ij}M^{3rd}_i(t)  $$
> where $M^{3rd}_i$ is now a neuron-specific (hence non-global) error feedback signal. For the case of standard backpropagation in layered networks, $M^{3rd}_i$ is calculated by a weighted sum over the errors in the next layer closer to the output; a calculation which needs a well-tuned feedback circuit from the output back to previous layers ([Roelfsema and van Ooyen, 2005](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B112); [Lillicrap et al., 2016](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B72); [Roelfsema and Holtmaat, 2018](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B111)). Interestingly, learning similar, but not identical, to backpropagation is still possible with feedback circuits, where the direct feedback from the output is replaced with fixed random weights ([Lillicrap et al., 2016](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B72); [Guerguiev et al., 2017](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B51)), or in networks with a single hidden layer and winner-take-all activity (one-hot coding) in the output layer ([Roelfsema and van Ooyen, 2005](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B112); [Rombouts et al., 2015](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B115)). In the latter case, the neuron-specific third factor $M^{3rd}_i$ further factorizes into a global modulator $M^{3rd}$ and an attention signal $A_i$, which leads to a four-factor learning rule ([Roelfsema and Holtmaat, 2018](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B111)).


## Reward-based Learning
> As a first example of a Type 1 three-factor learning rule, we consider the relation of neoHebbian three-factor rules to reward-based learning. Temporal Difference (TD) algorithms such as SARSA(λ) or TD(λ) from the theory of reinforcement learning ([Sutton and Barto, 1998](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B142)) as well as learning rules derived from policy gradient theories ([Williams, 1992](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B152)) can be interpreted in neuronal networks in terms of neoHebbian three-factor learning rules. 
> 
> The resulting plasticity rules are applied to synapses connecting “state-neurons” (e.g., place cells coding for the current location of an animal) to “action neurons” e.g., cells initiating an action program such as “turn left”) 
> 
> ([Brown and Sharp, 1995](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B19); [Suri and Schultz, 1999](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B140); [Arleo and Gerstner, 2000](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B1); [Foster et al., 2000](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B37); [Xie and Seung, 2004](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B154); [Loewenstein and Seung, 2006](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B80); [Florian, 2007](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B36); [Izhikevich, 2007](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B62); [Legenstein et al., 2008](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B70); [Vasilaki et al., 2009](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B150); [Frémaux et al., 2013](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B40)); for a review, see ([Frémaux and Gerstner, 2016](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B38)).

> The eligibility trace is increased during the joint activation of “state-neurons” and “action-neurons” and decays exponentially thereafter consistent with the framework of Equation (1). The third factor is defined as reward minus expected reward where the exact definition of expected reward depends on the implementation details. A long line of research by Wolfram Schultz and colleagues ([Schultz et al., 1997](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B124); [Schultz, 1998](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B122), [2002](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B123); [Schultz and Dickinson, 2000](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B125)) indicates that phasic increases of the neuromodulator dopamine have the necessary properties required for a third factor in the theoretical framework of reinforcement learning.

> However, despite the rich literature on dopamine and reward-based learning accumulated during the last 25 years, there is scant data on the decay time constant τ_e_ of the eligibility trace _e__ij_ in Equation (1) before 2015 (except the locusts study [Cassenaer and Laurent, 2012](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B23)). 
> 
> From the mathematical framework of neoHebbian three-factor rules it is clear that, in the context of action learning, the time constant of the eligibility trace (i.e., the duration of the synaptic flag) should roughly match the time span from the initiation of an action to the delivery of reward.

> **_the existing theory of three-factor learning rules predicts that the synaptic flag (eligibility trace for action learning) should be in the range of a typical elementary action, about 200 ms to 2 s_;**

See the example they give for as to why.
Perhaps a good time frame to use when choosing bins or bins within bins

## Surprise-Based Learning
>  Even in the absence of reward, a surprising event might trigger a combination of neuromodulators such as noradrenaline, acetylcholine and dopamine that may act as third factor for synaptic plasticity.

> If surprise can play a role similar to reward, then surprise-transmitting broadcast signals should speed-up plasticity. Indeed, theories of surprise as well as hierarchical Bayesian models predict a faster change of model parameters for surprising stimuli than for known ones ([Yu and Dayan, 2005](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B156); [Nassar et al., 2010](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B96); [Mathys et al., 2011](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B85), [2014](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B86); [Faraji et al., 2018](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B33)) similar to, but more general than, the well-known Kalman filters ([Kalman, 1960](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B65)).



## Policy Gradient vs. TD-learning

> Algorithmic models of TD-learning with discrete states and in discrete time do not need eligibility traces that extend beyond one time step ([Sutton and Barto, 1998](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B142)). In a scenario where the only reward is given in a target state that is several action steps away from the initial state, reward information shifts, over multiple trials, from the target state backwards, even if the one-step eligibility trace connects only one state to the next ([Sutton and Barto, 1998](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B142)).

> Nevertheless, extended eligibility traces across multiple time steps are considered convenient heuristic tools to speed up learning in temporal difference algorithms such as _TD_(λ) or SARSA(λ) ([Singh and Sutton, 1996](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B134); [Sutton and Barto, 1998](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B142)).