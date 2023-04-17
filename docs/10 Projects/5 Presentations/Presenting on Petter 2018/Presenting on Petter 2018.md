---
aliases:
type: project, presentation
project: Presenting on Petter 2018
status: open
priority: p4
creationtag: 2023-04-12 11:22
infotags: presentation
citekey: petterIntegratingModelsInterval2018
---

```dataview
table rows.file.link AS "Related",
file.ctime as "Created",
infotags as "Tags"
FROM ""
WHERE contains(project,"Presenting on Petter 2018")
OR contains(citekey,"petterIntegratingModelsInterval2018")
GROUP BY type
SORT file.ctime asc 
```

# Goals


# Slides

## Petter et al. 2018
[[Petter 2018 Slides - Draft 1]]
[[Petter 2018 Slides - Draft 2]]

## Summary
- Covers several animal experiments which test “Interval Timing (IT)”
- Explains the observed animal behavior in these experiments and response to reinforced stimulus
- Draws comparisons against RL methods

## Interval Timing Experiments
Conditioned Stimulus (CS): Stimulus which animal is conditioned to associate with
Unconditioned Stimulus (US): The reward or some unexpected stimulus
Interstimulus Interval (ISI): Interval of time between CS and US

Intertrial Interval (ITI): Interval of time between trials of CS and US

Pavlovian Conditioning Experiments
#### Figure 1b
![[image-20230417085734402.png]]
> Figure 1. Predicting Reward with Temporal Representations. 
> **(A)** Learning to anticipate a reward that follows a predictive cue can be accomplished by using a set of ‘microstimulus’ representations (temporal basis functions; see [24,25]). 
> 
> **(B)** These basis functions are activated by salient events (e.g., a tone signaling trial start), and peak at a characteristic delay from event onset. They have the benefit of naturally allowing for generalization of value across time. 
> 
> Specifically, the overlapping nature of the basis functions allows partial credit when rewards are received at times of less than maximal activation. Here the width of each basis function scales in proportion to its preferred duration, thus increasing the amount of generalization with longer durations. ISI, interstimulus interval; ITI, intertrial interval.



## TD & RPE
Temporal Difference and Reward Prediction Error
- Making reinforcements of predicted intervals based on the time elapsed between action and time reward is issued (TD)
- Is this similar to how RPE works?
	- Exists in dopaminergic neurons where reward that is predicted:
		- Increases dopa activity w/ greater reward
		- Activity stays constant with reward of similar value
		- Lack of reward at prediction leads to decrease in dopamine neuron activity
	- This is lovely as it basically has a built in decay / max function
- Currently we do not have something like this in ours
- If we made the oscillator agents more plastic, ie able to *rescale* their cycle length (or other properties)
**Illustration:** See figure 5 from [[2016 Schultz NRN+suppl.pdf|Schultz 2016]] 
![[image-20230417084207134.png]]



## Neurons and Oscillators
- It may be important to define at this point how they use the word “neuron” when talking about Time Cells
	- While a single neuron, like a Time Cell or Grid Cell, might fire in response to some event, it is actually the downstream output of computation done by some circuit of neurons
	- It is more accurate to call them then **neuronal circuits**, however this is can be 
	- This is reflected in our automata design where the actor automata is informed by a circuit of oscillator neurons, which are likewise the output of circuits which maintain some “oscillatory” status
	- The structure of these oscillatory circuits, from spiking neurons to circuits with oscillating activity, will be a discussion to be had. Especially to design around the pliable properties of the rescaling perceptive fields
