---
type: [writing]
status: active
priority: p4
project: Survey Paper/SBF-Model
creationtag: 2022-11-18 09:30
infotags:
people:
date: 2022-11-24
---
Turn into deliverable:  [[Brief Overview of SBF Model]]
# The SBF Model
Starting with [[@yinOscillationCoincidenceDetectionModels2022|B. Yin, Z. Shi, Y. Wang, W.H. Meck (2022)]] as point of orientation.

## The Biological Model
- A central timing network capable of embedding timing in the seconds to minutes range
- This core timing network provides timing pulses (i.e., predictive signals to meaningful stimuli) to the entire brain independent of the temporal-processing context
	- Likewise, distributed satellite timing networks, provide local timing input to task specific regions
	- however for now we will stick to an isolate model
	- but room for growth!

The SBF model posits that at the onset of a ‘to-be-timed’ signal, core neuron populations reset their phase/synchronize and begin oscillating at their endogenous periodicities. 

## The  Basic Model as I understand it
- Coincidence detection observes and event
- This event resets oscillators
	- Some sort of “accumulator” status which records how many oscillations have occurred?
	- Not according to Gu et al. 2015, which uses a  **“phase pattern**” as a timestep instead
	- A reinforcement event occurs and a “memory” neuron “stores” the oscillations which were in phase at that point
- The relation to an RL model is clear
	- to an DRL model, not so clear

## Model Variations
### Basic Model parameters from [[@allmanPathophysiologicalDistortionsTime2012|M.J. Allman, W.H. Meck (2012)]]
Used in [[@yinOscillationCoincidenceDetectionModels2022|B. Yin, Z. Shi, Y. Wang, W.H. Meck (2022)]]
![[@allmanPathophysiologicalDistortionsTime2012#Striatal beat frequency model simulation parameters based on [Matell and Meck (2004)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3491636/ awr210-B152).]]
- Not entirely sure what to do with this. I need to try replicating the simulation.


### [[Excitatory - Inhibitory Oscillation (EIO-SBF)]] Model
Adapted from [[@guOscillatoryMultiplexingNeural2015a|B. Gu, H. van Rijn, W.H. Meck (2015)]]

Quoting Yin:
> Unlike the original STT model, which postulates the accumulation of pacemaker pulses, multi-frequency EIO-based neurons oscillate over time, allowing a unique phase pattern to be observed at any given time (e.g., occurrence of a salient event). 
> 
> The phase pattern is essentially a timestamp, that can be represented by a relatively small number of EIO neurons and easily stored in memory ^[e.g., Gu et al., 2015].

- so instead of using an accumulator to keep track og how many cycles has passed since the start
- Instead use the “phase pattern” to establish a timestamp
- Does this mean if an event aligns at phase 5hz an phase 3hz, then it is at a time of some multiple of those?
	- then it should be more specific with more oscillators in the mix, right?

### Double Summation SBF
- Introduced by the authors here
- I’m not exactly understanding it
- It is fairly fleshed out in [[@yinOscillationCoincidenceDetectionModels2022#Figure 4.|Figure 4 of Yin et al. 2022]]

# Following Questions
## Will this integrate with three-factor STDP?
- [[70 Wiki/topics/Three-Factor Learning Rule|Three-factor STDP]] uses the dopamine signal as a reward learning signal
- It still uses STDP, but does not change the weights until the reward signal is sent
- Instead it “accumulates” the potential weight updates as an [[Eligibility Trace]] until a reward signal is sent
	- Is there a decay on the eligibility signal?
	- Obviously analogous to the pacemaker-accumulator
	- But ideally using the EIO-SBF as the timestamp is not identified by pulse accumulation
- I suggest we use this method to model the SBF in a SNN and task it with timing behavior tasks

## Automata Model
- How are we adapting this to an automata model
- The way Dr. Oomman suggested was to have bots which “wake” at predetermined intervals of time
	- like oscillators
- However what they do, is left in the air
	- I think this may be dependent on the application we set them to
- A mapping of the state-action space is mapped to the  “awake” bots
- Perhaps could be used to test the "timestamp" method
- Need to figure out the distribution of oscillator phases
	- The suggest a gaussian distribution
	- If I can decipher the type of typical brain waves they are using (delta, theta, gamma, etc.) we could use those and then distribue


## What would a model of this look like without oscillation hard resets
- Can’t “hard” reset oscillatory neurons 
	- Indeed an online model, the slate would not be wiped clean at a reset event
	- Instead the oscillators would already be outputting with particular phase only to be delayed or advanced by input signal
	- likewise the downstream neurons will have some learning signal tuned to previous oscillatory conditions
	- Changes made in medias res would have account for this
- So what if we are taking existing oscillators and “delaying” or “advancing” their cycles
- Mapping oscillators to action
	- We may also have some oscillators not affected by the reset signal, which are used to keep reference of another time frame
	- We likely have some centralized oscillator processes along with local and task specific timing populations
- From Yin et al. 2022: ![[@yinOscillationCoincidenceDetectionModels2022#^1rbavu]]


# Misc. Questions
- What is a **Time Base**?
	- The basis of oscillators that make up your naive signalStarter oscillaots
- Chronotropy?
	- Increasing ryhtm 
- Using Ramping activity as secondary indicator of target behavior
- How exactly is the double summation model working?

 

# References and Further reading
- [[@yinOscillationCoincidenceDetectionModels2022|B. Yin, Z. Shi, Y. Wang, W.H. Meck (2022)]]
- [[@guOscillatoryMultiplexingNeural2015a|B. Gu, H. van Rijn, W.H. Meck (2015)]]
- [[@allmanPathophysiologicalDistortionsTime2012|M.J. Allman, W.H. Meck (2012)]]
- [[@tekiPersistenceMemoryHow2017|S. Teki, B. Gu, W.H. Meck (2017)]]
	- Evidence for Oscillatory models in spatio-temporal mapping
	- Proposes the EIO-SBF
	- Talks about mappings between these time cells and grid cells
		- Potential to tie computational models together in the future
		- Look into research done on this front since

- ---
- [[Shi, Z., Gu, B., Glasauer, S., Meck, W. H., (2022)]]. Beyond scalar timing theory: integrating neural oscillators with computational accessibility in memory, Timing Time Percept. (current issue).  
	- A dense read on spatio-temporal dynamics in a binary approximation of a neural network
	- Reading now.


