---
type: web article
creationtag: 2022-11-17 14:01
title: "A model for the peak-interval task based on neural oscillation-delimited states"
URL: "https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub"
people: []
infotags: [pi, peak, interval, task]
project: timing tasks
citekey: varellaModelPeakintervalTask2019
---

> [!Excerpt] A model for the peak-interval task based on neural oscillation-delimited states - ScienceDirect
> Specific mechanisms underlying how the brain keeps track of time are largely unknown. Several existing computational models of timing reproduce behavi…

---

-   [PDFView **PDF**](https://www.sciencedirect.com/science/article/pii/S037663571930124X/pdfft?md5=efa147f2751ac00af5d55cc01d8237e0&pid=1-s2.0-S037663571930124X-main.pdf)

## Outline

1.  [Highlights](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#abs0010 "Highlights")
2.  [Abstract](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#abs0015 "Abstract")
3.  [Graphical abstract](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#abs0005 "Graphical abstract")
4.  [Keywords](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#kwd0005 "Keywords")
5.  [1\. Introduction](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#sec0005 "1. Introduction")
6.  [2\. Methods](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#sec0010 "2. Methods")
7.  [3\. Results](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#sec0045 "3. Results")
8.  [4\. Discussion](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#sec0070 "4. Discussion")
9.  [Declarations of interest](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#sec0075 "Declarations of interest")
10.  [Acknowledgements](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#ack0005 "Acknowledgements")
11.  [Appendix B. Supplementary data](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#sec0085 "Appendix B. Supplementary data")
12.  [References](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bibl0005 "References")

## Figures (5)

1.  [
    
    ![[1-s2.0-S037663571930124X-ga1.sml]]
    
    ](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#fig0025)
2.  [
    
    ![[1-s2.0-S037663571930124X-gr1.sml]]
    
    ](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#fig0005)
3.  [
    
    ![[1-s2.0-S037663571930124X-gr2.sml]]
    
    ](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#fig0010)
4.  [
    
    ![[1-s2.0-S037663571930124X-gr3.sml]]
    
    ](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#fig0015)
5.  [
    
    ![[1-s2.0-S037663571930124X-gr4.sml]]
    
    ](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#fig0020)

[![[70 Wiki/articles/Markdown Clips_old/Beyond STDP — towards diverse and functionally relevant plasticity rules/elsevier-non-solus.png]]](https://www.sciencedirect.com/journal/behavioural-processes "Go to Behavioural Processes on ScienceDirect")

[![[1-s2.0-S0376635719X00108-cov150h.gif]]](https://www.sciencedirect.com/journal/behavioural-processes/vol/168/suppl/C)

## Highlights

•

The proposed model is based on the sequential activation of neural states, delimited by [neural oscillations](https://www.sciencedirect.com/topics/neuroscience/neural-oscillation "Learn more about neural oscillations from ScienceDirect's AI-generated Topic Pages").

•

The model reproduces behavioral results on peak-procedure task, including individual trial responses.

•

Simulations using the network model predicts the Weber law.

•

The model parameters have biological interpretations.

## Abstract

Specific mechanisms underlying how the brain keeps track of time are largely unknown. Several existing computational models of timing reproduce behavioral results obtained with experimental psychophysical tasks, but only a few tackle the underlying biological mechanisms, such as the synchronized neural activity that occurs throughout brain areas. In this paper, we introduce a model for the peak-interval task based on neuronal network properties. We consider that Local Field Potential (LFP) oscillation cycles specify a sequence of states, represented as neuronal ensembles. Repeated presentation of time intervals during training reinforces the connections of specific ensembles to downstream networks — sets of neurons connected to the sequence of states. Later, during the peak-interval procedure, these downstream networks are reactivated by previously experienced neuronal ensembles, triggering behavioral responses at the learned time intervals. The model reproduces experimental response patterns from individual rats in the peak-interval procedure, satisfying relevant properties such as the Weber law. Finally, we provide a biological interpretation of the parameters of the model.

-   [Navigate Left**Previous**](https://www.sciencedirect.com/science/article/pii/S037663571930172X)
-   [**Next** Navigate Right](https://www.sciencedirect.com/science/article/pii/S037663571930083X)

## Keywords

Timing

Biological neural network

Computational model

Weber law

Peak-procedure

Scalar property

## 1\. Introduction

How the brain represents the passage of time and uses this information in time-related tasks is still an ongoing debate in the scientific community. There seems to be different mechanisms involved in temporal processing depending on the time scale ([Buhusi and Meck, 2005](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0035), [Paton and Buonomano, 2018](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0215)). For example, interaural delay is key to temporal discrimination in the microseconds range ([Shaffer, 1984](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0230)), while circadian rhythms ([Czeisler et al., 1999](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0075)) seem to play a role in the estimation of many hours/days, besides controlling other important human functions such as body temperature ([Benloucif et al., 2005](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0025)). In particular, intermediate durations ranging from seconds to minutes (referred to as *interval timing* by the timing community) stand out in many aspects of animal behavior and physiology. Examples include foraging, decision making, sequential motor performance, and associative learning ([Merchant and Lafuente, 2014](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0195), [Buhusi and Meck, 2005](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0035)).

There are several models of interval timing which are able to reproduce behavioral results. However, only a few can also describe the critical properties of timing observed in experimental data, such as proportional timing (i.e., the linear relationship between the measured behavioral variable and the interval timed), the scalar property (i.e., the linear relationship between the standard deviation of the measured behavioral variable and the interval timed), and consequently Weber's law (the constant relative sensitivity to differences in a behavioral variable when varying that variable across different time intervals) ([Church and Meck, 2003](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0070)). One of the most influential models which successfully accounts for these properties is the Scalar [Expectancy Theory](https://www.sciencedirect.com/topics/neuroscience/expectancy-theory "Learn more about Expectancy Theory from ScienceDirect's AI-generated Topic Pages"), SET ([Gibbon, 1977](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0105), [Grondin, 2014](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0115)). SET is a cognitive process model which assumes the existence of a pacemaker which emits pulses at a certain rate that are stored by an accumulator. The temporal estimation comes from counting the number of pulses in the accumulator and comparing it to a number of pulses previously stored in the reference memory (i.e., past experiences). There is plenty of evidence for ramping activity ([Narayanan, 2016](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0205)), which favors an accumulator mechanism and can be understood using drift-diffusion models ([Luzardo et al., 2017](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0155)). Nevertheless, there are still criticisms about the plausibility of long-duration ramping of neural activity, and this criticisms can also be applied to other timing models ([Simen et al., 2013](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0235)).

Alternative models which do not necessarily assume cognitive intervening variables have been proposed, such as the Behavioral Theory of Timing (BeT) ([Killeen and Fetterman, 1988](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0140)) and a modified version of BeT called Learning to Time (LeT) ([Machado, 1997](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0165), [Machado et al., 2016](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0170)). LeT, for example, assumes that different behavioral states are serially activated when an organism is experiencing the passage of time. Each of these states is linked to a response by some degree, and the strength of these associations (vector of weights) are updated at every reinforcement (in reinforced trials) and by its omission (extinction trials) during learning. Although LeT can reproduce many essential features of timing behavior such as the scalar property, it is subject to the same criticisms attributed to SET, that is, it lacks direct biological correlates for its main underlying assumptions.

In order to deal with the issue of biological validity, some biologically-inspired candidate models of timing have been proposed. One example is the Striatal Beat Frequency (SBF) model ([Matell and Meck, 2004](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0180), [Oprisan and Buhusi, 2011](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0210)), where the coincidental activation of oscillating neurons underlies the mechanism of time-tracking. Indeed, natural brain oscillations play a crucial role in many aspects of behavior in the [hippocampus](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/hippocampus "Learn more about hippocampus from ScienceDirect's AI-generated Topic Pages") ([Klimesch, 1999](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0145), [Belluscio et al., 2012](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0020)), [thalamus](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/thalamus "Learn more about thalamus from ScienceDirect's AI-generated Topic Pages") ([Steriade et al., 1993](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0245)), striatum ([Berke et al., 2004](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0030)), [amygdala](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/amygdala "Learn more about amygdala from ScienceDirect's AI-generated Topic Pages") ([Halgren et al., 1977](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0120)), and other areas. The sequential activation of neural states that occurs in the hippocampus ([Lisman et al., 2005](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0150), [Buzsáki and Tingley, 2018](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0045)) is another candidate for timing models ([Meck et al., 1984](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0190)). Such state sequences can be generated using a heteroassociative learning rule ([Sompolinsky and Kanter, 1986](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0240), [Camargo et al., 2018](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0060)), which increases connection strengths between neurons from consecutive states in a sequence. The hippocampus has neurons called *time cells* ([Eichenbaum, 2014](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0090)) that fire at specific moments during the time interval. Studies have reported the existence of these cells in the medial [entorhinal cortex](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/entorhinal-cortex "Learn more about entorhinal cortex from ScienceDirect's AI-generated Topic Pages") (MEC) ([Tsao et al., 2018](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0255)) and in the medial [prefrontal cortex](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/prefrontal-cortex "Learn more about prefrontal cortex from ScienceDirect's AI-generated Topic Pages") (mPFC) ([Tiganj et al., 2017](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0250)) as well. Incorporating the *time cells* to a model can be instrumental in verifying the biological plausibility of a timing model ([Zeki and Balci, 2019](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0260)), along with the presence of [neural oscillations](https://www.sciencedirect.com/topics/neuroscience/neural-oscillation "Learn more about neural oscillations from ScienceDirect's AI-generated Topic Pages").

Recent evidence also suggests that the dynamics of neural populations can account for behavioral data observed in timing tasks ([Paton and Buonomano, 2018](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0215), [Balci and Simen, 2016](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0015), [Eichenbaum, 2014](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0090)). In state-dependent networks ([Karmarkar and Buonomano, 2007](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0135)), the state of the network, defined as the set of active neurons at a given moment, evolves over time, in a clear parallel to the behavioral states proposed by LeT. Another network can read the evolution of the neural state trajectory to measure the passage of time. Recently, it has been hypothesized that time is not explicitly represented in the brain but is a byproduct of ongoing activity which is composed of a succession of events ([Buzsáki and Llinas, 2017](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0040)). This dynamical arrangement also agrees with the idea of using a chain of events to perform time-related tasks. Even though these biologically-inspired models can reproduce neural activity which is frequently observed, including those from ramping neurons ([Durstewitz and Deco, 2008](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0085), [Machens et al., 2005](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0175)), only recently a [recurrent neural network](https://www.sciencedirect.com/topics/neuroscience/recurrent-neural-network "Learn more about recurrent neural network from ScienceDirect's AI-generated Topic Pages") has been described which could satisfy Weber's Law ([Hardy and Buonomano, 2018](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0130)).

In this article, we describe a candidate timing model inspired on brain networks with oscillatory activity and sequential state activation, in which states are represented as neuronal ensembles delimited by oscillatory cycles. We use the model to simulate data in a peak-interval procedure, where repeated presentations of time intervals during training reinforce the connections of specific ensembles to a downstream network — sets of neurons connected to the sequence of states. Then, during a reproduction phase, these downstream networks are reactivated by previously experienced neuronal ensembles, triggering behavioral responses at the learned time intervals. We compare our simulations to real data collected from rats. The implementation of this model follows the proposal by LeT, providing a possible biological interpretation for its key assumptions.

## 2\. Methods

### 2.1. Experiment set-up

We performed secondary data analyses from a peak procedure described by [Caetano (2009)](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0050) ([Fig. 1](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#fig0005)). In brief, one group of six male Sprague Dawley rats (Experimental Group) were trained to press a lever in a standard operant chamber to receive a food pellet (fixed-ratio 1 schedule of reinforcement for one experimental session). Next, they had to make a nose-poke response 20 s after the lever press in order to receive the food pellet (*tandem* fixed ratio 1/fixed interval 20 s schedule of reinforcement). During this phase, each trial initiated by the onset of a houselight. The first lever press after light onset initiated a 20-s fixed interval. Food was primed 20 s after the first lever press. The first nose-poke into the food cup (detected by the breaking of a photobeam) after food prime delivered the food pellet, terminated the houselight, and introduced a variable inter-trial interval (ITI = 40 s). If no nose-pokes were made within 20 s from food prime, the houselight turned off, the ITI was initiated, but no food was delivered.

![[1-s2.0-S037663571930124X-gr1.jpg]]

1.  [Download : Download high-res image (254KB)](https://ars.els-cdn.com/content/image/1-s2.0-S037663571930124X-gr1_lrg.jpg "Download high-res image (254KB)")
2.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S037663571930124X-gr1.jpg "Download full-size image")

Fig. 1. (a) Experimental setup of a typical Peak-Interval Procedure during a Fixed-Interval trial. A time-dependent light will be used as a stimulus and at the first nose-poke after 20 s the light will turn off and the food will drop at the food pellet. During a peak-interval, the light will keep turned on and the food will not drop. (b) Summary of the nose-pokes registered during each peak-interval trial with a target time of 20 s and the distribution containing the mean number of nose-pokes during each second of a trial.

Concurrently, six Sprague Dawley rats were trained on a control procedure in which 0.5-s white noise stimuli were yoked to the lever presses of a rat from the Experimental Group (Yoked Group). That is, for each lever press made by one rat in the Experimental Group, a noise stimulus was presented to its paired rat in the Yoked Group. For rats in this Yoked Group, no levers were available throughout training, and the fixed interval 20 s started with the first noise stimulus (i.e., yoked to the first lever press of a rat in the Experimental Group). Therefore, food was primed 20 s after the first noise in the trial, and the first nose-poke after food prime delivered the food pellet, terminated the houselight and introduced the ITI. All other experimental details were identical between groups. All rats were trained for 98 experimental sessions in this phase to ensure behavior stability. Finally, in the last training phase, peak trials were introduced with a probability of 0.5, during which all responses were recorded, but there was no food pellets. After 80 s from the first noise stimulus, the houselight was turned off, the ITI was introduced, and the next trial started.

We analyzed the peak trials from the last 15 sessions of all rats in the Yoked Group from the original dataset of 25 peak sessions. Each session analyzed had from 2 to 28 peak trials (average of 14.33 peak trials per session, with a standard deviation of 5.48). All experimental procedures were approved by the [Institutional Animal Care and Use Committee](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/institutional-animal-care-and-use-committee "Learn more about Institutional Animal Care and Use Committee from ScienceDirect's AI-generated Topic Pages") at Brown University and conform to guidelines for the Ethical Treatment of Animals (National Institutes of Health).

### 2.2. Learning mechanism

The model consists of a heteroassociative network represented by a series of successive states ([Sompolinsky and Kanter, 1986](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0240), [Camargo et al., 2018](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0060)). Each state corresponds to a subset of active neural units within a [Local Field Potential](https://www.sciencedirect.com/topics/neuroscience/local-field-potential "Learn more about Local Field Potential from ScienceDirect's AI-generated Topic Pages") (LFP) oscillation. Each state *i* has a weight $<math><msub is="true"><mi is="true">w</mi><mi is="true">i</mi></msub></math>$ to a downstream network, representing the combined effect of all neurons in that state into that network. They store information about the specific time being learned, causing the downstream network to fire at that specific time. The model was implemented in two phases to account for the two potentially different mechanisms involved in the task: the learning phase and the behavioral reproduction phase.

During the learning phase, as written in pseudocode in Algorithm 1, states are consecutively activated until a specific target time *T* has elapsed ([Fig. 2](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#fig0010)a). At that moment, the [synaptic weight](https://www.sciencedirect.com/topics/veterinary-science-and-veterinary-medicine/synaptic-weight "Learn more about synaptic weight from ScienceDirect's AI-generated Topic Pages") $<math><msub is="true"><mi is="true">w</mi><mi is="true">i</mi></msub></math>$ between the current active state *i* and the downstream network increases one (arbitrary) unit. This state activation sequence happens multiple times, one for each learning trial. For each trial, there is a transition time step *t*<sub><em>s</em></sub> between states drew from a Gaussian distribution with mean *μ* and standard deviation *σ*. At the end of the simulation, we normalized the $<math><msub is="true"><mi is="true">w</mi><mi is="true">i</mi></msub></math>$ values so that the maximum weight is 1.

**Algorithm 1**

Learning phase

•

Initialize parameters: *μ*, *σ* and *T*.

•

Initialize vector $<math><mi is="true">w</mi></math>$, with $<math><msub is="true"><mi is="true">w</mi><mi is="true">i</mi></msub><mo is="true">=</mo><mn is="true">0</mn><mo is="true">,</mo><mo is="true">∀</mo><mi is="true">i</mi></math>$.

•

For each trial:

○

Initialize the elapsed time *t* = 0 and active state *i* = 0.

○

Draw a time step *t*<sub><em>s</em></sub> from the normal distribution *N*(*μ*, *σ*)

○

While *t* < *T*, update *t* = *t* + *t*<sub><em>s</em></sub> and *i* = *i* + 1.

○

Add 1 to $<math><msub is="true"><mi is="true">w</mi><mi is="true">i</mi></msub></math>$.

•

Divide vector $<math><mi is="true">w</mi></math>$ by $<math><mi is="true">maximum</mi><mo stretchy="false" is="true">(</mo><msub is="true"><mi is="true">w</mi><mi is="true">i</mi></msub><mo stretchy="false" is="true">)</mo><mo is="true">,</mo><mo is="true">∀</mo><mi is="true">i</mi></math>$.

![[1-s2.0-S037663571930124X-gr2.jpg]]

1.  [Download : Download high-res image (690KB)](https://ars.els-cdn.com/content/image/1-s2.0-S037663571930124X-gr2_lrg.jpg "Download high-res image (690KB)")
2.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S037663571930124X-gr2.jpg "Download full-size image")

Fig. 2. (a) Visual representation of the Learning Phase of the model. Each green sphere represents a state and the lines between the green and the blue spheres represent the weight $<math><msub is="true"><mi is="true">w</mi><mi is="true">i</mi></msub></math>$ of the link between the state itself and another neural network represented by the blue sphere. The time steps *t*<sub><em>s</em></sub> compose a Gaussian distribution and the time *t* increases according to these steps. When the time *t* reaches the target time *T*, the weight of current state will raise. (b) Visual representation of the Reproduction Phase of the model. The same states will be activated successively just like the learning phase but linked with a basal response. While the process reaches states with weights above a threshold ℓ, it will activate a neural unit responsible to identify the target time. (c) Drawing a smaller *t*<sub><em>s</em></sub> value from the *t*<sub><em>s</em></sub> distribution (top graph) causes the network to reach states that have $<math><msub is="true"><mi is="true">w</mi><mi is="true">i</mi></msub><mo is="true">&gt;</mo><mo is="true">ℓ</mo></math>$ earlier and for a shorter period (bottom graph). (d) Same as (c), but for a large *t*<sub><em>s</em></sub> value, which causes states with $<math><msub is="true"><mi is="true">w</mi><mi is="true">i</mi></msub><mo is="true">&gt;</mo><mo is="true">ℓ</mo></math>$ to be reached later and for a longer period.

Note that the last activated state *i* after the elapsed time *T* is $<math><mfrac is="true"><mi is="true">T</mi><mrow is="true"><msub is="true"><mi is="true">t</mi><mi is="true">s</mi></msub></mrow></mfrac></math>$. Thus, the function that describes the weight $<math><msub is="true"><mi is="true">w</mi><mi is="true">i</mi></msub></math>$ converges to a distribution obtained by a change of variables from the Gaussian distribution of *t*<sub><em>s</em></sub> to $<math><mi is="true">i</mi><mo is="true">=</mo><mfrac is="true"><mi is="true">T</mi><mrow is="true"><msub is="true"><mi is="true">t</mi><mi is="true">s</mi></msub></mrow></mfrac></math>$. Prior to normalization, we can describe the distribution as:(1)$<math><mi is="true">f</mi><mo stretchy="false" is="true">(</mo><mi is="true">i</mi><mo is="true">,</mo><mi is="true">μ</mi><mo is="true">,</mo><mi is="true">σ</mi><mo stretchy="false" is="true">)</mo><mo is="true">=</mo><mfrac is="true"><mi is="true">T</mi><mrow is="true"><msup is="true"><mi is="true">i</mi><mn is="true">2</mn></msup><msqrt is="true"><mrow is="true"><mn is="true">2</mn><mi is="true">π</mi><msup is="true"><mi is="true">σ</mi><mn is="true">2</mn></msup></mrow></msqrt></mrow></mfrac><mo is="true">exp</mo><mrow is="true"><mfenced open="[" close="]" is="true"><mrow is="true"><mfrac is="true"><mrow is="true"><mo is="true">−</mo><msup is="true"><mrow is="true"><mfenced open="(" close=")" is="true"><mrow is="true"><mfrac is="true"><mi is="true">T</mi><mi is="true">i</mi></mfrac><mo is="true">−</mo><mi is="true">μ</mi></mrow></mfenced></mrow><mn is="true">2</mn></msup></mrow><mrow is="true"><mn is="true">2</mn><msup is="true"><mi is="true">σ</mi><mn is="true">2</mn></msup></mrow></mfrac></mrow></mfenced></mrow></math>$

We then reduced the parameters *μ* and *σ* to the coefficient *ρ* = *σ*/*μ*, which is, therefore, the coefficient of variation of the time step between the activation of two neural states. When we change the parameters of the states *i* to the nose-poke time using the transformation *t* = *μ* · *i*, and make *σ* = *μρ*, Eq. [(1)](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#eq0005) becomes:$<math><mi is="true">f</mi><mo stretchy="false" is="true">(</mo><mi is="true">i</mi><mo is="true">,</mo><mi is="true">μ</mi><mo is="true">,</mo><mi is="true">σ</mi><mo stretchy="false" is="true">)</mo><mo is="true">=</mo><mi is="true">f</mi><mrow is="true"><mfenced open="(" close=")" is="true"><mrow is="true"><mfrac is="true"><mi is="true">t</mi><mi is="true">μ</mi></mfrac><mo is="true">,</mo><mi is="true">μ</mi><mo is="true">,</mo><mi is="true">μ</mi><mi is="true">ρ</mi></mrow></mfenced></mrow><mo is="true">=</mo><mfrac is="true"><mrow is="true"><mi is="true">μ</mi><mi is="true">T</mi></mrow><mrow is="true"><msup is="true"><mi is="true">t</mi><mn is="true">2</mn></msup><msqrt is="true"><mrow is="true"><mn is="true">2</mn><mi is="true">π</mi><msup is="true"><mi is="true">ρ</mi><mn is="true">2</mn></msup></mrow></msqrt></mrow></mfrac><mo is="true">exp</mo><mrow is="true"><mfenced open="[" close="]" is="true"><mrow is="true"><mo is="true">−</mo><mfrac is="true"><mrow is="true"><msup is="true"><mrow is="true"><mfenced open="(" close=")" is="true"><mrow is="true"><mfrac is="true"><mi is="true">T</mi><mi is="true">t</mi></mfrac><mo is="true">−</mo><mn is="true">1</mn></mrow></mfenced></mrow><mn is="true">2</mn></msup></mrow><mrow is="true"><mn is="true">2</mn><msup is="true"><mi is="true">ρ</mi><mn is="true">2</mn></msup></mrow></mfrac></mrow></mfenced></mrow><mo is="true">=</mo><mi is="true">μ</mi><mspace width="thinmathspace" is="true"></mspace><mi is="true">f</mi><mo stretchy="false" is="true">(</mo><mi is="true">t</mi><mo is="true">,</mo><mn is="true">1</mn><mo is="true">,</mo><mi is="true">ρ</mi><mo stretchy="false" is="true">)</mo></math>$

The threshold ℓ is the lower degree of activation that generates the behavioral response, and it ranges from 0 to 1. Thus, we have to normalize the maximum weight to 1 (last step in Algorithm 1) to establish a comparison of $<math><msub is="true"><mi is="true">w</mi><mi is="true">i</mi></msub></math>$ and ℓ. Given the maximum *M*(*ρ*) of the function *f*(*t*, 1, *ρ*) in *t*, we have that *μM*(*ρ*) must be the maximum of the function *f*(*i*, *μ*, *σ*). The final function describing the neural activity at the network in terms of the time elapsed is(2)$<math><msub is="true"><mrow is="true"><mfenced open="(" close=")" is="true"><mrow is="true"><mi is="true">f</mi><mo stretchy="false" is="true">(</mo><mi is="true">t</mi><mo is="true">,</mo><mi is="true">μ</mi><mo is="true">,</mo><mi is="true">σ</mi><mo stretchy="false" is="true">)</mo></mrow></mfenced></mrow><mrow is="true"><mo is="true">ℓ</mo><mo is="true">∈</mo><mo stretchy="false" is="true">[</mo><mn is="true">0</mn><mo is="true">,</mo><mn is="true">1</mn><mo stretchy="false" is="true">]</mo></mrow></msub><mo is="true">=</mo><mfrac is="true"><mn is="true">1</mn><mrow is="true"><mi is="true">μ</mi><mi is="true">M</mi><mo stretchy="false" is="true">(</mo><mi is="true">ρ</mi><mo stretchy="false" is="true">)</mo></mrow></mfrac><mi is="true">μ</mi><mspace width="thinmathspace" is="true"></mspace><mi is="true">f</mi><mrow is="true"><mfenced open="(" close=")" is="true"><mrow is="true"><mi is="true">t</mi><mo is="true">,</mo><mn is="true">1</mn><mo is="true">,</mo><mi is="true">ρ</mi></mrow></mfenced></mrow><mo is="true">=</mo><mfrac is="true"><mi is="true">T</mi><mrow is="true"><mi is="true">M</mi><mo stretchy="false" is="true">(</mo><mi is="true">ρ</mi><mo stretchy="false" is="true">)</mo><msup is="true"><mi is="true">t</mi><mn is="true">2</mn></msup><msqrt is="true"><mrow is="true"><mn is="true">2</mn><mi is="true">π</mi><msup is="true"><mi is="true">ρ</mi><mn is="true">2</mn></msup></mrow></msqrt></mrow></mfrac><mo is="true">exp</mo><mrow is="true"><mfenced open="[" close="]" is="true"><mrow is="true"><mo is="true">−</mo><mfrac is="true"><mrow is="true"><msup is="true"><mrow is="true"><mfenced open="(" close=")" is="true"><mrow is="true"><mfrac is="true"><mi is="true">T</mi><mi is="true">t</mi></mfrac><mo is="true">−</mo><mn is="true">1</mn></mrow></mfenced></mrow><mn is="true">2</mn></msup></mrow><mrow is="true"><mn is="true">2</mn><msup is="true"><mi is="true">ρ</mi><mn is="true">2</mn></msup></mrow></mfrac></mrow></mfenced></mrow></math>$so we can conclude that the only relevant parameters of the model to be used in the Algorithm 1 are *ρ* and ℓ.

### 2.3. Behavioral reproduction

In the reproduction phase the model generates single-trial responses that are similar to the responses observed in the experimental peak trials. The model uses the same series of states shown in [Fig. 2](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#fig0010)b. When the network activates states whose output weights are smaller than a threshold 0 ≤ ℓ ≤1, rats respond with a basal rate *r*<sub><em>b</em></sub>. When it reaches states whose weights are larger than the threshold, rats respond with a higher rate *r*<sub><em>a</em></sub>. Algorithm 2 shows the simulation steps. The rationale behind this scheme is that rats tend to respond in bursts of response around the criterion ([Church et al., 1994](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0065)).

The reproduction phase algorithm generates single-trial responses. The time required to reach and leave the states with weights larger than ℓ depends on the *t*<sub><em>s</em></sub> value drawn at each trial from the normal distribution *N*(*μ*, *σ*) ([Fig. 2](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#fig0010)c and d). We simulated the hypothetical nose-pokes using a [Poisson distribution](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/poisson-distribution "Learn more about Poisson distribution from ScienceDirect's AI-generated Topic Pages") with average rate *λ* = *r*<sub><em>a</em></sub> between time the burst start *t*<sub>1</sub> and burst stop *t*<sub>2</sub>, and *λ* = *r*<sub><em>b</em></sub> for the remaining period.

**Algorithm 2**

Behavioral reproduction phase

•

Initialize parameters *μ*, *σ*, $<math><mi is="true">w</mi></math>$, ℓ, *r*<sub><em>b</em></sub> and *r*<sub><em>a</em></sub>.

•

For each trial:

○

Initialize the elapsed time *t* = 0 and active state *i* = 0.

○

Draw a time step *t*<sub><em>s</em></sub> from the normal distribution *N*(*μ*, *σ*).

○

While $<math><msub is="true"><mi is="true">w</mi><mi is="true">i</mi></msub><mo is="true">≤</mo><mo is="true">ℓ</mo></math>$.

Update *t* = *t* + *t*<sub><em>s</em></sub> and *i* = *i* + 1.

○

Set *t*<sub>1</sub> = *t*.

○

While $<math><msub is="true"><mi is="true">w</mi><mi is="true">i</mi></msub><mo is="true">≥</mo><mo is="true">ℓ</mo></math>$.

Update *t* = *t* + *t*<sub><em>s</em></sub> and *i* = *i* + 1.

○

Set *t*<sub>2</sub> = *t*.

○

Generate nose-poke times from 0 to *t*<sub>1</sub> from Poisson process with a rate *r*<sub><em>b</em></sub>.

○

Generate nose-poke times from *t*<sub>1</sub> to *t*<sub>2</sub> from a Poisson process with a rate *r*<sub><em>a</em></sub>.

○

Generate nose-poke times from *t*<sub>2</sub> till end from a Poisson process with a rate *r*<sub><em>b</em></sub>.

### 2.4. Parameters search

We fitted the parameters to the experimental data of each rat separately. Parameters *ρ* = *σ*/*μ* and ℓ are important to the neural mechanism, while *r*<sub><em>a</em></sub> and *r*<sub><em>b</em></sub> are important to the behavioral response of rats.

Given the 4 parameters of one search instance, we generated trials of the reproduction phase — for each trial, we simulated a set of nose-poke times with Algorithm 2 and calculated a response-time histogram similar to [Fig. 1](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#fig0005)(b) using 80 bins (1 bin per second), covering all the 80 s of peak-interval task.

We found the best fit for each rat by calculating the mean squared error (MSE) between the histogram generated by the model and the experimental histograms. The experimental vector contained each 1-s bin of the experimental nose-poke distribution of a rat. The model vector contained each 1-s bin of the distribution generated by the model. After calculating the difference for many possible parameters for the model, we stored the parameters that gave the lower distance.

The basal rate and the burst rate were obtained by analyzing each distribution for each rat. That way, we made sure that the model parameters would be compatible with each rat behavior. The basal rate was the average nose-poke rate after 60 s — at the tail of the experimental distributions from [Fig. 3](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#fig0015). We searched the other two parameters (*ρ* and ℓ) in a grid where both parameters ranged from 0 to 1 in intervals of 0.05.

![[1-s2.0-S037663571930124X-gr3.jpg]]

1.  [Download : Download high-res image (644KB)](https://ars.els-cdn.com/content/image/1-s2.0-S037663571930124X-gr3_lrg.jpg "Download high-res image (644KB)")
2.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S037663571930124X-gr3.jpg "Download full-size image")

Fig. 3. (a) Fitting of the model with the experimental data for each of the 6 rats. The red line represents the simulation fitted with the best parameters and the black line represents the experimental data. (b) Region in the space of parameters (threshold vs. *σ*/*μ*) in which the goodness of fit of the simulation was smaller than 0.018. The solid dots represent best goodness of fit. Each color represents a different rat. In front of the labels, the upper number is the burst rate and the lower number is the basal rate for that particular rat. (c) Reproduction of the scalar property by calculating the standard deviation for 5 different target times (2, 4, 8, 16 and 32 s) and then plotting a linear regression.

### 2.5. Weber law

We can use the best parameters to simulate an idealized version of the rat and then check if the model express the scalar property. To assess the scalar property, we need to change the target time. For each target time, we simulated the model 10 times and averaged the standard deviation of the resulting nose-poke time distributions given by the model. Only 10 times was enough because the distributions had little variation in each simulation.

The basal nose-pokes response influences the distributions to stay above the zero line at any time, i.e., the responses distribution do not converge to zero at their tails. Hence, we are not able to normalize these curves and neither calculate their associated statistics. For that reason, we considered only the responses during the bursts to calculate the standard deviations.

### 2.6. Individual trials simulation and analysis

For each rat, we used the parameters search to find the best parameters associated with the model. With these parameters, we can reproduce single trials from the rat by using the Algorithm 2.

To compare the start (*t*<sub>1</sub>) and stop times (*t*<sub>2</sub>) from both experimental data and the model we fitted each experimental trial using the methodology proposed by [Church et al. (1994)](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0065). In that method, we made a search within *t*<sub>1</sub> and *t*<sub>2</sub> and stored the values that gave the maximum value of(3)$<math><msub is="true"><mi is="true">t</mi><mn is="true">1</mn></msub><mo stretchy="false" is="true">(</mo><mi is="true">r</mi><mo is="true">−</mo><msub is="true"><mi is="true">r</mi><mn is="true">1</mn></msub><mo stretchy="false" is="true">)</mo><mo is="true">−</mo><mo stretchy="false" is="true">(</mo><msub is="true"><mi is="true">t</mi><mn is="true">2</mn></msub><mo is="true">−</mo><msub is="true"><mi is="true">t</mi><mn is="true">1</mn></msub><mo stretchy="false" is="true">)</mo><mo stretchy="false" is="true">(</mo><mi is="true">r</mi><mo is="true">−</mo><msub is="true"><mi is="true">r</mi><mn is="true">2</mn></msub><mo stretchy="false" is="true">)</mo><mo is="true">+</mo><mo stretchy="false" is="true">(</mo><mn is="true">80</mn><mo is="true">−</mo><msub is="true"><mi is="true">t</mi><mn is="true">2</mn></msub><mo stretchy="false" is="true">)</mo><mo stretchy="false" is="true">(</mo><mi is="true">r</mi><mo is="true">−</mo><msub is="true"><mi is="true">r</mi><mn is="true">3</mn></msub><mo stretchy="false" is="true">)</mo><mo is="true">,</mo></math>$where *r* is the nose-poke rate for the whole trial, *r*<sub>1</sub> is the nose-poke rate for the first interval (from 0 to *t*<sub>1</sub>), *r*<sub>2</sub> is the nose-poke rate for the second interval (that is equivalent to the burst rate, from *t*<sub>1</sub> to *t*<sub>2</sub>) and *r*<sub>3</sub> is the nose-poke rate in the last interval (from *t*<sub>2</sub> to 80 s — the last time bin recorded).

## 3\. Results

### 3.1. Reproduction of behavioral responses

The model reproduced the experimental nose-poke rate response of 6 individual rats ([Fig. 3](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#fig0015)a). We characterized the nose-poke rate by tuning 4 parameters: the *ρ* = *σ*/*μ* ratio, the threshold ℓ of the [neural network](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/neural-networks "Learn more about neural network from ScienceDirect's AI-generated Topic Pages"), the burst rate *r*<sub><em>a</em></sub>, and the basal rate *r*<sub><em>b</em></sub>. The best goodness-of-fit after tuning the parameters are shown in [Table 1](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#tbl0005). All simulations could reproduce the target time and the standard deviation of the curve, except for a deviation of the tail of the distribution for rat 2 and of the target time for rat 3.

Table 1. Goodness of fit between the experimental data and the best fitted model for each rat in responses per second (resps./s)

| Rat | 1 | 2 | 3 | 4 | 5 | 6 |
| --- | --- | --- | --- | --- | --- | --- |
| MSE | 0.009 | 0.014 | 0.016 | 0.004 | 0.010 | 0.005 |

Each rat had a different nose-poke rate. We considered in the model that the rat would nose-poke at a burst rate *r*<sub><em>a</em></sub> when the downstream neural network is active. Otherwise, it would nose-poke at a basal rate *r*<sub><em>b</em></sub>. The target time *T* is the most important factor to determinate the activation of the downstream network. The threshold ℓ and the coefficient *ρ* = *σ*/*μ* of the time step sizes dictated the deviation of the final distribution. They are responsible for a fine-tuning of the response curve.

Notice that the rat 3 had the worst metrics among all the rats. That difference happened because the peak of the response distribution was delayed in relation to the peak predicted by the model — the rat was biased. The second worst model performance is from rat 2, which shows a difference in the tail of the distribution, reaching a rate lower than the basal rate before converging to the basal rate.

### 3.2. Parameters similarities

The parameter *ρ* = *σ*/*μ* and ℓ obtained for each of the rats were similar. Within the space of parameters, we plotted the regions where the MSE of the model and the experimental data were less than a certain value ([Fig. 3](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#fig0015)b). The smallest MSE that we found an intersecting region is approximately 0.018. The parameters correspondent to that distance are (ℓ , *ρ*) = (0.125, 0.35). It means that, for all rats, using these parameters yields a MSE of at most 0.018.

The basal rate found for each rat was, respectively, 0.3, 0.15, 0.02, 0.2, 0.1 and 0.19. The burst rate used for each rat was, respectively, 1.7, 2.1, 1.3, 1.8, 2.2, 1.3. Notice that basal rates were similar between rats, as were burst rates. The basal rates correspond to the height of the nose-poke rate curves at the immediate beginning and during the end of the sessions.

### 3.3. Weber law

There was a linear relationship between the target time and the standard deviation of the responses given by the model ([Fig. 3](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#fig0015)c). The error of the standard deviations (*y*\-axis) was small and thus not visible in the graph. The Weber fraction *WF* calculated using the parameters given by the intersecting region of the six rats was *WF* = 0.5. The value is consistent with values found in the literature, such as the range of 0.35 to 0.5 in [Gibbon (1977)](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0105).

### 3.4. Start and stop time distributions

The distributions of start and stop times that the model generated were similar to the experimental distributions ([Fig. 4](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#fig0020)a and b). We simulated single trials using Algorithm 2 for each rat. The parameters used were those from the best fit. The number of trials simulated was proportional to the experimental number of trials for each rat. The model reproduced the peak positions. It could not reproduce well the right tail of the start bursts and left tail of stop bursts. [Fig. 4](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#fig0020)c and d compare model-generated and experimental data, respectively, from one rat.

![[1-s2.0-S037663571930124X-gr4.jpg]]

1.  [Download : Download high-res image (379KB)](https://ars.els-cdn.com/content/image/1-s2.0-S037663571930124X-gr4_lrg.jpg "Download high-res image (379KB)")
2.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S037663571930124X-gr4.jpg "Download full-size image")

Fig. 4. (a) Comparison between start-times distribution in individual trials, both from experimental data (gray) and generated by the model (red). (b) Same as (a) for stop-times. (c) Individual trials generated by the model using the parameters optimized from rat 2. (d) Individual trials for rat 2, session 11.

## 4\. Discussion

The proposed model works with [neural networks](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/neural-networks "Learn more about neural networks from ScienceDirect's AI-generated Topic Pages") that generate reproducible sequences of states at steady rates. Heteroassociative networks ([Sompolinsky and Kanter, 1986](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0240), [Camargo et al., 2018](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0060)) can be used to implement our model as a biological neural network, as well as [Synfire chains](https://www.sciencedirect.com/topics/veterinary-science-and-veterinary-medicine/synfire-chain "Learn more about Synfire chains from ScienceDirect's AI-generated Topic Pages") ([Abeles, 1991](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0005), [Miyata et al., 2013](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0200)). The later introduced the idea of a rapid sequential activation of groups of neurons, representing the states in our model. Accordingly, heteroassociative networks are promising as a biological implementation of the model, since they can produce long sequences of state activation within a single network while performing pattern completion ([Camargo et al., 2018](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0060)). This kind of networks are present in both the CA3 ([Lisman et al., 2005](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0150)) and CA1 ([Miyata et al., 2013](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0200)) subregions of the [hippocampus](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/hippocampus "Learn more about hippocampus from ScienceDirect's AI-generated Topic Pages"), which is involved in some time-related tasks ([Meck et al., 1984](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0190)). Accumulated evidence suggests that timing mechanisms are decentralized ([Paton and Buonomano, 2018](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0215)) and the hippocampus is one from brain areas where sequences of states could be evoked ([Buzsáki and Tingley, 2018](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0045)).

Pieces of evidence support that [neural oscillations](https://www.sciencedirect.com/topics/neuroscience/neural-oscillation "Learn more about neural oscillations from ScienceDirect's AI-generated Topic Pages") are involved in many different processes such as memory ([Hanslmayr and Staudigl, 2014](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0125)) and brain integration or neural communication in general ([Fries, 2015](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0100)). Also, most of the brain regions exhibit electrical oscillations, so their integration with the model is beneficial. Even though the model can be implemented without them, they are a good candidate for providing steady transition rates between states. The parameter *μ* in our model would be related to the oscillation period and *σ* its variability. Interestingly, the coefficient *ρ* = *σ*/*μ* of the oscillation – not the Weber fraction – could be important to characterize brain oscillations, for instance, indicating its adaptability in certain contexts ([Schlee et al., 2014](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0225), [Calomeni et al., 2017](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0055)). The parameters obtained from the intersection of the 6 rats ([Fig. 3](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#fig0015)b) predicted a coefficient *ρ* at approximately 0.35. This could correspond, for instance, to *μ* = 25 ms and *σ* = 8.75 ms, resulting in a frequency range of 30-60 Hz, in the range of experimentally observed slow gamma waves ([Belluscio et al., 2012](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0020)). Gamma frequency waves are present in several brain areas and could be a candidate for providing the state transition rates.

The reproducible sequences of states at steady rates would also give rise to cells that respond at specific times of the task, similarly to time cells, discovered in the Hippocampus ([Einchenbaum, 2013](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0095)), medial [entorhinal cortex](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/entorhinal-cortex "Learn more about entorhinal cortex from ScienceDirect's AI-generated Topic Pages") (MEC) ([Tsao et al., 2018](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0255)) and medial [prefrontal cortex](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/prefrontal-cortex "Learn more about prefrontal cortex from ScienceDirect's AI-generated Topic Pages") (mPFC) ([Tiganj et al., 2017](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0250)). Neurons with behavior similar to time cells could appear both as part of the states in the sequence and as part of the downstream network. These time cells would also “retime” when an important temporal parameter changes ([MacDonald et al., 2011](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0160)). The existence of neurons with time cells is an important link of the proposed model with existing biological evidence.

The proposed model uses a bottom-up approach, from properties of brain neural networks to behavioral responses from rats. Interestingly, it resembles the computational implementation of the Learning-to-Time (LeT) behavioral model. In both models, serially activated states have different link strengths to an outside unit, and a threshold leading to behavioral responses. There are differences, such as the LeT extinguishing of non-active link strengths. The LeT model was motivated by the proposal of behavioral internal states, without reference to the underlying biological mechanisms. Our proposed model can provide a link from the behavioral model to a possible biological substrate.

Recently, a new model based on time cells was proposed ([Zeki and Balci, 2019](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0260)). The model consists of a chain of connected time cell ensembles, with each time cell receiving inhibitory feedback from a slow inhibitory cell (SICn). We should note that in their model time cells are used to represent the actual network states, while in our model time cells represent a separate set of neurons that reads the state from our model. Another difference is that in our model the scalar property derives mainly from the variation of the state transition rate *μ*, which is directly related to neural oscillations, while their model depends on inhibitory currents that modulate the interspike intervals.

Our model has some limitations. One example is that the model could not perfectly reproduce the start and the stop distributions of burst nose-pokes ([Fig. 4](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#fig0020)). The genesis of this discrepancy may rely on the way we generated single trials. A visual inspection of [Fig. 4](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#fig0020)c and d shows that the experimental data is more sparsely distributed than the simulation. That difference comes from the fact that the neural network we are proposing deals with the task-related interval representation in the brain. The way the behavior appears will have more intricate mechanisms. For example, the hypothesis of one single burst per trial is false in all experimental responses — processes like attention ([Graziano and Webb, 2015](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0110)), impulsiveness ([Dalley et al., 2011](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0080)), and satiation ([Avau et al., 2015](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0010)) impose a greater level of complexity to behavior that stretches beyond the scope of our model.

The peak of the response rate for all rats showed a bias toward values above the experimental interval of 20 s, which could arise from impulsive responding ([Matell and Portugal, 2007](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0185), [Renda et al., 2014](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bib0220)). Our model does not capture this bias correctly, as can be seen in the pressing rate distribution of rat 3, whose peak response lies 5 to 10 s delayed from the target time. The peak of the distribution of simulated responses depends on the target time learned by the rat. One way to account for a variation in the distribution peak in our model would be by increasing the transition time between states in the behavioral reproduction phase, but this would be hard to justify biologically. We believe that the bias is more related to the decision-making process than the timing mechanism itself and decided not to include an extra parameter, which would increase the complexity of the model.

## Declarations of interest

None declared.

## Acknowledgements

During the project, TTV was supported by the Fundação de Amparo à Pesquisa do Estado de São Paulo (FAPESP, grant [#2016/19691-1](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#gs0005)) and by the Universidade de São Paulo International Cooperation Office Scholarship. MSC is a member of the Instituto Nacional de Ciência e Tecnologia sobre Comportamento, Cognição e Ensino, with support from the Brazilian National Research Council (CNPq, Grant [#465686/2014-1](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#gs0015)), the Coordination of Superior Level Staff Improvement (CAPES, Grant [#88887.136407/2017-00](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#gs0020)), and FAPESP (Grant [#2014/50909-8](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#gs0005)). The authors would like to thank the members of the Timing and Cognition Lab ([http://neuro.ufabc.edu.br/timing/](http://neuro.ufabc.edu.br/timing/)), at Universidade Federal do ABC, for their suggestions during project development. Finally, authors thank Prof. Armando Machado for helpful discussions during the research.

## References

[Abeles, 1991](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0005)

M. Abeles

**Corticonics: Neuronal Circuits of the Cerebral Cortex**

Cambridge University Press, Cambridge (1991)

[Avau et al., 2015](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0010)

B. Avau, A. Rotondo, T. Thijs, C.N. Andrews, P. Janssen, J. Tack, I. Depoortere

**Targeting extra-oral bitter taste receptors modulates gastrointestinal motility with effects on satiation**

Sci. Rep., 5 (1) (2015)

[Balci and Simen, 2016](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0015)

F. Balci, P. Simen

**A decision model of timing**

Curr. Opin. Behav. Sci., 8 (2016), pp. 94-101

[Belluscio et al., 2012](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0020)

M.A. Belluscio, K. Mizuseki, R. Schimdt, R. Kempter, G. Buzsáki

**Cross-frequency phase-phase coupling between theta and gamma oscillations in the hippocampus**

J. Neurosci., 32 (2) (2012), pp. 423-435

[Benloucif et al., 2005](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0025)

S. Benloucif, M.J. Guico, K.J. Reid, L.F. Wolfe, M. L’Hermite-Balériaux, P.C. Zee

**Stability of melatonin and temperature as circadian phase markers and their relation to sleep times in humans**

J. Biol. Rhythms, 2 (2005), pp. 178-188

[Berke et al., 2004](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0030)

J.D. Berke, M. Okatan, J. Skurski, H. Eichenbaum

**Oscillatory entrainment of striatal neurons in freely moving rats**

Neuron, 43 (2004), pp. 883-896

[Buhusi and Meck, 2005](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0035)

C.V. Buhusi, W.H. Meck

**What makes us tick? functional and neural mechanisms of interval timing**

Nat. Rev. Neurosci., 6 (2005), pp. 755-765

[Buzsáki and Llinas, 2017](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0040)

G. Buzsáki, R. Llinas

**Space and time in the brain**

Science (New York, N.Y.), 358 (6362) (2017), pp. 482-485

[Buzsáki and Tingley, 2018](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0045)

G. Buzsáki, D. Tingley

**Space and time: the hippocampus as a sequence generator**

Trends Cognit. Sci., 22 (10) (2018), pp. 853-869

[Caetano, 2009](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0050)

M.S. Caetano

**Responses As Time Markers. PhD Thesis**

Brown University (2009)

[Calomeni et al., 2017](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0055)

M.R. Calomeni, V.F. da Silva, B.B. Velasques, O.G. Feijó, J. Bittencourt, A.P.R. de Souza e Silva

**Modulatory effect of association of brain stimulation by light and binaural beats in specific brain waves**

Clin. Pract. Epidemiol. Ment. Health, 13 (2017), pp. 134-144

[Camargo et al., 2018](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0060)

R. Camargo, R.S. Recio, M.B. Reyes

**Heteroassociative storage of hippocampal pattern sequences in the ca3 subregion**

PeerJ, 6 (2018), p. e4204

[Church et al., 1994](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0065)

R. Church, W. Meck, J. Gibbon

**Application of scalar timing theory to individual trials**

J. Exp. Psychol. Anim. Behav. Process., 20 (2) (1994), pp. 135-155

[Church and Meck, 2003](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0070)

R.M. Church, W.H. Meck

**Functional and Neural Mechanisms of Interval Timing, Chapter A Concise Introduction to Scalar Timing Theory**

CRC Press (2003), pp. 3-22

[Czeisler et al., 1999](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0075)

C.A. Czeisler, J.F. Duffy, T.L. Shanahan, E.N. Brown, J.F. Mitchell, D.W. Rimmer, J.M. Ronda, E.J. Silva, J.S. Allan, J.S. Emens, D.-J. Dijk, R.E. Kronauer

**Stability, precision, and near-24-hour period of the human circadian pacemaker**

Science, 284 (5423) (1999), pp. 2177-2181

[Dalley et al., 2011](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0080)

J.W. Dalley, B.J. Everitt, T.W. Robbins

**Impulsivity, compulsivity, and top-down cognitive control**

Neuron, 69 (4) (2011), pp. 680-694

[Durstewitz and Deco, 2008](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0085)

D. Durstewitz, G. Deco

**Computational significance of transient dynamics in cortical networks**

Eur. J. Neurosci., 27 (1) (2008), pp. 217-227

[Eichenbaum, 2014](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0090)

H. Eichenbaum

**Time cells in the hippocampus: a new dimension for mapping memories**

Nat. Rev. Neurosci., 15 (11) (2014), pp. 732-744

[Einchenbaum, 2013](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0095)

H. Einchenbaum

**Memory on time**

Trends Cognit. Sci., 17 (2) (2013), p. 255

[Fries, 2015](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0100)

P. Fries

**Rhythms for cognition: communication through coherence**

Neuron, 88 (1) (2015), pp. 220-235

[Gibbon, 1977](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0105)

J. Gibbon

**Scalar expectancy theory and weber's law in animal timing**

Psychol. Rev., 84 (3) (1977), pp. 279-325

[Graziano and Webb, 2015](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0110)

M.S.A. Graziano, T.W. Webb

**The attention schema theory: a mechanistic account of subjective awareness**

Front. Psychol. (2015), p. 06

[Grondin, 2014](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0115)

S. Grondin

**About the (non)scalar property for time perception**

Adv. Exp. Med. Biol., 829 (2014)

[Halgren et al., 1977](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0120)

E. Halgren, T. Babb, P. Crandall

**Responses of human limbic neurons to induced changes in blood gases**

Brain Res., 132 (1977), pp. 43-63

[Hanslmayr and Staudigl, 2014](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0125)

S. Hanslmayr, T. Staudigl

**How brain oscillations form memories – a processing based perspective on oscillatory subsequent memory effects**

NeuroImage, 85 (2014), pp. 648-655

[Hardy and Buonomano, 2018](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0130)

N.F. Hardy, D.V. Buonomano

**Encoding time in feedforward trajectories of a recurrent neural network model**

Neural Comput., 30 (2018), pp. 378-396

[Karmarkar and Buonomano, 2007](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0135)

U. Karmarkar, D. Buonomano

**Telling time in the absence of clocks**

Neuron, 53 (3) (2007), pp. 427-438

[Killeen and Fetterman, 1988](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0140)

D. Killeen, J.G. Fetterman

**A behavioral theory of timing**

Psychol. Rev., 95 (2) (1988), pp. 274-295

[Klimesch, 1999](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0145)

W. Klimesch

**Eeg alpha and theta oscillations reflect cognitive and memory performance: a review and analysis**

Brain Res. Rev., 29 (1999), pp. 169-195

[Lisman et al., 2005](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0150)

J.E. Lisman, L. Talamini, A. Raffone

**Recall of memory sequences by interaction of the dentate and ca3: a revised model of the phase precession**

Neural Netw., 18 (9) (2005), pp. 1191-1201

[Luzardo et al., 2017](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0155)

A. Luzardo, F. Rivest, E. Alonso, E.A. Ludvig

**A drift-diffusion model of interval timing in the peak procedure**

J. Math. Psychol., 77 (2017), pp. 111-123

[MacDonald et al., 2011](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0160)

C.J. MacDonald, K.Q. Lepage, U.T. Eden, H. Eichenbaum

**Hippocampal “time cells” bridge the gap in memory for discontiguous events**

Neuron, 71 (4) (2011), pp. 737-749

[Machado, 1997](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0165)

A. Machado

**Learning the temporal dynamics of behavior**

Psychol. Rev., 104 (2) (1997), pp. 241-265

[Machado et al., 2016](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0170)

A. Machado, M.P. Carvalho, F. Tonneau

**Learning in the temporal bisection task: relative or absolute?**

J. Exp. Psychol.: Anim. Learn. Cognit., 42 (1) (2016), pp. 67-81

[Machens et al., 2005](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0175)

C.K. Machens, R. Romo, C.D. Brody

**Flexible control of mutual inhibition: a neural model of two-interval discrimination**

Science, 5712 (307) (2005), pp. 1121-1124

[Matell and Meck, 2004](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0180)

M.S. Matell, W.H. Meck

**Cortico-striatal circuits and interval timing: coincidence detection of oscillatory processes**

Cognit. Brain Res., 21 (2004), pp. 139-170

[Matell and Portugal, 2007](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0185)

M.S. Matell, G.S. Portugal

**Impulsive responding on the peak-interval procedure**

Behav. Process., 74 (2) (2007), pp. 198-208

[Meck et al., 1984](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0190)

W.H. Meck, R.M. Church, D.S. Olton

**Hippocampus, time, and memory**

Behav. Neurosci., 98 (1) (1984), pp. 3-22

[Merchant and Lafuente, 2014](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0195)

H. Merchant, V. Lafuente

**Introduction to the neurobiology of interval timing**

Adv. Exp. Med. Biol., 829 (2014)

[Miyata et al., 2013](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0200)

R. Miyata, K. Ota, T. Aonishi

**Optimal design for hetero-associative memory: hippocampal ca1 phase response curve and spike-timing-dependent plasticity**

PLOS ONE, 8 (10) (2013)

[Narayanan, 2016](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0205)

N.S. Narayanan

**Ramping activity is a cortical mechanism of temporal control of action**

Curr. Opin. Behav. Sci., 8 (2016), pp. 226-230

[Oprisan and Buhusi, 2011](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0210)

S.A. Oprisan, C.V. Buhusi

**Modeling pharmacological clock and memory patterns of interval timing in a striatal beat-frequency model with realistic, noisy neurons**

Front. Integr. Neurosci., 5 (2011)

[Paton and Buonomano, 2018](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0215)

J.J. Paton, D.V. Buonomano

**The neural basis of timing: distributed mechanisms for diverse functions**

Neuron, 98 (2018), pp. 687-706

[Renda et al., 2014](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0220)

C.R. Renda, J.S. Stein, G.J. Madden

**Impulsive choice predicts poor working memory in male rats**

PLOS ONE, 9 (4) (2014)

[Schlee et al., 2014](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0225)

W. Schlee, M. Schecklmann, A. Lehner, P.M. Kreuzer, V. Vielsmeier, T.B. Poeppl, B. Langguth

**Reduced variability of auditory alpha activity in chronic tinnitus**

Neural Plast., 4 (3614) (2014), p. 6

[Shaffer, 1984](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0230)

H. Shaffer

**Timing and time perception**

N. Y. Acad. Sci., 423 (1984), pp. 420-428

[Simen et al., 2013](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0235)

P. Simen, F. Rivest, E.A. Ludvig, F. Balci, P. Killeen

**Timescale invariance in the pacemaker-accumulator family of timing models**

Timing Time Percept., 1 (2) (2013), pp. 159-188

[Sompolinsky and Kanter, 1986](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0240)

H. Sompolinsky, I. Kanter

**Temporal association in asymmetric neural networks**

Phys. Rev. Lett., 57 (22) (1986)

[Steriade et al., 1993](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0245)

M. Steriade, D.A. McCormick, T.J. Sejnowski

**Thalamocortical oscillations in the sleeping and aroused brain**

Science, 262 (5134) (1993), pp. 679-685

[Tiganj et al., 2017](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0250)

Z. Tiganj, M.W. Jung, J. Kim, M.W. Howard

**Sequential firing codes for time in rodent medial prefrontal cortex**

Cereb. Cortex, 27 (12) (2017), pp. 5663-5671

[Tsao et al., 2018](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0255)

A. Tsao, J. Sugar, L. Lu, C. Wang, J.J. Knierim, M.-B. Moser, E.I. Moser

**Integrating time from experience in the lateral entorhinal cortex**

Nature, 561 (2018), pp. 57-62

[Zeki and Balci, 2019](https://www.sciencedirect.com/science/article/pii/S037663571930124X?via%3Dihub#bbib0260)

M. Zeki, F. Balci

**A simplified model of communication between time cells: accounting for the linearly increasing timing imprecision**

Front. Comput. Neurosci., 12 (2019), p. 111

## Cited by (3)

[View Abstract](https://www.sciencedirect.com/science/article/abs/pii/S037663571930124X)

© 2019 Elsevier B.V. All rights reserved.
