---
type: reading
status: open
priority: p4
creationtag: 2023-04-11 11:15
infotags:
citekey: petterIntegratingModelsInterval2018
---

Comments:: [[Petter, Gershman, Meck (2018) - comments]]
Topics:: [[Petter, Gershman, Meck (2018) - topics]]
Glossary:: [[Petter, Gershman, Meck (2018) - glossary]]
Citation:: [[@petterIntegratingModelsInterval2018]]

---
# Overall Comments
- The paper is about using RL to do temporal processing
	- More specifically to to do Interval Timing, at multiple time-scales (in the seconds to minutes range)
	- The paper claims to be guided by [[Marr’s three levels of analysis]]
		- I’m not sure if relevant but keeping in mind
- The problem we want to solve for is Interval Timing and Interval Reproduction
	- As illustrated by a traditional Pavlovian Conditioning protocol
	- To flexibly and accurately predict timed actions wrt rewards
- Temporal difference (TD)
	- *Is this* is similar to [[Reward Prediction Error]] in the brain? 
		- looks like they also discuss that elsewhere
		> **The response to the reward itself disappears when the reward is predicted**. But if more than the predicted reward occurs, the dopamine neurons show stronger responses. By contrast, their activity decreases if no, or less than predicted, reward occurs.
	- I believe this could be used to dilate the oscillator intervals if we make them plastic
