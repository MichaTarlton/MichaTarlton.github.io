---
theme: simple
height: 540
margin: 0
maxScale: 4

type: presentation
status: active
priority: p1
project: Obsidian Addons and Todos/MD Slides
creationtag: 2023-04-16 23:42
infotags: presentation
people: na
date:
---
%%Spawned from :: [[Presenting on Petter 2018]]%%



## Petter et al. 2018
Integrating Models of Interval Timing and Reinforcement Learning

---

### Summary
- Covers several animal experiments which test “Interval Timing (IT)”
- Explains the observed animal behavior in these experiments and response to reinforced stimulus
- Daws comparisons against RL methods
---



<!-- slide template="[[tpl2]]" -->
::: title
##### Interval Timing Experiments
::: 

::: left
![[image-20230417085647116.png]]


:::

::: right
**Conditioned Stimulus (CS**): 
Stimulus which animal is conditioned to associate with

**Unconditioned Stimulus (US**): 
The reward or some unexpected stimulus

**Interstimulus Interval (ISI**): 
Interval of time between CS and US

**Intertrial Interval (ITI**): 
Interval of time between trials of CS and US
:::<!-- element align="left" style="font-size: 15px;" class="small-indent" --> 
::: source
###### Figure 1. Predicting Reward with Temporal Representations
:::

---

<!-- slide template="[[tpl2]]" -->
::: title
##### Temporal Difference and Reward Prediction Error
::: 

::: left
![[image-20230417084207134.png|400]]
:::

<style>
.small-indent > ul { 
   padding-left: 1em;
}
</style>

::: right
**Temporal Difference and Reward Prediction Error:**
- Making reinforcements of predicted intervals based on the time elapsed between action and time reward is issued (TD)

**RPE:** 
- Increases activity with greater reward
- Activity stays constant with reward of similar value
- Lack of reward at prediction leads to decrease in dopamine neuron activity
:::<!-- element align="left" style="font-size: 13px;" class="small-indent" -->

::: source
###### Figure 5 Schultz 2016
:::


---
<!-- slide template="[[tpl2]]" -->
::: title
#### Neurons, Circuits, and Oscillators
::: 

::: left
![[image-20230417092955099.png]]
:::

::: right
**Neurons v. Neuronal Circuits**

**Time Cells**

**Oscillator Circuits**

:::<!-- element align="left" style="font-size: 13px;" class="small-indent" -->
::: source
###### Figure 2. Yin et al. 2022: Striatal-beat-frequency model of reward-based timing
:::

---
<!-- slide template="[[tpl2]]" -->
::: title
#### Bias-Variance Trade-Off
::: 

::: left
![[image-20230417090216248.png|400]]
:::

::: right
**Exploration v. Exploitation**

**Time Cell Tuning**

**Receptive Fields**

**Rescaling?**

:::<!-- element align="left" style="font-size: 20px;" class="small-indent" -->

---
<!-- slide template="[[tpl2]]" -->
::: title
#### Rescaling
::: 

::: left
*This ability to display time-invariant neural activity for multiple durations can be modeled using a recurrent neural network that exhibits stereotyped neural trajectories that vary speed based on a gain input.*

*Consequently, it appears as though the transition through neural state space does not change when the temporal criteria are altered, but just the rate at which the trajectory progresses (i.e., **clock speed**)*.

- **Illustrate:** Visual explanation of phase rescaling
:::<!-- element align="left" style="font-size: 20px;" class="small-indent" -->

<style>
.small-indent > ul { 
   padding-left: 1em;
}
</style>

::: right

**I don’t exactly get what they mean by “rescaling”**

**Is it referring to the expanding and contracting as well as the precessing and recessing of the phase**

**Neurons are able to rescale quickly and flexibly**

**How do we rescale for an STDP neuron?**

:::<!-- element align="left" style="font-size: 13px;" class="small-indent" -->


---
<!-- slide template="[[tpl2]]" -->
::: title
#### Reward Prediction Error
::: 

::: left
![[image-20230417084207134.png|400]]
:::

<style>
.small-indent > ul { 
   padding-left: 1em;
}
</style>

::: right
**Tonic and Phasic Dopaminergic Input**

**Tonic input relays global reward average**

**Phasic input controls “precision”  RPE**

**Global to Local Circuits Recurrence**


:::<!-- element align="left" style="font-size: 20px;" class="small-indent" -->
::: source
###### Figure 5. Schultz 2016
:::


---
<!-- slide template="[[tpl2]]" -->
::: title
#### Belief States
::: 

::: left
![[image-20230417084522842.png|500]]
:::

<style>
.small-indent > ul { 
   padding-left: 1em;
}
</style>

::: right
**Belief States**: 
- Confidence decay in conditioned interval, with increasing RPE

**Pull to Reward Ratio**

**Relation to Eligibility Traces in Three-Factor Learning?**

:::<!-- element align="left" style="font-size: 20px;" class="small-indent" -->


::: source
###### Figure 2. Interval Timing and Belief States
:::

---

<!-- slide template="[[tpl2]]" -->
::: title
#### Desired Behaviors
::: 

::: left
![[image-20230417092009995.png|400]]
:::<!-- element align="left" style="font-size: 20px;" class="small-indent" -->

<style>
.small-indent > ul { 
   padding-left: 1em;
}
</style>

::: right

**See: List of Tasks**

**Rapid and flexible changes are desired**

**Adaptability to changes in reward periods in around 10 trials**

**Integration of multiple intervals**

:::<!-- element align="left" style="font-size: 20px;" class="small-indent" -->

::: source
###### Figure 1. Li & Dudman 2013
:::

---

<!-- slide template="[[tpl2]]" -->
::: title
#### Tasks List
::: 

::: left

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

:::<!-- element align="left" style="font-size: 20px;" class="small-indent" -->

<style>
.small-indent > ul { 
   padding-left: 1em;
}
</style>

::: right

**Many animal experiment variations mentioned**

**Most are some variation of the Fixed Interval or Temporal Bisection procedure**

**Made a list of all the tasks I caught**

:::<!-- element align="left" style="font-size: 20px;" class="small-indent" -->


---