---
type: [writing]
status: active
priority: p1
project: Survey Paper/SBF-Model
creationtag: 2022-11-22 09:30
infotags:
people:
date: 2022-11-24
---
For brief outline with further detail see: [[Outline of SBF Model]]
# Model Description
I will start with [[@yinOscillationCoincidenceDetectionModels2022|B. Yin, Z. Shi, Y. Wang, W.H. Meck (2022)]] to orientation our discussion of the [[Topics - Striatal Beat Frequency model (SBF)|Striatal Beat Frequency (SBF) model]] as it provides a terrific and current review of the SBF. The SBF model is a neuroanatomical model, describing the temporal properties of networked cortexes and interneurons. However, I will attempt to describe its properties abstracted from the neural substrate.

The biological SBF is a centralized timing network capable of embedding multiple internal encodings of time intervals within the seconds to minutes range. The centralized core of the network provides timed pulses to downstream reigons. These pulses act as predictive signals of meaningful stimuli. This may also be replicated in more localized regions which are lock to a particular task or timing association. For now we will focus on a single instance, though the potential for scaling a model proves a desirable target for further development.

At the onset of a ‘to-be-timed’ signal (the detection of meanigful stimuli or environmental event), core oscillatory neuron populations reset their phase/synchronize and begin oscillating at their endogenous periodicities. The phase patterns are then "recorded" in relation to some "stop" event given by some reinforcement. In earlier verisions of this model this was attributed to some "accumulator" of the pulses (suggested by some mechanism such as an LIF-neuron), but more recent models suggest the association of a "phase pattern" with the end-stimuli acting as identifiable timestamp ([[@guOscillatoryMultiplexingNeural2015a|Gu et al. 2015]]) .
# Model Variations
The parameters for a basic model of SBF is given in [[@allmanPathophysiologicalDistortionsTime2012#Appendix I|M.J. Allman, W.H. Meck (2012)]], but the model considered in Yin et al. 2022 is an [[Excitatory - Inhibitory Oscillation (EIO-SBF)]] model adapted from [[@guOscillatoryMultiplexingNeural2015a|B. Gu, H. van Rijn, W.H. Meck (2015)]]. Quoting Yin: "Unlike the original STT model, which postulates the accumulation of pacemaker pulses, multi-frequency EIO-based neurons oscillate over time, allowing a unique phase pattern to be observed at any given time (e.g., occurrence of a salient event). The phase pattern is essentially a timestamp, that can be represented by a relatively small number of EIO neurons and easily stored in memory (e.g., Gu et al., 2015)."

So instead of relying on an accumulator to track how many cycles has passed since the starting stimulatory event, a phase pattern is generated from the distribution of phase attenuated oscillators at the time of the end-stimulation. The authors suggest some gaussian distribution of oscillator phaeses based on previous studies, though I am  uncertain exactly as to what phases are actually suggested (as they are given as EEG brain waves: theta, gamma, delta, etc.) or what distributions will follow. See [[@tekiPersistenceMemoryHow2017|S. Teki, B. Gu, W.H. Meck (2017)]].

The authors further introduce a method of coincidence detection for the start stimuli, in what they call **Double-Summation SBF** though exactly how this works is still not clear to me. A brief summary is laid out in [[@yinOscillationCoincidenceDetectionModels2022#Figure 4.|their figure 4 description]].

# Following Questions
## Will this integrate with three-factor STDP?
[[70 Wiki/topics/Three-Factor Learning Rule|Three-factor STDP]], currently the most popular method of credit determination for STDP in SNNs ([[@gerstnerEligibilityTracesPlasticity2018|Gerstner et al. (2018)]]) uses a simulated “dopamine” reward signal to induce learning. Possibly we could use this SNN model to reproduce a SBF network.
## How does this adapt to an automata model? 
The way Dr. Oomman suggested was to have bots which “wake” at predetermined intervals of time and then perform some action accordingly. The direction one would take from here is unclear to me, though I presume it may be task specific. Determining the distribution of the oscillator phases may be more important here.
## What would a model of this look like without oscillation hard resets?
Presumably an already online distributed model would be resistant to “hard reset” events, where already operating phase cycles would only be advanced or delayed. The distribution of a phase on a greater, redundant network population will likely hold the key, as seen with EIO-SBF.
## Miscellaneous Questions
- What is a **Time Base**?
- Chronotropy?
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
- [[@shiScalarTimingTheory2022|Shi, Z., Gu, B., Glasauer, S., Meck, W. H., (2022)]]. Beyond scalar timing theory: integrating neural oscillators with computational accessibility in memory, Timing Time Percept. (current issue).  
	- A dense read on spatio-temporal dynamics in a binary approximation of a neural network