- When they talk about [[bias-variance trade-off]]
	- So in relation to our time experiment
	- Our “neural circuits”  (oscillating agents. They use the word “neurons”, however this is wrong and it will be more productive to our discussion to call them neural circuits) are narrowly tuned for a particular TI
	- To make up for this we have assigned multiple oscillator agents
	- But to get the most out of our agents, we will want to move them towards a broad tuning (see description as to why)
	- in our regime that means making the agents activate not “narrowly” to their defined oscillator phase, but have some probability of activating “broadly” i.e. within timesteps +/- range of the oscillator cycle
	- Let each oscillator agent phase be a mean with a distribution wrt to the mean of agent activation
	- They suggest in the case of rescaling, allowing the receptive field of a neuron to be gaussian with the variable width and amplitude proportional to its phase tuning, **i.e. Time Cells**. See [[Integrating Models of Interval Timing and Reinforcement Learning - 11.07.22#Figure 1|Fig 1]] 

- They mention the [[Weber's Law|scalar uncertainty of Time Cells aka: Weber's Law]] where variance in timing behavior increases with length of time
	- So perhaps we may want tie oscillator agent activity distribution to the oscillator phase length
	- [[Integrating Models of Interval Timing and Reinforcement Learning - 11.07.22#^mgm7ou|They also indicate]] that this should mean circuits tuned to longer intervals should be limited for favor of tuning to smaller interval durations
- They speak of [[rescaling]], which I believe would mean the tuning of the phase for the neuron(al circuit)
	- Gustavo might know more about rescaling as it is in [[@melloScalablePopulationCode2015]]
	- In our experiment this would mean creating some rule for the oscillator phase to expand or contract 
	- In the case of STDP, we may have our “activate” neuron which fires with some regularity assuming a homeostatic state or stable input. Change in the input, leading to some RPE  may cause the firing frequency of the neuron to increase or decrease, or even precession / antecession of their phase.
- So the part about rescaling [[Integrating Models of Interval Timing and Reinforcement Learning - 11.07.22#^0tkaye|here]] and the part about **[[Integrating Models of Interval Timing and Reinforcement Learning - 11.07.22#^eo7960|clock speed]]** which I fully do not get, check with Gustavo
	- My presumption is that it has to do with phase precession
- They introduce the idea of a global average reward being reported to the system as well as an immediate RPE
	- This is introduced as the difference between phasic and tonic dopamine inputs to neurons
	- Where the tonic input informs as to the global average reward
	- and the phasic input reward reports some RPE
	- Our model is approximating neither atm though it is closest to the phasic type
	- **I believe this is part of a more complex model** 
		- (which I’d like to build at some point, but it is very far away)
		- That is the activity of local oscillator circuits is integrated / averaged at a higher level (i.e. regular brain waves)
		- Which is then fed back to the local oscillator circuits to inform of a “tonic” or global brain time state
		- Currently we are only modeling local circuits with some shared information of the global state via the shared total maximum weight $w_{t}= 1$
		- Which I don’t see a mapping between the previous mentioned model and ours
	- They also posit that the tonic dopamine controls precision (which they call **inverse variance** though I’m not sure what is meant by that) and I’m not sure what to take away from their statement:
	>  Another possibility is that tonic dopamine controls the precision (inverse variance) of sensory measurements [46](https://www.sciencedirect.com/science/article/pii/S1364661318301931?via%3Dihub#bib0230), [47](https://www.sciencedirect.com/science/article/pii/S1364661318301931?via%3Dihub#bib0235), [48](https://www.sciencedirect.com/science/article/pii/S1364661318301931?via%3Dihub#bib0240). This could explain why decreasing tonic dopamine shortens subjective duration relative to physical time: when precision is low, the duration estimate is regularized towards the prior (see below for a discussion of central tendency effects),

 - Rapid and dramatic changes are desired, as seen in the [[Peak Interval (PI) procedure|peak interval preocedure]]
	- Currently we are not seeing that in our model. TBD.
	- According to to the hopper task experiments, animals were able to adapt to changes in reward periods in around 10 trials. We should attempt to observe similar 
	- We may need to create some metric of “settled” behavior for our model
	- I.e. when we believe it has arrived at the “correct” behavior
	- So for a fixed-interval trial, observe what the weight distribution is on the oscillator agents at some defined “correctness” and then compare in a mixed-interval trial what
- Averaging or integrating of intervals. They quote a task where an animal was habituated to two different stimuli, each corresponding to either a short or long stimuli. When exposed to both simultaneously, the animal was able to take an average of the two
	- This would indicate that internal models of time intervals are not isolate, but can be integrated together when appropriately prompted
	- So this does not track as easily to our current experiment as it relies on a particular input set, but it suggests work on a model where associations should be drawn between established intervals
	- Say we have “attention” weights between oscillator agents
	- So that activation probability increases wrt to weight between two oscillators
	- this could be co-activation as in our model, or some rescaling between the two oscillator phases
	- Curious to try to find methods of doing this
- Need to check all the methods of timing integration [[Integrating Models of Interval Timing and Reinforcement Learning - 11.07.22#^592cn4|here]]
- They basically come to the conclusion that internal timing is flexible, so whoop?
- **Belief States**: the decay of confidence in trained interval time, with increasing RPE
	- So say the RP changes, a “Belief State” or state of uncertainty is increases with increasing accumulation of RPE
	- Perhaps in our model this would be some control parameter which decides how quickly or how slowly learning can occur with reward to prediction ratio
	- Say increasing pull to reward ratio decreases exploration, 
		- Declining PtR ratio increases momentum of learning on oscillators with less weight
		- inversely proportions learning to weight value
	- How does this relate to [[Eligibility Trace|Eligibility Traces]] in [[Three-Factor Learning]]?
- Not certain what to make of the **structure Learning** section, other than previous state information must be incorporated into future actions
- They get into bayesian 

## Tasks
They mention several tasks, of which I’ll keep track here.
They talk about the expected behaviors elicited from animals in these tasks, which we should expect to observe and reproduce with our models.
I’m not sure I have the time to catalog all of these here and now, before I [[Presenting on Petter 2018|present]].

- two-interval reproduction task [\[39\]](https://www.sciencedirect.com/science/article/pii/S1364661318301931?via%3Dihub#bib0195).
- hopper-switch task [52](https://www.sciencedirect.com/science/article/pii/S1364661318301931?via%3Dihub#bib0260), [53](https://www.sciencedirect.com/science/article/pii/S1364661318301931?via%3Dihub#bib0265), [54](https://www.sciencedirect.com/science/article/pii/S1364661318301931?via%3Dihub#bib0270) 
	- two-hopper task variant
- Pavlovian conditioning task with random ISIs ([Figure 2](https://www.sciencedirect.com/science/article/pii/S1364661318301931?via%3Dihub#fig0010))
- Pavlovian delay conditioning experiments [\[51\]](https://www.sciencedirect.com/science/article/pii/S1364661318301931?via%3Dihub#bib0255).
- temporal reproduction task  [\[70\]](https://www.sciencedirect.com/science/article/pii/S1364661318301931?via%3Dihub#bib0350) 
- “generalizing a previously learned duration across stimulus modality, location, and task demands”
- Temporal bisection procedure
- Fixed-Interval procedure
- Peak-interval procedure
- Untitled task where stimuli corresponding to different interval times were averaged by the animal  [\[56\]](https://www.sciencedirect.com/science/article/pii/S1364661318301931?via%3Dihub#bib0280)
- See tasks focused on timing integration and flexibility [[Integrating Models of Interval Timing and Reinforcement Learning - 11.07.22#^592cn4|here]] 
	- They sort of lump a bunch in