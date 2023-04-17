---
created: 2022-06-08T15:25:59 (UTC +02:00)
tags: []
source: https://www.sciencedirect.com/science/article/pii/S0960982215002055
author: Helen Motanis, Dean V. Buonomano
---

# A Scalable Population Code for Time in the Striatum - ScienceDirect



> ## Excerpt
> To guide behavior and learn from its consequences, the brain must represent time over many scales. Yet, the neural signals used to encode time in the …

---
[![Elsevier logo](https://sdfestaticassets-us-east-1.sciencedirectassets.com/shared-assets/24/images/elsevier-non-solus-new-grey.svg)](https://www.sciencedirect.com/)

-   [View **PDF**](https://www.sciencedirect.com/science/article/pii/S0960982215002055/pdfft?md5=d1436d0b307f132c4b474d42164db408&pid=1-s2.0-S0960982215002055-main.pdf)

[![Journal home page for Current Biology](https://ars.els-cdn.com/content/image/Dcellpress.gif)](https://www.sciencedirect.com/journal/current-biology/vol/25/issue/9)

## Highlights

•

Striatal neurons fire at different times over tens of seconds during timing behavior

•

Response times of striatal neurons rescaled with the interval being timed

•

Time coding by the population predicted timing behavior from trial to trial

•

Striatal neurons multiplexed information about action and time

## Summary

To guide behavior and learn from its consequences, the brain must represent time over many scales. Yet, the neural signals used to encode time in the seconds-to-minute range are not known. The striatum is a major input area of the [basal ganglia](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/basal-ganglia "Learn more about basal ganglia from ScienceDirect's AI-generated Topic Pages") associated with learning and motor function. Previous studies have also shown that the striatum is necessary for normal timing behavior. To address how striatal signals might be involved in timing, we recorded from striatal neurons in rats performing an interval timing task. We found that neurons fired at delays spanning tens of seconds and that this pattern of responding reflected the interaction between time and the animals’ ongoing sensorimotor state. Surprisingly, cells rescaled responses in time when intervals changed, indicating that striatal populations encoded relative time. Moreover, time estimates decoded from activity predicted timing behavior as animals adjusted to new intervals, and disrupting striatal function led to a decrease in timing performance. These results suggest that striatal activity forms a scalable population code for time, providing timing signals that animals use to guide their actions.

-   [**Previous**](https://www.sciencedirect.com/science/article/pii/S0960982215003358)
-   [**Next**](https://www.sciencedirect.com/science/article/pii/S0960982215002237)

## Introduction

To behave adaptively in complex, ever-changing environments, animals must learn which actions to take in a particular context based on their past experience. However, to learn about the sometimes-delayed consequences of actions and to guide future behavior, it is absolutely necessary that the brain represent not only actions and consequences but also temporal information about when those actions and consequences occur \[[1](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib1)\].

Multiple lines of evidence implicate the [basal ganglia](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/basal-ganglia "Learn more about basal ganglia from ScienceDirect's AI-generated Topic Pages") (BG) as a locus for the representation of such temporal information. Lesions of the striatum in rats \[[2](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib2)\], disease states that affect the BG such as Parkinson’s \[[3](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib3)\] and Huntington’s disease \[[4](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib4)\], drugs that affect dopamine (DA) signaling \[[5](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib5)\], and genetic manipulations that affect the DA system in the BG \[[6](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib6)\] all result in interval timing dysfunction. Furthermore, human fMRI studies have found that the striatum, a main input area of the BG, is activated by tasks that involve the processing of interval information \[[7](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib7), [8](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib8)\].

In addition, many theoretical models have been proposed to explain timing behavior. These models can be grouped into at least three categories. Pacemaker-accumulator models integrate pulses emitted from a central pacemaker to measure elapsed time \[[9](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib9), [10](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib10)\]. Beat frequency models detect patterns of activation across resettable oscillatory processes at different frequencies to encode time delays from a resetting event \[[11](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib11)\]. Sequential state models contain orderly transitions between different activity states that can be used to encode time \[[12](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib12), [13](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib13), [14](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib14)\]. These theories reproduce various aspects of timing behavior in many interval timing tasks. However, neural data in conflict or in support of the various theories are lacking.

To understand how time is encoded in neural circuits, we recorded the spiking activity of neurons as rats performed an interval timing task. Specifically, given the apparent localization of timing function in striatal tissue, we asked whether striatal neural activity could encode elapsed time over durations of tens of seconds to 1 min while we measured behavior that reflected animals’ estimates of time.

We found that different striatal neurons fired maximally at different delays from reward receipt and that information about animals’ time estimates could be extracted from striatal populations by simply treating neurons as tuned for time. Importantly, this tuning for time, while affected by sensorimotor event-related neural responses, could not be fully explained by ongoing behavior, as even cells that displayed responses locked to a specific behavior varied their responses depending on when that behavior was executed within a given interval. Strikingly, we found that temporal tuning stretched or contracted, rescaling with the interval being timed. Thus, striatal populations encoded relative time, flexibly adapting to the immediate demands of the environment. Finally, we ran a simple simulation of the task and show that neural responses resembling those we observe in the striatum are suitable as a basis for timing behavior. These results provide important biological insight into how a major brain system encodes time during behavior.

## Results

### Lever Pressing Start Time under Fixed Interval Reinforcement Schedules Is a Behavioral Measure of Rats’ Expectation of Time until Reward

To elicit robust time-dependent behavior over a broad range of timescales, we employed operant conditioning procedures under fixed interval (FI) schedules of reinforcement ([Figure 1](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig1)A). Briefly, rats were placed in a behavioral box containing a lever positioned over a liquid delivery port and were trained to press the lever to receive water reward. Reward delivery triggered a timer, and reward became available again only after the timer exceeded a FI ranging from 12 s to 60 s in multiples of 12 s. Lever presses occurring after reward delivery but before the FI had elapsed were not reinforced. A FI was maintained for between 18 and 40 rewards before changing to another FI, randomly chosen from the interval set.

![](https://ars.els-cdn.com/content/image/1-s2.0-S0960982215002055-gr1.jpg)

1.  [Download : Download high-res image (609KB)](https://ars.els-cdn.com/content/image/1-s2.0-S0960982215002055-gr1_lrg.jpg "Download high-res image (609KB)")
2.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S0960982215002055-gr1.jpg "Download full-size image")

Figure 1. The SFI Task Produces Systematic Changes in Lever PST

(A) Task structure. The following color code will be commonly used: blue represents short FIs, and green represents longer FIs.

(B) Example of lever pressing behavior in a single session of the SFI task. Gray markers indicate a lever press; red markers indicate the PST.

(C) Average lever pressing rate in each of the five FIs, aligned on preceding reward. Dashed lines represent SEM.

(D) Average rate of lever pressing in each block, aligned on PST. Traces are plotted on a solid line for the period for which more than half of the trials contribute data and on a dotted line after that point. Shaded patches along the horizontal axis represent SEM. 1 s bins are indicated in (C) and (D).

(E) Median and interquartile range of PST for each of the five FIs. Smoothed density functions depicting the full distributions of PST are shown on the right.

See also [Figure S1](https://www.sciencedirect.com/science/article/pii/S0960982215002055#app2).

In single sessions, rats tended to distribute lever pressing toward the latter portion of the FI, shifting when they responded as FI changes occurred ([Figures 1](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig1)B and [S1](https://www.sciencedirect.com/science/article/pii/S0960982215002055#app2)A). This pattern of responding produced ramps in block-wise averaged pressing as a function of time that varied in slope in relation to FI ([Figures 1](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig1)C and [S1](https://www.sciencedirect.com/science/article/pii/S0960982215002055#app2)B). However, this did not reflect the pattern of responding in single trials. We asked how pressing evolved after pressing onset (pressing start times, PSTs) in each trial by aligning on the PST and averaging lever press rates across trials and within blocks of the same FI ([Figure 1](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig1)D). Rats pressed at a relatively constant rate after the first press in each trial, with a rate determined by the experienced reward rate ([Figure S1](https://www.sciencedirect.com/science/article/pii/S0960982215002055#app2)C). The ramps in the reward-aligned pressing as a function of time largely result from changing distributions of PSTs ([Figure 1](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig1)E), as these vary systematically with FI, and averaging a group of step functions with onset times drawn from these distributions will produce ramps of varying slope.

This serial fixed interval (SFI) lever pressing task produced systematic variation in the distributions of PSTs of bouts of anticipatory pressing, consistent with previous timing studies employing FI schedules of reinforcement \[[9](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib9)\]. These bouts were of a relatively constant rate that varied with reward rate over time ([Figures 1](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig1)D and [S1](https://www.sciencedirect.com/science/article/pii/S0960982215002055#app2)C). The PST thus provided a behavioral metric that covaried with the animals’ changing expectation about time until the next available reward, which we compared to the activity of neurons recorded in the striatum during performance of the task as described below.

### Striatal Neurons Display Temporal Tuning

In the SFI task, reward delivery is both the timing cue and the reinforcer. Since animals reported knowledge of time between reward availability by when they began to press a lever, we asked whether neuronal responses in the striatum aligned on reward might reveal a signal that animals could use to guide the decision of when to begin pressing. We recorded broadly in the [dorsal striatum](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/dorsal-striatum "Learn more about dorsal striatum from ScienceDirect's AI-generated Topic Pages") so as to sample neurons from regions previously shown to be important for interval timing behavior \[[2](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib2)\] (inset in [Figure S1](https://www.sciencedirect.com/science/article/pii/S0960982215002055#app2)D), and the vast majority of units we recorded exhibited average firing rates of less than five spikes per second, consistent with a population made up of mostly medium spiny projection neurons \[[15](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib15)\] ([Figure S1](https://www.sciencedirect.com/science/article/pii/S0960982215002055#app2)D).

Aligned on reward delivery, the population of recorded cells exhibited a broad distribution of activity patterns, as reflected in the normalized spike density functions (SDFs; see [Supplemental Experimental Procedures](https://www.sciencedirect.com/science/article/pii/S0960982215002055#app2) for details) shown in [Figure 2](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig2)A. Some cells fired just after reward delivery, others fired in the middle of the delay, and others fired leading up to the next reward ([Figures 2](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig2)A, [S2](https://www.sciencedirect.com/science/article/pii/S0960982215002055#app2), and [S3](https://www.sciencedirect.com/science/article/pii/S0960982215002055#app2)). This produced a slow-moving “bump” of activity that traversed the population during each FI. In theory, reading out the location of this bump in the population could provide an estimate of time within the FI. However, a core feature of interval timing behavior is that timing accuracy decreases with the magnitude of the interval being timed \[[9](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib9)\]. Two features of the neural data could potentially contribute to this phenomenon: an increased spread of each neuron’s responses as a function of their peak latency and a decreasing density of neurons displaying peak firing rates as time progresses. We found that the widths of responses were indeed correlated with their latencies to peak firing within each FI ([Figure 2](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig2)B, linear regression, FI 12 s, R = 0.4443, p < 0.001; FI 24 s, R = 0.7563, p < 0.001; FI 36 s R = 0.7188, p < 0.001; FI 48 s, R = 0.5910, p < 0.001; FI 60 s R = 0.4733, p < 0.001; see [Supplemental Experimental Procedures](https://www.sciencedirect.com/science/article/pii/S0960982215002055#app2) for details). In addition, the density of peak firing rate latencies in our population decreased over time within the FI ([Figure 2](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig2)C). Thus, the bump in activity within the striatum population moved progressively slower as the FI wore on. Strikingly, the overall time taken by this bump to traverse the population appeared to scale with the FI ([Figures 2](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig2)A and [S4](https://www.sciencedirect.com/science/article/pii/S0960982215002055#app2)A). To begin to assess apparent scaling of response times, we first selected cells that we had recorded in all five FIs and that maintained their ordinal position within the population when responses within each FI were ordered by firing dynamics \[[16](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib16)\]. Of the 112 neurons recorded in all FIs, we found that 76 neurons (68%) maintained their ordinal position in time across the population (see [Supplemental Experimental Procedures](https://www.sciencedirect.com/science/article/pii/S0960982215002055#app2) for details). The responses of these neurons can be observed in [Figure 2](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig2)A, wherein the position of cells along the y axis is the same across the panels displaying average responses in each of the FIs (for all recorded cells, see [Figure S4](https://www.sciencedirect.com/science/article/pii/S0960982215002055#app2)A).

![](https://ars.els-cdn.com/content/image/1-s2.0-S0960982215002055-gr2.jpg)

1.  [Download : Download high-res image (708KB)](https://ars.els-cdn.com/content/image/1-s2.0-S0960982215002055-gr2_lrg.jpg "Download high-res image (708KB)")
2.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S0960982215002055-gr2.jpg "Download full-size image")

Figure 2. Striatal Neurons Display Variable Responses that Tile Tens of Seconds to 1 Min

(A) SDFs of neurons that maintained their relative ordinal position in time within the population across all five FIs, aligned on reward.

(B) Width of each cell’s response within each FI as a function of latency to peak firing. Colored lines represent the best linear fit to the data.

(C) Histogram of relative peak latencies pooled over all FIs, using data shown in (B).

See also [Figure S2](https://www.sciencedirect.com/science/article/pii/S0960982215002055#app2).

To quantify to what degree responses rescaled, we computed a scale factor for each neuron as the ratio of the center of mass (COM) of the SDF in the 12-s FI over the COM of the SDF in each of the other four FIs ([Figure 3](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig3)A). The distributions of these scale factors were sharper than and significantly different from null distributions generated by shuffling cell identity across FIs and recomputing the scale factors (red distributions in [Figure 3](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig3)A, Kolmogorov-Smirnov test, p < 0.001 for all pairwise comparisons). The medians of these distributions, were the population to have rescaled its responses in direct proportion to the FI, should lie at 1/2, 1/3, 1/4, and 1/5 for the scale factors corresponding to 12/24 s, 12/36 s, 12/48 s, and 12/60 s FIs, respectively. We observed median values of 0.59, 0.39, 0.30, 0.24 for the corresponding distributions, indicating near-proportional rescaling of response times across the recorded striatal population. A more-complete description of the relative scale of responses can be seen in [Figures 3](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig3)B–3E, where the COM of each cell’s SDF in the 12-s FI against each of the other FIs are displayed. These data demonstrate a strong tendency for rescaling of neural responses across the population, suggesting that the state of striatal populations may convey relative elapsed time information scaled to the animal’s estimate of the current behaviorally relevant timescale in the environment. We explore this hypothesis in greater detail below.

![](https://ars.els-cdn.com/content/image/1-s2.0-S0960982215002055-gr3.jpg)

1.  [Download : Download high-res image (270KB)](https://ars.els-cdn.com/content/image/1-s2.0-S0960982215002055-gr3_lrg.jpg "Download high-res image (270KB)")
2.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S0960982215002055-gr3.jpg "Download full-size image")

Figure 3. Striatal Neurons Rescale Their Response Time with FI

(A) Distributions of scale factors obtained by calculating the ratio of the center of mass (COM) of the SDF between the 12-s FI and X-s FI (24 s, 36 s, 48 s, and 60 s, respectively, from blue to green) for each cell. For each distribution of scale factors, a null distribution was generated by shuffling cell identity across FIs and recomputing the scale factors (red).

(B–E) COM of each cell’s SDF in the 12-s FI against each of the other FIs. The black dotted line signifies no change in COM from block to block. The colored dotted line signifies a change in COM that is proportional to the change in FI relative to the 12-s FI.

See also [Figure S3](https://www.sciencedirect.com/science/article/pii/S0960982215002055#app2).

### Striatal Populations Encode Information about Timing Behavior

The above analyses of striatal neural responses indicate a gross correspondence between striatal activity and timing behavior across blocks of trials, suggesting that striatal activity patterns might guide decisions about when to begin pressing the lever during each FI. To test this hypothesis, we applied a decoding approach to data collected from single trials near block transitions, wherein animals systematically changed the time that they began to press the lever. Specifically, we asked three questions. First, we asked whether decoded time estimates covaried with true time. Second, we asked whether systematic errors in estimated time as compared to true time occurred at these block transitions. Lastly, we asked whether any observed errors in time encoding correlated with timing behavior.

We first built a probabilistic decoder to derive an estimate of elapsed time from reward in single trials given the observed spiking response of the population. We focused on the first trials of the 12-s and 60-s FI blocks because these blocks were the shortest and longest FIs employed, respectively. Thus, animals consistently overestimated and underestimated the amount of time remaining until reward as they entered 12-s and 60-s blocks. Briefly, our decoder was constructed as follows. In each of the first seven trials of a block, we counted spikes within defined time bins and asked how likely we were to have observed that number of spikes at each time given the observed distributions of spike counts in trials 8 onward of the corresponding block. This generated a likelihood function for current time, given an observed spike count in each bin, for each individual cell. To derive a measure of the population’s estimate of the likelihood for current time, we multiplied together the individual cells’ likelihood functions. We then took the mean of this likelihood function as our estimate for current time \[[17](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib17)\].

In [Figures 4](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig4)A and 4C, we display decoded estimates as a function of time for the first seven trials of 12-s and 60-s FI blocks. We found that decoded estimates tracked true time but that systematic errors between estimates and true time were present in the first few trials of the 12-s and 60-s FI blocks. This feature can be observed more readily when estimates derived from multiple trials are plotted on the same axes ([Figures 4](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig4)B and 4D, quadratic fits). Initial estimates were relatively slow and fast in the first trials of the 12-s and 60-s FI blocks, respectively, and became more accurate after the first few trials.

![](https://ars.els-cdn.com/content/image/1-s2.0-S0960982215002055-gr4.jpg)

1.  [Download : Download high-res image (1MB)](https://ars.els-cdn.com/content/image/1-s2.0-S0960982215002055-gr4_lrg.jpg "Download high-res image (1MB)")
2.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S0960982215002055-gr4.jpg "Download full-size image")

Figure 4. Single-Trial Estimates of Elapsed Time Decoded from the Population Response Correlate with True Time during Initial Trials of 12-s and 60-s FI Blocks

(A) Decoded population estimates of elapsed time from reward in single trials, for the first seven trials of the 12-s FI block plotted against true time. Red traces indicate the mean of the population likelihood function, and the underlying heatmap indicates the population likelihood function. The last panel shows a seven-trial average likelihood function using the first seven trials of the 12-s block.

(B) Decoded estimates of elapsed time for the first seven trials of the 12-s FI block plotted on the same axis. Curves are quadratic fits to the mean likelihood function of each individual trial (red lines in first seven panels). Red curves represent early trials, and black curves represent later trials.

(C) Same description as in (A), but for the 60-s FI.

(D) Same description as in (B), but for the 60-s FI.

See also [Figure S4](https://www.sciencedirect.com/science/article/pii/S0960982215002055#app2).

Next we asked whether such timing signals may be used by animals to guide timing behavior. We first asked whether errors in decoded time estimates over the first trials of blocks were correlated with timing behavior. We found that the mean PST was significantly correlated with the errors in time estimates derived from the population over the first seven trials of 12-s and 60-s FI blocks ([Figure 5](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig5); FI = 12, R2 = 0.63, p = 0.03; FI = 60, R2 = 0.64, p = 0.03). In the initial trials of the 12-s FI block, rats began pressing late relative to subsequent trials, and likewise, the decoded estimate of time relative to reward ran slow ([Figures 4](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig4)B and [5](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig5)). The first trials of the 60-s FI block showed a similar relationship, yet opposite in direction: the decoded estimate ran quickly in early trials, and rats were early to press ([Figures 4](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig4)D and [5](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig5)). We then tested in two control animals whether manipulating striatal circuitry via bilateral infusions of the GABAa agonist [muscimol](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/muscimol "Learn more about muscimol from ScienceDirect's AI-generated Topic Pages") produced deficits in timing behavior ([Figure S5](https://www.sciencedirect.com/science/article/pii/S0960982215002055#app2)). Indeed, at a dose that rendered rats able to perform the task, muscimol reversibly and significantly diminished the relationship between PST and FI (linear regression, likelihood ratio test, significant effect of treatment, p < 0.001), showing that a normally functioning striatum is critical for normal timing behavior. The consistency between time estimates decoded from striatal populations and trial-by-trial variations in timing behavior at block transitions, together with observed dependence of a normally functioning striatum for normal timing behavior, suggests that the brain uses a population code for time that samples broadly from striatal neurons to guide decisions about when to act.

![](https://ars.els-cdn.com/content/image/1-s2.0-S0960982215002055-gr5.jpg)

1.  [Download : Download high-res image (212KB)](https://ars.els-cdn.com/content/image/1-s2.0-S0960982215002055-gr5_lrg.jpg "Download high-res image (212KB)")
2.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S0960982215002055-gr5.jpg "Download full-size image")

Figure 5. Errors in Decoded Time Predicted Timing Behavior

Mean error between true time and the decoded population estimate in the first seven trials of the 12-s (blue) and 60-s (green) FI blocks. Contiguous trials are connected by solid lines to display the trajectory of the data over trials, and the first trial on each block is indicated by the black arrow. Dashed horizontal gray line represents zero error average decoding as compared to true time. See also [Figure S5](https://www.sciencedirect.com/science/article/pii/S0960982215002055#app2).

### Striatal Neurons Multiplexed Information about Action and Time

Based on previous studies \[[18](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib18), [19](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib19), [20](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib20)\], we expected that striatal neurons would display significant modulation by behaviors during the FI. Could behaviors that accompany task performance fully explain the sequential neural responses we observed? Several features of the data argue against this possibility. Rats consistently licked at the reward port from 0.5 s to 5.5 s after reward delivery ([Figure S4](https://www.sciencedirect.com/science/article/pii/S0960982215002055#app2)B), and yet, our ability to decode time was unaffected by the animal being engaged in a fixed behavior over this time (see initial ∼5 s of decoded time estimates in [Figures 4](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig4)A and 4C). After departing from the reward port, however, it is possible that observed dynamics in neural responses are accounted for by ongoing behaviors. Were this the case, responses related to a particular behavior should not vary depending on when in a trial the rat engaged in that behavior. To identify neurons that were significantly modulated by a measured behavior in our task, we focused on a 2.5-s epoch centered on the PST in each trial. We found that of the 76 neurons displayed in [Figure 2](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig2)A, 31 exhibited significant modulations around the onset of lever pressing. Next, we asked whether spiking observed in time bins aligned on the PST was additionally correlated with the time, relative to the FI, that pressing onset occurred. More than half of pressing onset-modulated neurons (16/31, 52%) displayed a significant correlation between spiking around each press initiation and the relative time that press onset occurred within the FI (Pearson’s linear regression, p < 0.01). [Figures 6](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig6)A–6D show examples of four such neurons from three different animals, all of which vary in their responses around the PST, from none at all to robust firing.

![](https://ars.els-cdn.com/content/image/1-s2.0-S0960982215002055-gr6.jpg)

1.  [Download : Download high-res image (936KB)](https://ars.els-cdn.com/content/image/1-s2.0-S0960982215002055-gr6_lrg.jpg "Download high-res image (936KB)")
2.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S0960982215002055-gr6.jpg "Download full-size image")

Figure 6. Pressing Onset Responsive Neurons Display Sensitivity to the Time Relative to the FIs

(A–D) Four single-neuron peri-stimulus time histograms (top) and raster plots (middle) of 2.5-s epochs aligned on pressing onset event (from three animals; the two first columns display data from two neurons recorded in the same animal and same session). Trials were sorted in ascendant fashion from bottom to top on the vertical axis by the pressing onset time relative to the FI (middle) and grouped into quintiles. Here, the colors from gray to red represent the first to the fifth quintile, respectively (middle and top panels). Bottom panels: correlation between the firing rate of the respective neuron and the time of the pressing onset relative to FI. Each data point is color coded from gray to red for the first to the tenth decile of the relative pressing onset time. Firing rates were extracted from the most modulated 500 ms bin of the four bins surrounding the pressing onset event.

The regression approach described above is only expected to identify neurons that display a monotonic relationship between pressing onset response and the relative time of pressing onset. Other cells may have displayed significant time-dependent modulations in pressing onset response that were not monotonic (for example, see [Figures S2](https://www.sciencedirect.com/science/article/pii/S0960982215002055#app2)B and [S3](https://www.sciencedirect.com/science/article/pii/S0960982215002055#app2)A). To identify such cells, we asked whether the median of distributions of spikes counts, collected around pressing onsets and falling into each of five quintiles of relative PSTs, differed from each other. We found that 53 out of 76 neurons (70%) displayed in [Figure 2](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig2)A exhibited significantly different median spike counts across relative time within the FI (p < 0.01, Kruskal-Wallis). Of these, nine cells were significantly modulated by the onset of lever pressing and were not identified in the linear regression analysis. Overall, only six cells that displayed response modulation around PST did not exhibit additional modulation by relative time in the FI as assessed by linear regression and/or nonparametric testing for median difference in spike count. These results suggest that striatal neurons multiplex information about time and immediate sensorimotor state of the animal and argue strongly against the possibility that the striatal population responses we observed can be explained by purely non-time-related responses to specific sensory or motor components of ongoing behavior.

### A Simple Simulation of Timing Behavior

In order to understand the relationship between the recorded striatal signals and rats’ behavior, we ran a simple simulation that performed the SFI task ([Figure 7](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig7)A). The core of this simulation is comprised of a set of temporal basis functions that were inspired by the diverse single-neuron responses observed in our striatal dataset as well as existing timing and learning models \[[21](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib21), [22](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib22), [23](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib23), [24](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib24)\]. We used the method described in \[[23](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib23)\] to generate temporal bases. Each function was used as a rate function for generating inhomogeneous Poisson spike trains from which time was read out during task performance. Whenever this time readout passed a threshold, presses were produced at a fixed rate. In order to adapt to the changing FIs, we implemented a simple learning rule to update a temporal scale factor for the basis functions depending on the difference between expected time of reward and encoded time at the time of reward delivery. Lastly, to account for our observation that many striatal neurons multiplexed information about action and time, each press produced a response in the temporal bases that was proportional to the product of the original time-dependent rate function at the time of the press and a rate function generated by the press itself. With these elements, we ran the simulation under the conditions contained in the SFI task.

![](https://ars.els-cdn.com/content/image/1-s2.0-S0960982215002055-gr7.jpg)

1.  [Download : Download high-res image (967KB)](https://ars.els-cdn.com/content/image/1-s2.0-S0960982215002055-gr7_lrg.jpg "Download high-res image (967KB)")
2.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S0960982215002055-gr7.jpg "Download full-size image")

Figure 7. A Simple Simulation of Timing Behavior

(A) Firing of striatal neurons was modeled based on receptive fields for the height of a decaying trace that is reset in each trial by reward delivery (top left). This trace can decay faster (solid line) or slower (dotted line) by adjusting the parameter γ. The Gaussian functions (top right) represent receptive fields evenly spaced along the height of the trace function. The trace function was multiplied by the receptive fields to generate rate functions, the levels of which vary across time as the memory trace decays. Spike counts observed within defined time bins were then multiplied by the logarithm of their respective rate functions and summed to compute the population log likelihood function for current time given the population response, from t = 0 to t = FI. The maximum of this likelihood function was used to derive our estimate for current time relative to reward, for each time bin. Decoded time estimates can run faster or slower depending on whether the trace function decays quickly or slowly. For each trial, when the decoded time estimate reached a given threshold (red dotted line), we simulated a probabilistic pressing process. If the decoded estimate runs too slowly, it fails to reach the threshold value for expected reward (blue dotted line) before the current FI elapses, and the reward happens before it was expected (dotted black box), generating a large prediction error that drives appropriate updating of γ in the next trial. If the decoded estimate runs more accurately (solid black box), a small prediction error is generated, and γ is minimally adjusted in the next trial.

(B) Example of simulated lever pressing behavior on the SFI task. Gray markers indicate a lever press; red markers indicate the PST.

(C) SDFs of simulated units ordered by response profile. Each panel corresponds to one FI.

(D) Four single-unit peri-stimulus time histograms of 2.5-s epochs aligned on pressing onset event (top). Trials were grouped in quintiles of the relative PST. The colors from gray to red represent the average firing in the first to the fifth quintile, respectively. The bottom panel shows the correlation between the firing rate of the correspondent unit on the top panel and the PST relative to FI. Each data point is color coded from gray to red for the first to the tenth decile of the relative PST.

See also [Figure S6](https://www.sciencedirect.com/science/article/pii/S0960982215002055#app2).

The simulation produced qualitatively similar behavior to that of rats ([Figures 7](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig7)B and [S6](https://www.sciencedirect.com/science/article/pii/S0960982215002055#app2)) and reproduced the three main features that we observed in striatal neurons: temporal tuning, rescaling of neural responses ([Figure 7](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig7)C), and multiplexing of information about action and time ([Figure 7](https://www.sciencedirect.com/science/article/pii/S0960982215002055#fig7)D). Although simple, the simulation serves as proof of principle that neural activity with the properties that we observe in this study can serve as a basis for timing behavior and suggests candidate computational elements such as a scale factor and temporal error signal for which there might exist functional analogs in the brain.

## Discussion

Time is a fundamental dimension of animals’ experience in the world. As such, it plays an integral role in many brain processes, from perception to motor control to learning and memory formation. What is the role of temporal representation within the [BG](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/basal-ganglia "Learn more about BG from ScienceDirect's AI-generated Topic Pages")? A dominant view supported by a wide range of neurobiological data posits that the BG implements aspects of reinforcement learning (RL) \[[1](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib1), [20](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib20), [25](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib25), [26](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib26), [27](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib27), [28](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib28)\], learning how an organism ought to act in order to maximize reward. However, to learn about the sometimes-delayed consequences of actions and to guide future behavior toward rewarding outcomes, it is absolutely necessary that the brain represent situations and actions through time \[[1](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib1), [29](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib29)\]. Indeed, temporal relations among actions and events contain the causal information that learning systems have evolved to detect through a process sometimes referred to as credit assignment \[[30](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib30)\]. Once credit for the occurrence of predictable events has been assigned, this information must be used to profitably guide the course and timing of action as situations arise. This continuous learning-behaving cycle is what RL algorithms naturally account for \[[29](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib29)\]. Yet, it is not known how the BG, the brain system most often associated with RL, represents temporal relationships over the durations necessary to explain its purported role in animal learning and behavior.

The sequential neural states that we describe in the striatum during timing behavior can provide a unifying view of the BG’s role in timing and RL. These signals are strikingly similar to temporal basis functions proposed in existing learning models as more neurally plausible and efficient representations of time \[[21](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib21), [22](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib22), [23](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib23)\], which we show can be used to generate timing behavior similar to what we observed experimentally. Such models operate by learning a set of weights used in a weighted sum of the temporal bases to construct a moment-by-moment prediction about future events such as expected reward. In theory, a weighted combination of activity patterns in the cortical or thalamic inputs to the striatum could act as such temporal bases and modulate the responses of striatal neurons that we observed.

An important question for future studies concerns the mechanism that generated the striatal dynamics we observed. We find it unlikely, given the duration of the intervals we examined, that striatal dynamics were purely locally generated, although several modeling studies suggest mechanisms for generating sequential activity states using striatum-like circuitry over shorter timescales \[[31](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib31), [32](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib32)\]. Indeed, the signals we use to decode time were affected, but not fully explained by, the ongoing sensorimotor state of the animal. Thus, our decoding approach implicitly endorses a number of prominent interval timing theories, positing that animals may use behavioral \[[12](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib12), [14](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib14)\] or sensory state \[[33](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib33)\] transitions to learn to time events in the environment and their own behavior.

Our data appear most consistent with theoretical models that suggest distributed representations of time encoded by the joint activity of populations of neurons \[[13](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib13)\]. Indeed, the decoder used in the current study assumes that time information may be present in many different neurons. However, we cannot rule out that upstream of the population we recorded in the striatum, other forms of temporal representations may exist. For instance, an accumulating process such as that contained within pacemaker accumulator models \[[9](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib9)\] might act to trigger neurons to become active at different delays as the accumulator passes a series of thresholds.

We show that sequential neural activation in the striatum can be used to encode time on a scale of tens of seconds up to 1 min. These results add to a growing list of studies that demonstrate sequential activation of neurons over multi-second timescales in other brain areas, such as the [hippocampus](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/hippocampus "Learn more about hippocampus from ScienceDirect's AI-generated Topic Pages") \[[34](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib34), [35](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib35)\], the [cerebellum](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/cerebellum "Learn more about cerebellum from ScienceDirect's AI-generated Topic Pages") \[[36](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib36)\], the [parietal cortex](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/parietal-cortex "Learn more about parietal cortex from ScienceDirect's AI-generated Topic Pages") \[[37](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib37)\], and the [prefrontal cortex](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/prefrontal-cortex "Learn more about prefrontal cortex from ScienceDirect's AI-generated Topic Pages") \[[38](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib38), [39](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib39), [40](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib40)\]. Unlike previous studies, we found that many individual striatal neurons exhibited responses that dynamically rescaled with the timing of events in the environment and that this scaling of responses produced changes in time encoding by the population that correlated with timing behavior. Combined with previous studies highlighting the importance of a normally functioning striatum for timing behavior \[[2](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib2), [3](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib3), [4](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib4), [6](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib6)\], the effect of striatal inactivation in the current study, and other work that demonstrated time encoding by striatal populations over shorter timescales \[[41](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib41)\], our results suggest that information about where in time a subject finds itself relative to anticipated events in the environment is present in populations of striatal neurons and is used to guide behavior.

Similar timing signals observed in areas other than the striatum are viewed within the larger context of the functional role of those areas where they were recorded. Timing signals in the hippocampus might endow explicit memories with accurate information about the order and temporal context of events \[[24](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib24)\], and timing signals in the cerebellum might coordinate learned actions at a fine timescale \[[36](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib36)\], while timing signals in [premotor cortex](https://www.sciencedirect.com/topics/neuroscience/premotor-cortex "Learn more about premotor cortex from ScienceDirect's AI-generated Topic Pages") might enable accurate timing of movement in general \[[42](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib42)\]. The striatal neurons we observed appear to multiplex temporal information with other, non-temporal types of information, such as signals related to the ongoing sensorimotor state of the animal and likely other previously identified striatal signals related to actions, motor sequences, or reinforcement \[[19](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib19), [26](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib26), [27](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib27), [28](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bib28)\]. Such multiplexing of temporal and other information in populations of striatal neurons as observed in the current study is likely to be critical to the previously ascribed and often-studied function of the BG in learning and action selection.

## Experimental Procedures

All experiments were in accordance with the European Union Directive 86/609/EEC and approved by the Portuguese Veterinary General Board (Direcção-Geral de Veterinária, project approval 014303 - 0420/000/000/2011). Five male Long-Evans [hooded rats](https://www.sciencedirect.com/topics/biochemistry-genetics-and-molecular-biology/hooded-rat "Learn more about hooded rats from ScienceDirect's AI-generated Topic Pages") were used in the neurophysiological experiments, and two male Long-Evans rats were used for the [muscimol](https://www.sciencedirect.com/topics/agricultural-and-biological-sciences/muscimol "Learn more about muscimol from ScienceDirect's AI-generated Topic Pages") experiments. All isolated units (179 total from 5 rats, 25 R1, 9 R2, 21 R3, 28 R4, 96 R5) recorded for at least three blocks in sessions in which PSTs correlated significantly with FI (p < 0.05) were included in subsequent analyses. All analyses and simulations were performed using custom software in [MATLAB](https://www.sciencedirect.com/topics/biochemistry-genetics-and-molecular-biology/sequest "Learn more about MATLAB from ScienceDirect's AI-generated Topic Pages") (MathWorks). See [Supplemental Experimental Procedures](https://www.sciencedirect.com/science/article/pii/S0960982215002055#app2) for a detailed description of methods and procedures.

## Author Contributions

G.B.M.M. and J.J.P. designed the experiments. G.B.M.M. and S.S. carried out the experiments. G.B.M.M., S.S., and J.J.P. analyzed the data and wrote the manuscript.

## Acknowledgments

We thank Bassam Atallah, Brian Lau, Kenway Louie, Christian Machens, Zachary Mainen, Thiago Gouvêa, Eric DeWitt, Alfonso Renart, and Masayoshi Murakami for critical comments on versions of the manuscript and discussions. We thank the histopathology and vivarium staff from the Champalimaud Scientific and Technological Platforms for support. This work was supported by Champalimaud and Gulbenkian Foundations and fellowships to G.B.M.M. and S.S from the Portuguese Foundation for Science and Technology.

## References

[1](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib1)

W. Schultz, P. Dayan, P.R. Montague

**A neural substrate of prediction and reward**

Science, 275 (1997), pp. 1593-1599

[2](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib2)

W.H. Meck

**Neuroanatomical localization of an internal clock: a functional link between mesolimbic, nigrostriatal, and mesocortical dopaminergic systems**

Brain Res., 1109 (2006), pp. 93-107

[3](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib3)

C. Malapani, B. Rakitin, R. Levy, W.H. Meck, B. Deweer, B. Dubois, J. Gibbon

**Coupled temporal memories in Parkinson’s disease: a dopamine-related dysfunction**

J. Cogn. Neurosci., 10 (1998), pp. 316-331

[4](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib4)

K.C. Rowe, J.S. Paulsen, D.R. Langbehn, K. Duff, L.J. Beglinger, C. Wang, J.J. O’Rourke, J.C. Stout, D.J. Moser

**Self-paced timing detects and tracks change in prodromal Huntington disease**

Neuropsychology, 24 (2010), pp. 435-442

[5](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib5)

A.V. Maricq, R.M. Church

**The differential effects of haloperidol and methamphetamine on time estimation in the rat**

Psychopharmacology (Berl.), 79 (1983), pp. 10-15

[6](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib6)

R.D. Ward, C. Kellendonk, E.H. Simpson, O. Lipatova, M.R. Drew, S. Fairhurst, E.R. Kandel, P.D. Balsam

**Impaired timing precision produced by striatal D2 receptor overexpression is mediated by cognitive and motivational deficits**

Behav. Neurosci., 123 (2009), pp. 720-730

[7](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib7)

S.C. Hinton, W.H. Meck

**Frontal-striatal circuitry activated by human peak-interval timing in the supra-seconds range**

Brain Res. Cogn. Brain Res., 21 (2004), pp. 171-182

[8](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib8)

S.C. Tanaka, K. Doya, G. Okada, K. Ueda, Y. Okamoto, S. Yamawaki

**Prediction of immediate and future rewards differentially recruits cortico-basal ganglia loops**

Nat. Neurosci., 7 (2004), pp. 887-893

[9](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib9)

J. Gibbon

**Scalar expectancy theory and Weber’s law in animal timing**

Psychol. Rev., 84 (1977), pp. 279-325

[10](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib10)

P. Simen, F. Balci, L. de Souza, J.D. Cohen, P. Holmes

**A model of interval timing by neural integration**

J. Neurosci., 31 (2011), pp. 9238-9253

[11](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib11)

W.H. Meck, T.B. Penney, V. Pouthas

**Cortico-striatal representation of time in animals and humans**

Curr. Opin. Neurobiol., 18 (2008), pp. 145-152

[12](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib12)

P.R. Killeen, J.G. Fetterman

**A behavioral theory of timing**

Psychol. Rev., 95 (1988), pp. 274-295

[13](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib13)

D.V. Buonomano, M.M. Merzenich

**Temporal information transformed into a spatial code by a neural network with realistic properties**

Science, 267 (1995), pp. 1028-1030

[14](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib14)

A. Machado, M.T. Malheiro, W. Erlhagen

**Learning to time: a perspective**

J. Exp. Anal. Behav., 92 (2009), pp. 423-458

[15](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib15)

G.J. Gage, C.R. Stoetzner, A.B. Wiltschko, J.D. Berke

**Selective activation of striatal fast-spiking interneurons during choice execution**

Neuron, 67 (2010), pp. 466-479

[16](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib16)

M.N. Geffen, B.M. Broome, G. Laurent, M. Meister

**Neural encoding of rapidly fluctuating odors**

Neuron, 61 (2009), pp. 570-586

[17](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib17)

P. Dayan, L.F. Abbott

**Theoretical Neuroscience**

(Second Edition), MIT Press, Cambridge (2005)

[18](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib18)

J.W. Mink

**The basal ganglia: focused selection and inhibition of competing motor programs**

Prog. Neurobiol., 50 (1996), pp. 381-425

[19](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib19)

X. Jin, R.M. Costa

**Start/stop signals emerge in nigrostriatal circuits during sequence learning**

Nature, 466 (2010), pp. 457-462

[20](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib20)

H. Kim, J.H. Sul, N. Huh, D. Lee, M.W. Jung

**Role of striatum in updating values of chosen actions**

J. Neurosci., 29 (2009), pp. 14701-14712

[21](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib21)

S. Grossberg, N.A. Schmajuk

**Neural dynamics of adaptive timing and temporal discrimination during associative learning**

Neural Netw., 2 (1989), pp. 79-102

[22](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib22)

R.E. Suri, W. Schultz

**A neural network model with dopamine-like reinforcement signal that learns a spatial delayed response task**

Neuroscience, 91 (1999), pp. 871-890

[23](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib23)

E.A. Ludvig, R.S. Sutton, E.J. Kehoe

**Stimulus representation and the timing of reward-prediction errors in models of the dopamine system**

Neural Comput., 20 (2008), pp. 3034-3054

[24](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib24)

M.W. Howard, C.J. MacDonald, Z. Tiganj, K.H. Shankar, Q. Du, M.E. Hasselmo, H. Eichenbaum

**A unified mathematical framework for coding time, space, and sequences in the hippocampal region**

J. Neurosci., 34 (2014), pp. 4692-4707

[25](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib25)

K. Doya

**What are the computations of the cerebellum, the basal ganglia and the cerebral cortex?**

Neural Netw., 12 (1999), pp. 961-974

[26](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib26)

J. Lauwereyns, K. Watanabe, B. Coe, O. Hikosaka

**A neural correlate of response bias in monkey caudate nucleus**

Nature, 418 (2002), pp. 413-417

[27](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib27)

K. Samejima, Y. Ueda, K. Doya, M. Kimura

**Representation of action-specific reward values in the striatum**

Science, 310 (2005), pp. 1337-1340

[28](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib28)

B. Lau, P.W. Glimcher

**Value representations in the primate striatum during matching behavior**

Neuron, 58 (2008), pp. 451-463

[29](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib29)

R.S. Sutton, A.G. Barto

**Reinforcement Learning**

MIT Press, Cambridge (1998)

[30](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib30)

P.D. Balsam, C.R. Gallistel

**Temporal maps and informativeness in associative learning**

Trends Neurosci., 32 (2009), pp. 73-78

[31](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib31)

A. Ponzi, J. Wickens

**Sequentially switching cell assemblies in random inhibitory networks of spiking neurons in the striatum**

J. Neurosci., 30 (2010), pp. 5894-5911

[32](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib32)

G.S. Berns, T.J. Sejnowski

**A computational model of how the basal ganglia produce sequences**

J. Cogn. Neurosci., 10 (1998), pp. 108-121

[33](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib33)

M.B. Ahrens, M. Sahani

**Observers exploit stochastic models of sensory change to help judge the passage of time**

Curr. Biol., 21 (2011), pp. 200-206

[34](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib34)

E. Pastalkova, V. Itskov, A. Amarasingham, G. Buzsáki

**Internally generated cell assembly sequences in the rat hippocampus**

Science, 321 (2008), pp. 1322-1327

[35](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib35)

C.J. MacDonald, K.Q. Lepage, U.T. Eden, H. Eichenbaum

**Hippocampal “time cells” bridge the gap in memory for discontiguous events**

Neuron, 71 (2011), pp. 737-749

[36](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib36)

D.V. Buonomano, M.D. Mauk

**Neural network model of the cerebellum: temporal discrimination and the timing of motor responses**

Neural Comput., 6 (1994), pp. 38-55

[37](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib37)

C.D. Harvey, P. Coen, D.W. Tank

**Choice-specific sequences in parietal cortex during a virtual-navigation decision task**

Nature, 484 (2012), pp. 62-68

[38](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib38)

C.K. Machens, R. Romo, C.D. Brody

**Functional, but not anatomical, separation of “what” and “when” in prefrontal cortex**

J. Neurosci., 30 (2010), pp. 350-360

[39](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib39)

S. Shinomoto, T. Omi, A. Mita, H. Mushiake, K. Shima, Y. Matsuzaka, J. Tanji

**Deciphering elapsed time and predicting action timing from neuronal population signals**

Front. Comput. Neurosci., 5 (2011), p. 29

[40](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib40)

J. Kim, J.W. Ghim, J.H. Lee, M.W. Jung

**Neural correlates of interval timing in rodent prefrontal cortex**

J. Neurosci., 33 (2013), pp. 13834-13847

[41](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib41)

D.Z. Jin, N. Fujii, A.M. Graybiel

**Neural representation of time in cortico-basal ganglia circuits**

Proc. Natl. Acad. Sci. USA, 106 (2009), pp. 19156-19161

[42](https://www.sciencedirect.com/science/article/pii/S0960982215002055#bbib42)

H. Merchant, O. Pérez, W. Zarco, J. Gámez

**Interval tuning in the primate medial premotor cortex as a general timing mechanism**

J. Neurosci., 33 (2013), pp. 9082-9096

## Cited by (201)

Copyright © 2015 Elsevier Ltd. All rights reserved.
