---
type: writing/draft
status: active
priority: p1
creationtag: 2022-05-12 14:09
infotags: proposal 
---

# 1 Introduction
- write it more like an introduction this time
- The pitch is this:
	- RL DL combos exist
	- DL SNN combos exist
	- By law of communicative properties we need to make a RL DL SNN
## Combining fields at the forefront of machine learning
### Consider the RL you sluggard
- Give a more formal definition of it
- Emphasize the strengths:
	- Unsupervised
	- Adaptable
	- Reactive
	- I.e. more akin to what one would assume of an animal agent
	- Or what one would need out of an agent placed in an unpredictable or changing, environment or task space
- Weaknesses:
	- Don’t necessarily get caught into an attractor, but can be slow to switch from a current S→A policy distribution
	- Large state and action spaces (or even reward) become intractable to compute
		- Insert DL from stage right

Reinforcement Learning (RL) considers some *agent*  acting in an environment, the *state* of the environment informing the agent’s actions to take in interacting with its environment. The goal of RL schemes is optimize its actions in response to environmental states, to maximize some reward input. In this way RL schemes are able to “self-teach” an optimal policy of state-action responses without direct supervision. 

### Deep Learning 
- Can learn for a high-dimension space
- Uses Gradient descent learning, which isn’t really implementable in RL
- Opposite of RL in terms of bio plausible
- Combined with  RL → DQN
	- Spend some time on this
- Maybe just do like the rainbow paper and consider this a RL DL section
- 

### DL and SNNs
- DLs are moving towards using SNNs
	- Why
	- Basically makes this the SNN section
- **SNNs**
	- What they are
		- Keep this to more of an elevator pitch and then let loose in the methods section
	- What they make up for in DL
		- RNNs and memory
		- Temporal dynamics
### Spiking. Deep. Reinforcement. Learning. Neural Networks.
- Gentlemen
~~- Basically this hasn’t been done before~~ 
~~- We get to create a whole new field~~
- This is sorta new territory
- The possibilities for it are vast
- Again emphasize this a new field essentially. I don’t see anything in literature directly referring to it directly. Possibly some stuff within the past 2-3 years but not much more.
- ***A reactive, adaptable, generalizable, fast model, with memory over multiple time scales. A model prepared for implementation in multiple applications.***
	- This is basically the investor pitch though as every model wants to claim this

## Task - Time Representation in Spiking Neural Networks over Multiple Time Scales

### side note: I haven’t really covered snn rl

# Methods
- Possibly combine with Related Work section
## Time Scale Dynamics
### LMUs
### Echo State Networks / Liquid State Networks
- Elicit memory through recurrent network phases 

## Credit Assignment Problem
- STDP
	- Relation to temporal conditions of the network

## Neuromorphic Hardware and SNNs
- More Voelkner and Eliasmith to look at
 - Exploiting new Memresistor hardwares?
 - Loihi, Spinnaker, or Brainscales
 - [[Mehonic 2021]]


# Related Work
## Time scales
- Possibly combine with Methods section
### LMUs
- Implemented in SNNs
- and on Neuromorphic hardware
- further, mention **on-chip learning** so how does that relate to RL?

## Credit Assignment Problem
-  go through SNUFA paper again and reiterate methods
- In the *Linking normative and biologically plausible plasticity models* section 
- **A number of non bio plausible alternatives in this, maybe just say we are picking out some highlights*
### FORCE
- One of the first to address this problem
- 
### Payuer 2021
- Eligibility traces
	- Gerstner 2018
	- Biologicallyplausible but not as favorable in
- The dual channel method may be useful for RL as the learning signals propagate in real time
### Bellec 2020
- Reiterate importance of temporal dynamics

# Research Questions
- Largely unchanged from previous draft

# Research Plan
## Research, Development, and Benchmarking the Framework 
### Establishing Benchmark Heuristics

## Implementation of Hardware

## Potential Collaborations

## Progress plan

# Expected Results




![[Supervision meeting 13.05.22 - Comments on Project Description]]