---
type: lecture
status: open
priority: p1
project: "MLSS^N 2022 Krakow"
creationtag: 2022-08-03 16:34
infotags: [biological learning, continual learning, RL, predictive coding, springs]
people: "Rafal Bogcaz"
date:
---
# Materials
[MLSS^N Day 1 - 27.06.2022 - YouTube](https://youtu.be/N447XbErsGE?t=22212)
![[Krakow_summer.pptx]]


# Notes
- UKRI - Brain Network Dynamics Unit
- Generative model of the world
	- Relying on local computations
	- and local plasticity

 Developments
- See slide of papers, list
- [ ] Wittington \& Bogacz 2017 "Approx BP" #rd 
- Prospective config 2022
	- Alt credit asszynment

- [ ] Model for unsupervised learning in visual cortex - Rao & Ballard (1999) #rd #p3
- [ ] General framework for describing brain function - Friston (2010) #rd #p3
- [ ] Approximates backpropagation - Whittington & Bogacz (2017) #rd #p1
- [ ] Distinct learning principle: prospective configuration - Song et al. (2022) #rd #p1
	- Alternative credit assignment
	- literally can’t find this
- 

Prospective Config
- [ ] Predictive Coding (PC) #tp
- [ ] Reduced Interference (RI) #tp
So you can cause collateral damage in a fully connected model.
i.e. destroy a common path used by another

PC: looks af total config, tries to avoid error from $R I$ even str connection on other connection
- [ ] Energy machine #tp
This sounds similar to something I've seen before...
Neuron activity and weights are not directly "attached"

Nodes let the activity converge (Relaxation) and then adiust weights to mimimize evievgy
ie. "energy in springs"

Neural Implementation

# Salmon Problem
- Spring distance is analonous to prediction evrov

# sim
- not sure how big a difference there is in how it $\mathrm{BPs}$, the error. Does it go all at once?

Q. How big are the steps

# Target Alignment

Note:
It kinda averages over all error?
Or because the tensor is through multiple layers?

# with larger nets
Q: why did you use linear activation fnc?
a: Simplicity

# Fashion MNIST
Train without batches

# Limited Traing Set
- Last few slides have just been performance graphs

# Concept Drifting
Continual & Reinforcement learning
$Q$ : Why is the Variance higher in the perf of the $P C$ (It is high )
A: Doesh't know
$Q:$ missed this one
Q: Dropout? Network Modification



Q: Key problem? what lid he say?
Somethins about speed?
A: “It is slower." wait how is it local, he has to go through multiple layers. to be local it has to he able to uplate all neurous at once.
$Q:$ Adversarial attacks?
A: "can only "speculate"
Q: Bio plausibility
A: "Natural spicing interpretation"
- [ ] Boer lin et al. 2013 #reading #P2

# Inference of latent state

Inference during motor learning

# BP Algo
Ok this misht explain the diff
# Energy machine
$\hat{x}$ : predictive activity
i: current layer
y: Previous layer
# Node Dynamics

$$
\begin{aligned}
&\dot{x}_{i}^{(l)}=\frac{-\partial}{\partial x_{i}^{(l)}} \frac{1}{2}\left[_{i j} x_{i}^{(t)} - \sum_{\hat{j}} v_{i, j}^{(l-1)} f\left(x_{j}^{(l-1)}\right)\right]^{2}
\\
&=-\frac{1}{2}(2)\left(x_{i}^{(l)}-\sum_{j} v_{ij}^{(1-j)} f\left(x_{j}^{(l-1)}\right)\right)
\\
&+\sum_{j} x_{i}^{(l+1)}-\sum_{i} v_{i j}^{(l)} f\left(x^{(l)}\right) \quad v_{i j}^{2} f^{\prime}\left(x_{j}^{(l)}\right)
\\
&\dot{x}_{i}^{l}=-\varepsilon_{i}^{l}+f^{\prime}\left(x_{i}^{l}\right) \sum_{i} v_{i, i}^{l} \varepsilon_{i}^{(l+1)}
\end{aligned}
$$

# Predictive Coding network
See list of reading

# Local Plasticity
uses hebbian

# Error in output layer

# feature not a bug
- [ ] Inferring Neural activity..." - Song et al. 2022 #reading
- [ ] Equilibrium prop #tp
Avoiding Neural  activity shift


## plasticity - stability
others see lit.
can be used together.y

![[image-20220803180404137.png]]

![[image-20220803180421042.png]]

![[Notepad7.pdf]]