#### Figure 2. Yin et al. 2022: Striatal-beat-frequency model of reward-based timing
![[image-20230417092955099.png]]
![[@yinOscillationCoincidenceDetectionModels2022#^tz9ijz]]

![[@yinOscillationCoincidenceDetectionModels2022#^prz9jm]]

## Bias-Variance trade off
- ok so with that in mind, they speak about a [[bias-variance trade-off]] in Time Cells 
- Where the receptive field for a Time Cell which is “tuned” for a particular interval of time
	- an obvious analog for our oscillator agents
- However in the biological regime the Time Cells are capable changing their tuning
- They are able to change the tuning of their receptive field, that is the range around the interval at which they activate
	- Which is a Gaussian distribution of activation
	- Where the mean is the is the length of the encoded interval
	- And the variance of the distribution is the noise
	- In according with Weber’s law, the variable width and amplitude is proportional to the phase tuning
		- Ie the chance for variation of the interval increases with the length of the time interval
		- As it is not very useful to have precise encoding for larger time scales
		- (find citation)
		- They also suggest the distribution of oscillation circuits should be tuned towards shorter cycle lengths than longer ones
	- This variance can be narrowly or broadly tuned so that the cells activate with a narrow “bias” or a broader variance for exploration 
	- 
- You can say our oscillators are narrowly tuned with no noise
- What if we added receptor fields to our model
	- First with static fields
	- Then with plastic fields, how would we manipulate the distribution
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
#### Figure 1.
![[image-20230417090216248.png]]
> Figure 1. Predicting Reward with Temporal Representations. 
> **(A)** Learning to anticipate a reward that follows a predictive cue can be accomplished by using a set of ‘microstimulus’ representations (temporal basis functions; see [24,25]). 
> 
> **(B)** These basis functions are activated by salient events (e.g., a tone signaling trial start), and peak at a characteristic delay from event onset. They have the benefit of naturally allowing for generalization of value across time. 
> 
> Specifically, the overlapping nature of the basis functions allows partial credit when rewards are received at times of less than maximal activation. Here the width of each basis function scales in proportion to its preferred duration, thus increasing the amount of generalization with longer durations. ISI, interstimulus interval; ITI, intertrial interval.


## Rescaling
- They suggest rescaling, that these receptive fields are pliable to change with the TD
	- I’m hoping Gustavo knows more about Rescaling as it is his 2015 paper 
	- Reading the excerpt from the paper about, I have no idea what it means
	- Is this referring to the expanding and contracting as well as the precessing and recessing of the phase
	- **Illustrate:** Visual explanation of phase rescaling
- They also comment on the ability for neurons to rescale quickly and flexibly [[Integrating Models of Interval Timing and Reinforcement Learning - 11.07.22#^0tkaye|here]]
- How do we rescale for an STDP neuron?

**Illustration:** Display this excerpt: ![[Integrating Models of Interval Timing and Reinforcement Learning - 11.07.22#^eo7960]] Because I have no idea what it means

## Reward Prediction Error
- They discuss the tonic and phasic dopamine inputs to the neurons
- Where the tonic activity represents some global average reward
- And the phasic activity controls the “precision” or that is a more local RPE
- The closest thing our current model does it take an average value across intervals of how close they are to the target one
- **I think this may inform a more complex model**
	- That is the activity of local oscillator circuits is integrated / averaged at a higher level (i.e. regular brain waves)
		- Which is then fed back to the local oscillator circuits to inform of a global brain time state
		- This done across multiple scales
		- Currently we are only modeling local circuits with some shared information of the global state via the shared total maximum weight $w_{t}= 1$
		- Which I don’t see a mapping between the previous mentioned model and ours


## Belief States
- **Belief States**: the decay of confidence in trained interval time, with increasing RPE
	- So say the RP changes, a “Belief State” or state of uncertainty is increases with increasing accumulation of RPE
	- Perhaps in our model this would be some control parameter which decides how quickly or how slowly learning can occur with reward to prediction ratio
	- Say increasing pull to reward ratio decreases exploration, 
		- Declining PtR ratio increases momentum of learning on oscillators with less weight
		- inversely proportions learning to weight value
	- How does this relate to [[Eligibility Trace|Eligibility Traces]] in [[Three-Factor Learning]]?
###### Figure 2
![[image-20230417084451821.png]]

> Interactions between interval timing and belief states (probability distributions over states) can be understood through a comparison of Pavlovian tasks with and without state uncertainty. 
> 
> When a reward follows a tone with 100% probability **(A),** the animal always knows that it is in the interstimulus interval (ISI) state before reward [p(ITI) = 1] and in the intertrial interval (ITI) state after reward [p(ITI) = 0]. 
> 
> As time progresses in the ISI state, the reward becomes more likely, and subjects are less surprised when it is delivered. This corresponds to a monotonic decline in the dopamine reward prediction error signal as a function of ISI (Starkweather et al. [5,6]). 
> 
> When rewards are occasionally omitted **(B),** subjects have uncertainty about whether they are in the ISI or the ITI state. This uncertainty can be captured by a dynamic belief state. As time progresses without a reward, subjects become increasingly confident that the state has silently transitioned to the ITI, and thus their reward expectations will eventually decrease. In this case, reward prediction errors should increase as a function of time, consistent with experimental findings (Starkweather et al. [5,6]).



## Behaviors
Rapid and dramatic changes are desired, as seen in the [[Peak Interval (PI) procedure|peak interval preocedure]]
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

#### Figure 1. Li & Dudman 2013
[[@liMiceInferProbabilistic2013]]
![[image-20230417092004655.png]]

> Fig. 1. Design and performance of the [[@liMiceInferProbabilistic2013#SIV Task]]. 
> 
> **(A)** Schematic representation of select moments (red numbers 1–3) from the video of a single trial of the SIV task. 
> 
> **(B)** Timeline of three example trials taken from an example block in the SIV task. Blue sun indicates illumination of the cue light upon a successful lever press. Trial types are defined at left and referred to in the text. Probe trials were spaced by 6–10 trials (uniform random distribution, ∼15% of all trials in a block). Black Gaussian distributions represent the σdelay for the block, and the cyan circle represents the delay chosen for the current trial. The presence or absence of water reward is indicated by a blue water drop or red cross, respectively. The duration of reward consumption and waiting periods are indicated by yellow and gray shaded areas, respectively. Exit from the vestibule was used as an indication of the attempt to initiate a new trial. Red numbers indicate the corresponding moments between the timeline (B)and performance schematic (A). Interval metrics used in the text and subsequent figures are schematically shown as intervals corresponding to the “approach,” “reward,” and “waiting” times for each trial. (C) Example data from four blocks of a single daily session in which a trained mouse performed the SIV task. For each block of trials the reward delay interval distribution is indicated in the upper row. Individual waiting times (twaiting) on rewarded (black), probe (red), and error (cyan) trials are plotted as a function of trial.
> 
## Tasks
They use several micro episodes of animal IT experiments to describe expected behaviors, which we should expect to observe and reproduce with our models.

Most are some variation of the FI or Bisection procedure. Current model is basically in a FI environment. I will attempt to add further task environments as we go.

I haven’t had time to catalog them all yet but here is a list:
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
	- An extension of the FI task
- Untitled task where stimuli corresponding to different interval times were averaged by the animal  [\[56\]](https://www.sciencedirect.com/science/article/pii/S1364661318301931?via%3Dihub#bib0280)
- Tasks focused on timing integration and flexibility [[Integrating Models of Interval Timing and Reinforcement Learning - 11.07.22#^592cn4|here]] 