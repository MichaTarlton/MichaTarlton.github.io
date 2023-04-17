---
aliases:
type: project
project: Presenting-Oomman
status: closed
priority: p4
creationtag: 2022-11-04 17:11
infotags:
---
# RL, SNNs, and Representing time
---
### Spiking Neural Networks
- Spiking networks operate the only biomechanical thinking machines we know of
- These are able to efficiently encode information and respond quickly to inputs
### RL
- These biological networks are inherently self organizing 
- making them capable of responding to their environment based on inputs
- as well as plastic: able to adapt to a change in environmental conditions
- both of which are related to RL

### Time Representation
- These networks naturally encode time information in their spiking communication
- A biologically plausible method of Hebbian learning, **Spike-Timing Dependent Plasticity (STDP)** 
	- is dependent on spike-timing to organize the network in response to stimulus
---
### The Three Headed Challenge
- SNNs require new methods of credit assignment 
- RL methods assign credit, but
	- these methods are unexplored for  “deep” networks
	- these methods are unexplored for mechanisms of *[[interval timing]]*

We believe some method requiring elements to self-organize based on reward and properties of time could result in scalable models which are responsive to time and environmental inputs.
---
## Making some Self-Organizing Automata
- There are some some self organizing systems that are capable of representing time in their dynamics
- Such as [[Reservoir Computing|reservoir computers]] known as [[Echo State Networks]]
	- Which store a time delay echo state in their recurrent dynamics
- However these are usually rigid and non-plastic
We would like to adapt some automata model to the problem of time and reward
---
### [[Neural Cellular Automata]]
- There is something called neural cell automata
- This uses a neural network to optimize an automata
- Perhaps something could be done to train a time based automata
<iframe src="https://distill.pub/2020/growing-ca/?ref=https://githubhelp.com" allow="fullscreen" allowfullscreen="" style="height:100%;width:100%; aspect-ratio: 16 / 9; "></iframe>
---
## Target: Biological Models of Time 
- Ideally, any model we create, particularly a bio-inspired one, should match to behavior found in animal studies
### Multiple-timescales
- Animals are able to operate on multiple timescales
- RL can be trained to a single timescale easily
	- Multiple timescales are more difficult

### Animal Trials of Interval Timing
- RL of interval timing exists in animal models 
- [[Interval Timing]]
---
### [[Peak Interval (PI) procedure]]
- [[Interval Timing|Fixed Interval]]
- ![[image-20220630115532239.png]]
- ![[melloScalablePopulationCode2015_44BX6Q7X 1.png]]
### [[Temporal Bisection Task|Temporal Bisection]]
- ![[Temporal Bisection Procedure - 20.06.22#^iupoim]]
---
### Animal models of time representation
- [[Topics - Striatal Beat Frequency model (SBF)]] and [[pacemaker accumulator models (PA)]] are proposed models of time-delay-reward representation in animals
- These propose that multiple oscillatory processes in the brain can encode timing linked with reward based on the phase synchronization of the oscillators at the time of the reward.







```dataview
table rows.file.link AS "Related",
file.ctime as "Created",
infotags as "Tags"
FROM ""
WHERE contains(project,"Presenting to Ooman")
GROUP BY type
SORT file.ctime asc 
```

