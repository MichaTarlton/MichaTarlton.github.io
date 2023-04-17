---
type:  writing/draft
status: active
priority: p1
creationtag: 2022-05-10 12:07
infotags: propsal
---

# 1 Introduction
Working title: Spiking Deep Reinforcement Learning Neural Networks
(or some permutation thereof)

## Deep Reinforcement Learning (DRL)

Reinforcement Learning schemes, learn an optimal policy based on exploration of reward space in an environment with the RL agent optimizing in respect to the parameters of both: *state, action, and reward* in the system. However, in hyperparameterized environments, the learning of optimal policy becomes an intractable problem. In response to this we integrate RL with the field of Deep Learning.

This relatively young subject is expanding and development of new techniques and methods and are still to be explored. The benefits of which would lend themselves to breakthrough applications in Generalized AI, self-teaching and reactive offline systems, robotics, etc.
- we need to expand the field of DRL and DRL methods 
- Why what is the potential?
-  [[@hesselRainbowCombiningImprovements2017-MDnotes]]
	- ![[@hesselRainbowCombiningImprovements2017-MDnotes#Deep Reinforcement learning and RL]] 
### Addendum
Deep SNN methodologies are being effected (see SNUFA paper) however they are not yet being extended to RL (or at least that I have seen). Mostly learning seems to be online and supervised (what’s the difference lol). So methods of DRL in SNN need to be developed. 
- Standard DL models using gradient learning which is not biologically plausible, or usable in SNNs. The closest you can get is [[surrogate gradient learning]] 
- 

## Multi timescales in DRL

Reinforcement Learning is able to adapt to some novel task based on interpretation and optimization of state-action policy optimization in response to a probabilistic reward distribution from the environment.

However in real world applications, unobserved changes in the environment may lead to shifting reward probability distribution masses over time and state-action policies which were optimal at one episode in time, may not be optimal during other episodes. 

Further, maximizing for reward in an immediate smaller time-scale, can mis-optimize for greater rewards at larger timescales, where delayed gratification behavior in smaller time scales can be optimal for return of maximum reward at greater timescales. A local maxima problem in the temporal distribution of reward, if you will.
- optimizing rewards in different time scales to maximize reward at greater time scales
	- Hierarchical, though I don’t think I really want to focus on HRL
	- Somewhat related to multi-objective RL, though the different objectives are in time not objective space

In order to understand, associate, and respond to events and rewards in the environment at different timescales, the system must maintain some concept of “time” in it’s calculations. A number of methods of including this in RL systems have been used. 
- [ Citations needed: 
	- synfire chains, 
	- rolling windows (need more like this of time/memories in conventional systems), 
	- dynamical temporal behavior in RNNs (echos and liquid states)
	-  ]
- System must retain some sense of time in order to “observe” these changes 

Additionally,  shifts in environmental conditions to reward distributions may return to, or take on characteristics of previous states in the environmental conditions, in which case the action policy system of a Reinforcement Learning scheme retaining some trace, or *memory* of optimal policies for those states can improve the overall learning response.
- Returning to old dists
	- Memory
	- Need to roll this back into the RNN memory issue

### Addendum 
- See issues with RNNs and how SNNs can be used to alleviate this
- Probably should bring up RNNs and how they are used for keeping memories
- And then transition to how SNNs can be used to keep multi-timescale information

## The need for Spiking Neural Networks in the DRL context

Spiking Neural Networks (SNNs) represent the field of models that reproduce biologically plausible mechanisms of learning adapted from established concepts in neuronal functioning. The strengths of which are, that we know the brain is capable of many features that we desire to recreate.
- we want to adopt the mechanisms used in the brain, which is capable of all the learning behaviors which we hope to reproduce in silico

Spiking Neural Networks bring with them all the advantages their key features: reactivity, adaptability, efficiency, temporality, and multiplexity.

Because of the sparse analog nature of the an event-driven spiking network, SNNs are reactive and computationally efficient, making them particularly suited for use in energy-efficient neuromorphic hardware, and with robotics applications relying on this hardware, reactivity to novel environmental conditions are key, in addition to the benefit of better energy efficiency.
- Neuromorphics and Robotics
- Need to emphasize the need to capitalize on emergent technologies
- Memresistors make plasticity in hardware more viable and it is a property which will need to be exploited.

By definition of their spiking communication, SNNs directly encode temporal data into their network behavior. At the whole-network level, dynamic temporal behavior arises from recursive network connections, analogous to neural oscillations, discarding reliance on a centralized clock and allowing for and multiplexed information processing in parallel and multiple timescales.
- RNNs
	- Modern RNNs have issues of “catastrophic forgetfulness” 
	- “Typically overspecialized to narrow task domain”
	- “performance on previously learned tasks is diluted”
	- - Prince et al. 2022
	- 
- Temporal learning
- Memory
- Different time scales may be supported through “network phases” analogous to neural oscillations, to what I want to call “echo-states”

At the neuron-to-neuron communication level, multiple dimensions of synaptic learning data can be conveyed through spike timing relationships and spike burst patterns. The well studied biological mechanism of Spike-Timing Dependent Plasticity (STDP) has been used in reproduction of Deep Learning back-propagation techniques for SNNs

These temporal dynamics are what we wish to focus on and study potential models of their contributions to encoding temporal memories and system learning state configurations in SNNs. The project goal being to integrate elements of established  machine learning techniques with the more biologically considered elements of spiking networks to create a model capable of reacting and learning and environment in multiple time-frames: adapting both to an immediate environmental reward space, as well as a generalized adaptation to larger timescales and environmental dynamics.

## The Credit Assignment Problem
- Move the STDP down  here as well as discussion on potential alternate methods


## Heuristics in the field of Spiking DRL NN
- Write a bit about the need for a heuristic by which to test the effectiveness of our model
- See papers which describe the need for new heuritics specific to DL SNNs [Pfeiffer 2018, Prince, SNUFA paper all mention it]
- Using the MNIST on current DL
- What is typically used in RL for testing?



> [!NOTE TO SELF] 
>  Maybe end this whole thing with emphasis on the idea of breaking ground in what is essentially an entirely new field.
>  Entirely aggrandizing.



# 2 Related work

Recent work has been focused on similar questions of both timing and adaptability in SNNs.

## Multiple Time-Scale Dynamics in SNN
- The SNUFA paper  Zenke 2021, talks about this extensively
	- [ ] FORCE Training algo - Nicola and Clopath 2017 #reading 
- [[Voelker & Eliasmith 2018]]
- [[Voelkner 2019]]


## NeoHebbian Deep Learning
- Talk about the challenge with the Credit Assignment Problem in SNNs
- [[Gerstner et al. 2018]]
- [[Payeur et al. 2021]]
	- Point out its implementation of inhibitory microcircuits
	- Isolated Spike and Bursts maintain different meaning, allowing for two information channels
	- Allowing each neuron to have simultaneous feed-forward and feedback error flows
	- 
- [Frémaux and Gerstner, 2016](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B38))
- [ ] Bellac et al. 2020 #reading 
	- Mentioned in the SNUFA paper as offering a bio plausible solution to the spatial credit problem

## Neuromorphic Hardware and SNNs
- More Voelkner and Eliasmith to look at
 - Exploiting new Memresistor hardwares?
 - Loihi, Spinnaker, or Brainscales
 - [[Mehonic 2021]]




# 3 Research Questions
- Can we train DRL models which can learn for different time scales and adapt to changes in the environment 
- Can we encode the memory of different time scales into the “state” of the network
	- That is, can we rely on “in-computation” memory to encode optimal network configurations
- Can we effectively utilize “recurrent-ness” in a network to effect an echo state memory
- Can we effectively utilize properties of spiking networks (and particularly spike timing properties) to…
	-  train the network
		- STDP
	- encode memory into the spiking phases
- Can we build a model which scales


Our model needs to:
	Utilize spike-timing properties in an SNN to train offline to a task defined by a dynamical reward environment. The task environment in which the model network learns, may change over time, and in the response the network must retain a “memory” of previous optimizations to inform future optimizations. 

#  Methods
What I have below may need to put in the "planning" section
## Research, Development, and Benchmarking the Framework 
This stage of the project will consist of the development of a Deep Reinforcement Learning model in a Spiking Neural Network framework. We will build this model up from established methods in SNNs and DRL to create a basic combined model. Using this basic model we can develop a analytic heuristic against which to benchmark descendant models.
- there is need for new benchmarks - Pfeiffer 2018
- Should try to create an insanely basic combinatorial model
	- DQN in SNN?
- Or find an already established one and use that
- Heuristic for an RNN?
	- This is just over the “more than I can chew line” but finding an ideal RNN could be based off a complexity / chaos trade-off measure. Don’t ask me what that means

In establishing a combined model, we can then iterate on the minute mechanics of the model which will be more open to experimentation. This will include the shape of the network architectures, node unit structure and mechanisms, and methods of credit assignment throughout the network.
- Network Architecture
	- Perhaps best to begin with simple feed-forward with back propagation 
	- Recurrent network architectures next
		- Though this may also be implemented on the “nodal” basis. See LMUs.
	- Possible hierarchical structures
		- Global signals such as “dopamine” simulation
		- Because of sparse, low saturation of the network, small world or pseudo-fully connected models may be viable
- Nodal Units
	- This may overlap considerably with methods of credit assignment as STDP type learning is self-contained
	- LMUs
	- Payeur three factor STDP neurons
	- Other timing based units 
	- Honestly designing our own would be dope
		- Though I’m initially inclined towards some STDP + LMU type situation

We will test our iterative models in current conventional software environments, while maintaining the goal of eventual implementation in neuromorphic hardware. Thus we will take steps to ensure our methods can easily be ported to new software environments once a suitable neuromorphic platform option has been decided on, or made available.

Testing a framework for 
- Implementation of SNN with learning
- Implementation of LMUs or other timing network units

## Implementation of Hardware
We will consider and apply for use of available neuromorphic hardware platforms. This decision will need to be informed by the properties of the “production” model we decide to use, and the availability of the hardware. For instance should our model include an STDP driven mechanism, we may prefer use of hardware which natively supports such a feature.
- [[Mehonic 2021]]
	- Perhaps could borrow figure 2 from there. However I would not like for that to be the only figure I use if any.
- using Intel neuromorphic hardware
- Loihi, Spinnaker, or Brainscales
	- Loihi has been used for LMUs
	- STDP in sppinaker and Brainscales
- Exploiting new Memresistor hardwares? 

### Testing Hardware?
Probably comparing our benchmark test for a problem against our novel methods in the chosen hardware platform.


## Potential Collaborations
- Waterloo
- 



# Expected Results
This project will be one of the first projects to explore and establish a new framework of combined Deep Reinforcement Learning in a Spiking Neural Network which can be applied in neuromorphic hardware. This framework will be novel in its ability to exploit the strengths of Deep Learning to guide a Reinforcement Learning problem, as well in its exploitation of a spiking neural network. Further, this project will contribute to the study of temporal dynamics in SNNs, and will develop novel models in multiple aspects of SNN temporal dynamics at multiple timescales. The Reinforcement Learning aspect of this in respect to memory will allow for real-world application in systems which demand reactivity and adaptability to varied tasks over time.



# Research Plan
I have illustrated my progress plan below. My PhD program will extend for four years and I plan to include teaching and supervision during this time in addition to this project. 
