---
type: web article
creationtag: 2022-07-12 14:49
URL: "https://www.nature.com/articles/s41586-022-04894-9"
people: []
infotags: []
project:
citekey: cruzActionSuppressionReveals2022
---

> [!Excerpt] Action suppression reveals opponent parallel control via striatal circuits | Nature
> The direct and indirect pathways of the basal ganglia are classically thought to promote and suppress action, respectively1. However, the observed co-activation of striatal direct and indirect medium spiny neurons2 (dMSNs and iMSNs, respectively) has challenged this view. 
> 
> Here we study these circuits in mice performing an interval categorization task that requires a series of self-initiated and cued actions and, critically, a sustained period of dynamic action suppression. Although movement produced the co-activation of iMSNs and dMSNs in the sensorimotor, dorsolateral striatum (DLS), fibre photometry and photo-identified electrophysiological recordings revealed signatures of functional opponency between the two pathways during action suppression. 
> 
> Notably, optogenetic inhibition showed that ==**DLS circuits were largely engaged to suppress—and not promote—action**==. Specifically, iMSNs on a given hemisphere were dynamically engaged to suppress tempting contralateral action. 
> 
> To understand how such regionally specific circuit function arose, we constructed a ==computational reinforcement learning model== that reproduced key features of behaviour, neural activity and optogenetic inhibition. 
> 
> The model predicted that parallel striatal circuits outside the DLS learned the action-promoting functions, generating the temptation to act. Consistent with this, optogenetic inhibition experiments revealed that dMSNs in the associative, dorsomedial striatum, in contrast to those in the DLS, promote contralateral actions. These data highlight how opponent interactions between multiple circuit- and region-specific basal ganglia processes can lead to behavioural control, and establish a critical role for the sensorimotor indirect pathway in the proactive suppression of tempting actions. 
> 
> Experiments in mice show that direct- and indirect-pathway neurons in the basal ganglia are co-activated during movement but exhibit opposite patterns of activity during the active suppression of movement.

---
## Abstract
***Same as above***

The direct and indirect pathways of the basal ganglia are classically thought to promote and suppress action, respectively[1](https://www.nature.com/articles/s41586-022-04894-9#ref-CR1 "Albin, R. L., Young, A. B. & Penney, J. B. The functional anatomy of basal ganglia disorders. Trends Neurosci. 12, 366–375 (1989)."). However, the observed co-activation of striatal direct and indirect medium spiny neurons[2](https://www.nature.com/articles/s41586-022-04894-9#ref-CR2 "Cui, G. et al. Concurrent activation of striatal direct and indirect pathways during action initiation. Nature 494, 238–242 (2013).") (dMSNs and iMSNs, respectively) has challenged this view. Here we study these circuits in mice performing an interval categorization task that requires a series of self-initiated and cued actions and, critically, a sustained period of dynamic action suppression. Although movement produced the co-activation of iMSNs and dMSNs in the sensorimotor, dorsolateral striatum (DLS), fibre photometry and photo-identified electrophysiological recordings revealed signatures of functional opponency between the two pathways during action suppression. Notably, optogenetic inhibition showed that DLS circuits were largely engaged to suppress—and not promote—action. Specifically, iMSNs on a given hemisphere were dynamically engaged to suppress tempting contralateral action. To understand how such regionally specific circuit function arose, we constructed a computational reinforcement learning model that reproduced key features of behaviour, neural activity and optogenetic inhibition. The model predicted that parallel striatal circuits outside the DLS learned the action-promoting functions, generating the temptation to act. Consistent with this, optogenetic inhibition experiments revealed that dMSNs in the associative, dorsomedial striatum, in contrast to those in the DLS, promote contralateral actions. These data highlight how opponent interactions between multiple circuit- and region-specific basal ganglia processes can lead to behavioural control, and establish a critical role for the sensorimotor indirect pathway in the proactive suppression of tempting actions.

## Main

Adaptive behaviour involves a judicious combination of suppression and production of actions. A predator must suppress its urge to pounce until prey is within reach, just as humans must suppress temptation to secure longer-term rewards.

The basal ganglia are thought to regulate action selection depending on consequences[3](https://www.nature.com/articles/s41586-022-04894-9#ref-CR3 "Schultz, W. in Functions of the Cortico-Basal Ganglia Loop (eds Kimura, M. & Graybiel, A. M.) 31–48 (Springer, 1995)."),[4](https://www.nature.com/articles/s41586-022-04894-9#ref-CR4 "Doya, K. What are the computations of the cerebellum, the basal ganglia and the cerebral cortex? Neural Netw. 12, 961–974 (1999)."). In addition, the inability to balance action production and suppression is associated with disorders that involve the basal ganglia, such as attention deficit hyperactivity disorder (ADHD)[5](https://www.nature.com/articles/s41586-022-04894-9#ref-CR5 "Barkley, R. A. Behavioral inhibition, sustained attention, and executive functions: constructing a unifying theory of ADHD. Psychol. Bull. 121, 65–94 (1997)."), Parkinson’s disease and Huntington’s disease[1](https://www.nature.com/articles/s41586-022-04894-9#ref-CR1 "Albin, R. L., Young, A. B. & Penney, J. B. The functional anatomy of basal ganglia disorders. Trends Neurosci. 12, 366–375 (1989)."). Two major basal ganglia circuits, the direct and the indirect pathways, are thought to promote and suppress actions, respectively[6](https://www.nature.com/articles/s41586-022-04894-9#ref-CR6 "Gerfen, C. R. & Surmeier, D. J. Modulation of striatal projection systems by dopamine. Annu. Rev. Neurosci. 34, 441–466 (2011)."),[7](https://www.nature.com/articles/s41586-022-04894-9#ref-CR7 "Alexander, G. E. & Crutcher, M. D. Functional architecture of basal ganglia circuits: neural substrates of parallel processing. Trends Neurosci. 13, 266–271 (1990)."). 

These two pathways originate in the striatum at direct striatonigral medium spiny neurons (dMSNs) and indirect striatopallidal medium spiny neurons (iMSNs). Although several lines of evidence suggest that there is functional opponency between the two pathways, an apparent discordance between their observed co-activation around movement on the one hand[2](https://www.nature.com/articles/s41586-022-04894-9#ref-CR2 "Cui, G. et al. Concurrent activation of striatal direct and indirect pathways during action initiation. Nature 494, 238–242 (2013)."), and anatomy and cell-type-specific perturbation data suggesting opponent function on the other[8](https://www.nature.com/articles/s41586-022-04894-9#ref-CR8 "Kravitz, A. V. et al. Regulation of parkinsonian motor behaviours by optogenetic control of basal ganglia circuitry. Nature 466, 622–626 (2010)."),[9](https://www.nature.com/articles/s41586-022-04894-9#ref-CR9 "Freeze, B. S., Kravitz, A. V., Hammack, N., Berke, J. D. & Kreitzer, A. C. Control of basal ganglia output by direct and indirect pathway projection neurons. J. Neurosci. 33, 18531–18539 (2013)."), has led to an ongoing debate with regard to their roles in basal ganglia circuit function.

A long-standing, and potentially reconciling, view is that action selection is mediated by competition[10](https://www.nature.com/articles/s41586-022-04894-9#ref-CR10 "Denny-Brown, D. & Yanagisawa, N. The role of the basal ganglia in the initiation of movement. Res. Publ. Assoc. Res. Nerv. Ment. Dis. 55, 115–149 (1976)."),[11](https://www.nature.com/articles/s41586-022-04894-9#ref-CR11 "Mink, J. W. The basal ganglia: focused selection and inhibition of competing motor programs. Prog. Neurobiol. 50, 381–425 (1996)."),[12](https://www.nature.com/articles/s41586-022-04894-9#ref-CR12 "Redgrave, P., Prescott, T. J. & Gurney, K. The basal ganglia: a vertebrate solution to the selection problem? Neuroscience 89, 1009–1023 (1999)."). In this view, combined promotion of motor programs by the direct pathway and suppression by the indirect pathway results in selection. This predicts broad co-activation of the two pathways during action production even as they function in opposition to each other. Notably, this also predicts that sustained suppression of action should preferentially engage the indirect pathway.

To test this hypothesis, we used an interval categorization task[13](https://www.nature.com/articles/s41586-022-04894-9#ref-CR13 "Gouvêa, T. S. et al. Striatal dynamics explain duration judgments. eLife 4, e11386 (2015)."),[14](https://www.nature.com/articles/s41586-022-04894-9#ref-CR14 "Soares, S., Atallah, B. V. & Paton, J. J. Midbrain dopamine neurons control judgment of time. Science 354, 1273–1277 (2016).") that requires a series of self-initiated and cued actions, and critically, a sustained period of dynamic action suppression. We then recorded, manipulated and constructed a computational reinforcement learning model to explain the activity and functions of dMSNs and iMSNs in the DLS of mice during behaviour. ^4gdmip

## Production and suppression of action

Mice performed a time interval categorization task requiring movement suppression during interval presentation (Fig. [1a](https://www.nature.com/articles/s41586-022-04894-9#Fig1)). Rewards were delivered for choices to one side (‘short’ choice) if the presented interval was shorter, and at the opposite side (‘long’ choice) if the interval was longer than a 1.5-s decision boundary.

Categorization of very long and very short intervals was highly accurate (92.1 ± 0.7%, 0.6-s and 2.4-s intervals; mean ± s.e.m.; *n* = 14 mice), but it was more variable for intermediate intervals (Fig. [1b](https://www.nature.com/articles/s41586-022-04894-9#Fig1)). 

Movement speed increased leading to trial initiation, before the mice settled into a period of immobility until the delivery of the second tone (Fig. [1c](https://www.nature.com/articles/s41586-022-04894-9#Fig1)). Failure to maintain position in the initiation port until the second tone led to an error tone and trial termination (36.5 ± 2.1% of all trials; *n* = 14 mice). We refer to these trials as **‘broken fixations’**. Of note, mice often made choices after breaking fixation (52.1 ± 4.9% of broken fixations; *n* = 14 mice). These choices were executed with a similar time course and trajectory to valid choices (Fig. [1d,e](https://www.nature.com/articles/s41586-022-04894-9#Fig1)) and were largely toward the ‘short’ side when breaking early in a trial, and the ‘long’ side late in a trial (Fig. [1f,g](https://www.nature.com/articles/s41586-022-04894-9#Fig1)). The pattern of broken fixations reflected the reward associated with the two choices over time (Fig. [1b,g h](https://www.nature.com/articles/s41586-022-04894-9#Fig1)), consistent with the mice developing a dynamic, latent motor plan that must be suppressed, in which failure to suppress depended on expected reward and led to premature execution of an action.

**Fig. 1: Mice learned to dynamically suppress lateralized actions.**
[![[41586_2022_4894_Fig1_HTML.png]]](https://www.nature.com/articles/s41586-022-04894-9/figures/1)

**a**, Task and event diagram. 
**b**, Bottom, average (black) and individual (grey) performance for mice with photometric recordings (*n* = 14). Top, expected reward and the rectified psychometric fit at 1.5 s. *P*Reward and *P*Long refer to the probability of a rewarded trial and reporting a ‘long’ choice, respectively. 
**c**, Head speed of mice over time, aligned on trial initiation, for single sessions of mice with photometric recordings (2.4-s interval, correct trials). Grey, average of individual mice; black, average of all mice (*n* = 14). The shaded region highlights the period of immobility (0.6 s to 2.4 s after trial initiation) 
**d**, Distribution of choice times: from centre port departure to choice, on valid (black) and broken fixation (green) trials. The inset depicts the median choice times per mouse for valid and broken fixation trials (two-tailed *t*\-test, *P* = 0.155, *t*13 = 1.511; *n* = 14 mice). 
**e**, Comparison of example average nape trajectories on valid (top) and broken fixation (bottom) trials, during choice movements (−0.5 to 1.5 s relative to leaving the centre port), on trials in which mice chose the short (black) or long (grey) nose port. Thinner purple lines depict single trials and circles represent the long (black circle), initiation (orange circle) and short (grey circle) nose ports (see also Extended Data Fig. [8](https://www.nature.com/articles/s41586-022-04894-9#Fig12)). 
**f**, Probability density functions of broken fixations over time during the immobility period, conditioned on subsequent choice at one of the side ports (*n* = 14 mice). 
**g**, Average overall pseudo-performance  of mice with photometric recordings calculated from broken fixation trials. Inset depicts the single-mouse probability of choosing long as a function of breaking fixation before (<1.5 s) or after (>1.5 s) the decision boundary (two-tailed *t*\-test, *P* = 4.87 × 10−8, *t*13 = 11.178, *n* = 14 mice). **h**, Probability density function of broken fixations over time (green) and corresponding hazard rate (black full line). The orange line represents the decision boundary (1.5 s). All error bars and boxes represent mean ± s.e.m. NS, not significant (*P* > 0.05); \*\*\**P* ≤ 0.001.

[Source data](https://www.nature.com/articles/s41586-022-04894-9#MOESM4)

[Full size image](https://www.nature.com/articles/s41586-022-04894-9/figures/1)

## Opposite modulation of the two pathways

To probe the direct and indirect pathways for signs of functional opponency, we recorded the activity of dMSNs and iMSNs in the DLS during task performance using fibre photometry[14](https://www.nature.com/articles/s41586-022-04894-9#ref-CR14 "Soares, S., Atallah, B. V. & Paton, J. J. Midbrain dopamine neurons control judgment of time. Science 354, 1273–1277 (2016)."),[15](https://www.nature.com/articles/s41586-022-04894-9#ref-CR15 "Matias, S., Lottem, E., Dugué, G. P. & Mainen, Z. F. Activity patterns of serotonin neurons underlying cognitive flexibility. eLife 6, e20552 (2017).") (Fig. [2a–d](https://www.nature.com/articles/s41586-022-04894-9#Fig2) and Extended Data Fig. [1a](https://www.nature.com/articles/s41586-022-04894-9#Fig5)). 

In individual mice, the activity of either dMSNs or iMSNs increased around movements, namely trial initiation and choice, consistent with previous observations[2](https://www.nature.com/articles/s41586-022-04894-9#ref-CR2 "Cui, G. et al. Concurrent activation of striatal direct and indirect pathways during action initiation. Nature 494, 238–242 (2013).") (Fig. [2e](https://www.nature.com/articles/s41586-022-04894-9#Fig2) and Extended Data Fig. [2d,e](https://www.nature.com/articles/s41586-022-04894-9#Fig6)). Indeed, the mean activity of the two pathways was indistinguishable around trial initiation (Fig. [2e](https://www.nature.com/articles/s41586-022-04894-9#Fig2)). However, iMSN activity was significantly increased relative to dMSN activity when mice suppressed movement during interval presentation (Fig. [2e](https://www.nature.com/articles/s41586-022-04894-9#Fig2) and Extended Data Fig. [2a](https://www.nature.com/articles/s41586-022-04894-9#Fig6)). We then recorded single units electrophysiologically from the DLS and optogenetically photo-identified iMSNs[16](https://www.nature.com/articles/s41586-022-04894-9#ref-CR16 "Lima, S. Q., Hromádka, T., Znamenskiy, P. & Zador, A. M. PINP: a new method of tagging neuronal populations for identification during in vivo electrophysiological recording. PLoS One 4, e6099 (2009)."). Both photo-identified and non-photo-identified putative MSNs exhibited diverse responses[17](https://www.nature.com/articles/s41586-022-04894-9#ref-CR17 "Jin, X. & Costa, R. M. Start/stop signals emerge in nigrostriatal circuits during sequence learning. Nature 466, 457–462 (2010)."),[18](https://www.nature.com/articles/s41586-022-04894-9#ref-CR18 "Klaus, A. et al. The spatiotemporal organization of the striatum encodes action space. Neuron 96, 949 (2017).") (Fig. [2f](https://www.nature.com/articles/s41586-022-04894-9#Fig2) and Extended Data Fig. [3a](https://www.nature.com/articles/s41586-022-04894-9#Fig7)). Consistent with photometry, the photo-identified iMSN population was significantly enriched for cells that showed increased activity during action suppression (Extended Data Fig. [3b,c](https://www.nature.com/articles/s41586-022-04894-9#Fig7)).

**Fig. 2: Opposite modulation of DLS iMSNs and dMSNs during action suppression.**
[![[41586_2022_4894_Fig2_HTML.png]]](https://www.nature.com/articles/s41586-022-04894-9/figures/2)

**a**, Ca2+ recording strategy. 
**b**, Expression, around 2.1 mm lateral to bregma (ML). GPe, external globus pallidus; SNr, substantia nigra pars reticulata; Str, striatum. **c**,**d**, Example traces (**c**) and trial-aligned normalized photometry (**d**) in a single A2a-Cre (left) and D1-Cre (right) mouse. **e**, Normalized activity (A2a-Cre:iMSN *n* = 8, D1-Cre:dMSN *n* = 6) at 2.4 s (dark trace) and shorter intervals (lighter traces). Colouring: immobility period. Linear mixed model (LMM) two-tailed contrast, iMSN versus dMSN at trial initiation (0:0.6 s): *P* = 0.8065, *t*12.5 = 0.034; *n* = 8 A2a-Cre, *n* = 6 D1-Cre. LMM one-tailed contrast, iMSN versus dMSN during immobility (0.6:2.4 s): *P* = 0.0341, *t*12.5 = 2.004, *n* = 8 A2a-Cre, *n* = 6 D1-Cre. **f**, Example photo-identified units. Top, raster; bottom, peristimulus time histogram. Valid, black; broken fixation, green. FR, firing rate. **g**, Hazard rate of breaking fixation conditioned on choice. **h**, Hemisphere labelling convention. **i**, Normalized activity within hemisphere. LMM two-tailed contrast, pre- versus post-1.5 s: iMSN:CL *P* = 0.0462, *t*12.5 = 2.949, *n* = 8 A2a-Cre; dMSN:CL *P* = 0.0272, *t*12.5 = −3.265, *n* = 6 D1-Cre; iMSN:CS *P* = 0.9275, *t*12.5 = 0.430, *n* = 8 A2a-Cre; dMSN:CS *P* = 0.9988, *t*12.5 = 0.212, *n* = 6 D1-Cre. Correct trials. **j**, Pairwise interhemispheric activity differences (CL–CS, immobility period). **k**, Difference in iMSN photometry derivative (*n* = 16 hemispheres; dashed green line) and activity difference in all activated, photo-identified iMSNs (*n* = 12 units, 2 mice, dashed salmon line) at broken fixations ([Methods](https://www.nature.com/articles/s41586-022-04894-9#Sec7), Extended Data Fig. [4](https://www.nature.com/articles/s41586-022-04894-9#Fig8)). Bars, significance from 0 (two-tailed *t*\-test, *P* ≤ 0.05). **l**, Delay period activity versus difference of activity at broken fixations (\[−0.1:0\] s); photo-identified iMSNs (*n* = 89, from 2 mice), labelled by delay period modulation (*P* = 6.04 × 10−15, *t*87 = −9.43). Error bars and boxes represent mean ± s.e.m. NS, not significant (*P* > 0.05); \**P* ≤ 0.05, \*\**P* ≤ 0.01, \*\*\**P* ≤ 0.001.

[Source data](https://www.nature.com/articles/s41586-022-04894-9#MOESM5)

[Full size image](https://www.nature.com/articles/s41586-022-04894-9/figures/2)

---

The difference in photometric signals from iMSNs and dMSNs grew on average as suppression continued, and we wondered whether the need to suppress action might similarly grow over time. Indeed, after a dip around the decision boundary, the hazard rate of broken fixations rose markedly (Fig. [1h](https://www.nature.com/articles/s41586-022-04894-9#Fig1)). 

Notably, the urge to break and make long choices late in the trial far outweighed the urge to break fixation and make short choices early in the delay period (Fig. [2g](https://www.nature.com/articles/s41586-022-04894-9#Fig2)), perhaps reflecting increasing certainty over time about the ultimate location of reward at the 'long' choice port. This asymmetry in behaviour resembled the observed asymmetry in the relative levels of iMSNs and dMSNs across hemispheres: contralateral to the 'long' port (contra-long, CL; Fig. [2h](https://www.nature.com/articles/s41586-022-04894-9#Fig2)), iMSN and dMSN activity steadily increased and decreased throughout the delay period, respectively (Fig. [2i](https://www.nature.com/articles/s41586-022-04894-9#Fig2) and Extended Data Fig. [2b](https://www.nature.com/articles/s41586-022-04894-9#Fig6)), whereas contralateral to the 'short' port (contra-short, CS; Fig. [2h](https://www.nature.com/articles/s41586-022-04894-9#Fig2)), activity levels in both pathways were relatively constant (Fig. [2i](https://www.nature.com/articles/s41586-022-04894-9#Fig2) and Extended Data Fig. [2c](https://www.nature.com/articles/s41586-022-04894-9#Fig6)).

These data reflect a situation in which the relative levels of activity between the two hemispheres varied over time in opposite directions in the two pathways (Fig. [2j](https://www.nature.com/articles/s41586-022-04894-9#Fig2)). Such observations suggest that basal ganglia circuitry in a particular hemisphere was preferentially recruited to suppress movements to the contralateral direction when, and to the degree that, the mouse was tempted to move in that direction.

Consistent with this, we detected significant downward deviations in the rate of change of photometric signal in iMSNs[19](https://www.nature.com/articles/s41586-022-04894-9#ref-CR19 "Markowitz, J. E. et al. The striatum organizes 3D behavior via moment-to-moment action selection. Cell 174, 44–58 (2018).") preceding broken fixations (Fig. [2k](https://www.nature.com/articles/s41586-022-04894-9#Fig2)). Photo-identified iMSNs that were engaged during action suppression also exhibited significant decreases in firing rate preceding the movement (Fig. [2k](https://www.nature.com/articles/s41586-022-04894-9#Fig2)). By contrast, iMSNs that were not engaged during action suppression increased activity just before broken fixations (Fig. [2l](https://www.nature.com/articles/s41586-022-04894-9#Fig2) and Extended Data Fig. [4b](https://www.nature.com/articles/s41586-022-04894-9#Fig8)). Thus, the biphasic photometric signal that precedes broken fixations may reflect the contribution of two subpopulations of iMSNs. These data show that transient disruption of iMSN activity is associated with the failure to successfully suppress action.

## Opponent functions of the two pathways

To probe the functional importance of neural activity in the two pathways, we next performed a series of optogenetic experiments (Fig. [3](https://www.nature.com/articles/s41586-022-04894-9#Fig3)). We first characterized the effect of ArchT (ref. [20](https://www.nature.com/articles/s41586-022-04894-9#ref-CR20 "Han, X. et al. A high-light sensitivity optical neural silencer: development and application to optogenetic control of non-human primate cortex. Front. Syst. Neurosci. 5, 18 (2011).")) photoinhibition by performing extracellular electrophysiological recordings during a quiet awake state (Extended Data Fig. [5b–d](https://www.nature.com/articles/s41586-022-04894-9#Fig9)). Illumination of striatal tissue produced a rapid and sustained inhibition of putative MSN firing in both iMSN-ArchT and dMSN-ArchT mice, with no evidence for the disinhibition of non-targeted MSNs. By contrast, ChR2-mediated excitation[21](https://www.nature.com/articles/s41586-022-04894-9#ref-CR21 "Nagel, G. et al. Channelrhodopsin-2, a directly light-gated cation-selective membrane channel. Proc. Natl Acad. Sci. USA 100, 13940–13945 (2003).") produced a robust activation of MSNs, but also sustained inhibition in 10–20% of putative MSNs (Extended Data Fig. [3e–h](https://www.nature.com/articles/s41586-022-04894-9#Fig7)). We thus proceeded to examine the behavioural effects of optogenetic inhibition during the task.

**Fig. 3: Optogenetic inhibition of DLS iMSNs, but not dMSNs, disrupted action suppression and selection, whereas inhibition of dMSNs, but not iMSNs, slowed movement.**

[![[41586_2022_4894_Fig3_HTML.png]]](https://www.nature.com/articles/s41586-022-04894-9/figures/3)

**a**,**b**, Viral strategy (**a**) and protocol (**b**) for optogenetic manipulation. **c**, Pattern of transgene expression around 2.1 mm ML. **d**, Overall probability of breaking fixation during iMSN inhibition experiments during laser-on (coloured) and laser-off (black) trials. Light delivery to the DLS was bilateral (yellow) (two-tailed *t*\-test, *P* = 0.022, *t*3 = 4.37; *n* = 4 pairs of hemispheres) or unilateral (*P* = 0.015, *t*7 = 3.21; *n* = 8 hemispheres. Green, contra-short manipulation sessions; purple, contra-long manipulation sessions. **e**, Differences in within-mouse median post-broken fixation choice times, during manipulated (yellow) and non-manipulated (black) trials (two-tailed *t*\-test, *P* = 0.46, *t*4 = −0.817; *n* = 5). **f**, Change in probability, after broken fixation, of choices contralateral to the manipulated hemisphere (Δ*P* = *P*Manipulation − *P*Control, two-tailed *t*\-test, *P* = 0.0003, *t*7 = 6.605; *n* = 8 hemispheres). **g**, Left, histogram of normalized broken fixation counts for control (black outline) and manipulation conditions at the contra-short (green) or contra-long (purple) hemispheres. Right, change in broken fixation probability (Δ*P* = *P*Manipulation − *P*Control; *n* = 12 hemispheres) owing to the inhibition of contra-short (green) or contra-long (purple) hemispheres relative to control trials (see Extended Data Fig. [7](https://www.nature.com/articles/s41586-022-04894-9#Fig11)). **h**–**k**, Same as **d**–**g** but for D1-Cre mice. **h**, Bilateral: two-tailed *t*\-test, *P* = 0.074, *t*3 = 2.689; *n* = 4 pairs of hemispheres; unilateral: *P* = 0.185, *t*11 = 1.413; *n* = 12 hemispheres. **i**, Two-tailed t-test, *P* = 0.005, *t*5 = 4.834; *n* = 6 mice. **j**, Two-tailed *t*\-test, *P* = 0.428, *t*11 = −0.824; *n* = 12 hemispheres. **k**, *n* = 8 hemispheres. All error bars and boxes represent mean ± s.e.m. NS, not significant (*P* > 0.05); \**P* ≤ 0.05, \*\**P* ≤ 0.01, \*\*\**P* ≤ 0.001.

[Source data](https://www.nature.com/articles/s41586-022-04894-9#MOESM6)

[Full size image](https://www.nature.com/articles/s41586-022-04894-9/figures/3)

We delivered light in a random minority of trials (30%) (Fig. [3b](https://www.nature.com/articles/s41586-022-04894-9#Fig3)). Bilateral optogenetic inhibition of iMSNs produced a near-complete inability of mice to suppress movement during interval presentation (Fig. [3d](https://www.nature.com/articles/s41586-022-04894-9#Fig3)). Mice broke fixation on 35 ± 6% (*n* = 4 mice) of non-inhibited trials and on 86 ± 7% of bilateral iMSN inhibition trials and were generally unable to maintain fixation for the longest interval duration. However, broken fixations were unaffected by bilateral inhibition of dMSNs (Fig. [3h](https://www.nature.com/articles/s41586-022-04894-9#Fig3)). During broken fixations followed by a choice, the first 300 ms of movement overlapped with the light delivery (250-ms ramp off plus 50-ms grace period; [Methods](https://www.nature.com/articles/s41586-022-04894-9#Sec7)). We therefore examined whether these movements were affected by the inhibition of DLS iMSNs or dMSNs. We found that inhibition of dMSNs, but not that of iMSNs, significantly increased choice times after broken fixations (Fig. [3e,i](https://www.nature.com/articles/s41586-022-04894-9#Fig3) and Extended Data Fig. [6b](https://www.nature.com/articles/s41586-022-04894-9#Fig10)), consistent with a role specifically for the direct pathway of the DLS in augmenting movement vigour[22](https://www.nature.com/articles/s41586-022-04894-9#ref-CR22 "Turner, R. S. & Desmurget, M. Basal ganglia contributions to motor control: a vigorous tutor. Curr. Opin. Neurobiol. 20, 704–716 (2010)."),[23](https://www.nature.com/articles/s41586-022-04894-9#ref-CR23 "Panigrahi, B. et al. Dopamine Is required for the neural representation and control of movement vigor. Cell 162, 1418–1430 (2015)."),[24](https://www.nature.com/articles/s41586-022-04894-9#ref-CR24 "Dudman, J. T. & Krakauer, J. W. The basal ganglia: from motor commands to the control of vigor. Curr. Opin. Neurobiol. 37, 158–166 (2016).").

Given the observed interhemispheric dynamics in DLS iMSNs (Fig. [2i,j](https://www.nature.com/articles/s41586-022-04894-9#Fig2)), we next assessed whether unilateral iMSN inhibition would disrupt action suppression preferentially when activity in a given hemisphere was most engaged. Indeed, although unilateral iMSN inhibition produced a modest increase in broken fixations (Fig. [3d](https://www.nature.com/articles/s41586-022-04894-9#Fig3)), the timing of broken fixations was systematically related to the laterality of inhibition and neural activity. Mice were more likely to break fixation early or late when iMSNs contralateral to the short or long choice were inhibited, respectively (Fig. [3g](https://www.nature.com/articles/s41586-022-04894-9#Fig3) and Extended Data Fig. [7a,c](https://www.nature.com/articles/s41586-022-04894-9#Fig11)), mirroring the contingency between reward and action over time during a trial, and in correspondence with the pattern of hemispheric dominance that was observed in iMSN activity (Fig. [2j](https://www.nature.com/articles/s41586-022-04894-9#Fig2)). We observed no consistent effects of unilaterally inhibiting dMSNs on the timing of broken fixations (Fig. [3k](https://www.nature.com/articles/s41586-022-04894-9#Fig3) and Extended Data Fig. [7b,d](https://www.nature.com/articles/s41586-022-04894-9#Fig11)).

Finally, given the widely assumed importance of basal ganglia circuits in action selection, we examined whether the inhibition of MSNs affected the choices of mice. Unilaterally inhibiting iMSNs produced an increase in contralateral choices after breaking fixation (Fig. [3f](https://www.nature.com/articles/s41586-022-04894-9#Fig3)), both before and after the decision boundary (Extended Data Fig. [7e](https://www.nature.com/articles/s41586-022-04894-9#Fig11)). Features of these choice movements after unilateral iMSN inhibition were indistinguishable from choices without iMSN inhibition (Extended Data Fig. [8](https://www.nature.com/articles/s41586-022-04894-9#Fig12)). Once again, we did not observe a significant effect of unilateral DLS dMSN inhibition on choice behaviour after broken fixations (Fig. [3j](https://www.nature.com/articles/s41586-022-04894-9#Fig3)), nor when dMSN inhibition was applied during choice (Extended Data Fig. [6b](https://www.nature.com/articles/s41586-022-04894-9#Fig10)). These data, together with the observed interhemispheric dynamics of iMSN activity, show that the indirect pathway in the DLS of a given hemisphere was dynamically engaged to suppress contralateral movements when they would be tempting, and that suppression of specific actions can bias action selection.

## Parallel reinforcement learning model

DLS circuits appeared to be largely engaged to suppress tempting actions, which suggests that the drive to produce those actions originated elsewhere. Plasticity at striatal synapses is thought to underlie the learning of policies—programs for behavioural control that map states to actions within reinforcement learning models[4](https://www.nature.com/articles/s41586-022-04894-9#ref-CR4 "Doya, K. What are the computations of the cerebellum, the basal ganglia and the cerebral cortex? Neural Netw. 12, 961–974 (1999)."),[25](https://www.nature.com/articles/s41586-022-04894-9#ref-CR25 "Sutton, R. S. & Barto, A. G. Reinforcement Learning: an Introduction (MIT Press, 1998)."). If the policy learned by DLS in this task is to suppress movement, we wondered how it is learned. Parallel basal ganglia circuits are known to integrate different types of information[7](https://www.nature.com/articles/s41586-022-04894-9#ref-CR7 "Alexander, G. E. & Crutcher, M. D. Functional architecture of basal ganglia circuits: neural substrates of parallel processing. Trends Neurosci. 13, 266–271 (1990)."), and are proposed to learn distinct types of policies[26](https://www.nature.com/articles/s41586-022-04894-9#ref-CR26 "Bornstein, A. M. & Daw, N. D. Multiplicity of control in the basal ganglia: computational roles of striatal subregions. Curr. Opin. Neurobiol. 21, 374–380 (2011)."), and thus we hypothesized that the suppressive policy of the DLS might arise in response to an action-promoting policy located elsewhere.

We constructed a model containing two sub-agents, the policies of which were combined to perform the interval categorization task ([Methods](https://www.nature.com/articles/s41586-022-04894-9#Sec7)). The model followed an actor–critic architecture, in which prediction errors were used to drive the learning of both state values and action preferences[25](https://www.nature.com/articles/s41586-022-04894-9#ref-CR25 "Sutton, R. S. & Barto, A. G. Reinforcement Learning: an Introduction (MIT Press, 1998).") (Fig. [4a](https://www.nature.com/articles/s41586-022-04894-9#Fig4)). To account for known differences in how dopaminergic prediction errors affect plasticity at dMSN and iMSN synapses[27](https://www.nature.com/articles/s41586-022-04894-9#ref-CR27 "Shen, W., Flajolet, M., Greengard, P. & Surmeier, D. J. Dichotomous dopaminergic control of striatal synaptic plasticity. Science 321, 848–851 (2008)."),[28](https://www.nature.com/articles/s41586-022-04894-9#ref-CR28 "Collins, A. G. E. & Frank, M. J. Opponent actor learning (OpAL): modeling interactive effects of striatal dopamine on reinforcement learning and choice incentive. Psychol. Rev. 121, 337–366 (2014)."),[29](https://www.nature.com/articles/s41586-022-04894-9#ref-CR29 "Gurney, K. N., Humphries, M. D. & Redgrave, P. A new framework for cortico-striatal plasticity: behavioural theory meets in vitro data at the reinforcement-action interface. PLoS Biol. 13, e1002034 (2015)."),[30](https://www.nature.com/articles/s41586-022-04894-9#ref-CR30 "Iino, Y. et al. Dopamine D2 receptors in discrimination learning and spine enlargement. Nature 579, 555–560 (2020)."),[31](https://www.nature.com/articles/s41586-022-04894-9#ref-CR31 "Lee, S. J. et al. Cell-type-specific asynchronous modulation of PKA by dopamine in learning. Nature 590, 451–456 (2021)."), direct and indirect pathways were subject to different learning rules (Fig. [4b](https://www.nature.com/articles/s41586-022-04894-9#Fig4)). 

Critically, the two sub-agents were provided with distinct state representations. The DLS sub-agent agent states resembled the immediate environment, whereas the other ‘X’ sub-agent received a more compact representation. Although not explicitly modelled as such, this compact representation can be viewed as predictive[32](https://www.nature.com/articles/s41586-022-04894-9#ref-CR32 "Dayan, P. Improving generalization for temporal difference learning: the successor representation. Neural Comput. 5, 613–624 (1993)."),[33](https://www.nature.com/articles/s41586-022-04894-9#ref-CR33 "Stachenfeld, K. L., Botvinick, M. M. & Gershman, S. J. The hippocampus as a predictive map. Nat. Neurosci. 20, 1643–1653 (2017)."), encoding states subsequent to the second tone, were it to occur at each moment. Each sub-agent learned action preferences that were then combined to guide action selection ([Methods](https://www.nature.com/articles/s41586-022-04894-9#Sec7)). ^uvsamt

**Fig. 4: A simplified dual agent model reproduces behaviour, neural activity and effects of optogenetic inhibition.**
[![[41586_2022_4894_Fig4_HTML.png]]](https://www.nature.com/articles/s41586-022-04894-9/figures/4)

**a**, Schematic of model. Two critics {*V*L(*s**t*L*)*, *V*X*(s**t*X)} access distinct state representations (*s**t*L given by *K*L(*θ*, *Δθ**i**d*, *τ**i*), and *s**t*X given by *K*X(*θ*, Δ*θ**i**d*). Each critic updates its value and action preference functions {*A*D(*s**t*L,*a**t*), *A*I(*s**t*L,*a**t*), *A*D(*s**t*X,*a**t*), *A*I(*s**t*X,*a**t*)} through filtered versions of the respective reward prediction errors (RPEs) {𝛿*t*L,𝛿*t*X}. Action preference components corresponding to DLS dMSNs and iMSNs, and region X dMSNs and iMSNs receive RPEs filtered by *f*D*(*𝛿*t*L*)*, *f*I(𝛿*t*L), *f*D(𝛿*t**X*) and *f*I(𝛿*t**X*), respectively. **b**, Pathway-specific RPE filter functions. **c**, Choice performance of the model. **d**,**e**, Probability densities (**d**) and hazard rate (**e**) of model broken fixations over time, conditioned on subsequent choice. **f**, Action preference functions corresponding to the direct (blue) and indirect (red) pathways of the DLS sub-agent. **g**, Same as **f** for sub-agent X. **h**, Effect of action preference inhibition of the indirect pathway for the two actions simultaneously or for only short or long (control and manipulated trials shown as black and yellow, respectively). **i**, Histogram of normalized broken fixation counts for control (black outline) and inhibition of short (green) and long (purple) DLS sub-agent indirect-pathway action preferences (see Extended Data Fig. [10](https://www.nature.com/articles/s41586-022-04894-9#Fig14)). **j**, Left axis, Change in probability of a contralateral choice when inhibiting action preferences of the DLS sub-agent indirect pathway (red fill), or the pathway X direct pathway (gold fill), for short (green marker edge) or long (purple marker edge) actions after broken fixations. Right axis, change in probability of choices contralateral to the hemisphere manipulated when inhibiting iMSNs in the DLS (red; reproduced from Fig. [3f](https://www.nature.com/articles/s41586-022-04894-9#Fig3)) or dMSNs in the DMS (blue; two-tailed *t*\-test, *P* = 0.028, *t*11 = −2.528; *n* = 12 hemispheres), after breaking fixation. Boxes represent mean ± s.e.m.

[Source data](https://www.nature.com/articles/s41586-022-04894-9#MOESM7)

[Full size image](https://www.nature.com/articles/s41586-022-04894-9/figures/4)

---

The model learned to make appropriate choices (Fig. [4c](https://www.nature.com/articles/s41586-022-04894-9#Fig4)) and, like the mice, sometimes produced premature choices directed towards the appropriate sides as a function of time (Fig. [4d,e](https://www.nature.com/articles/s41586-022-04894-9#Fig4)). These broken fixations resulted from the X sub-agent producing a drive to make short choices before 1.5 s, and long choices after, constituting an urge to act prematurely (Fig. [4g](https://www.nature.com/articles/s41586-022-04894-9#Fig4)). The DLS sub-agent learned to suppress this urge until the second tone owing to the negative reward prediction errors (RPEs) caused by premature choices. These negative RPEs drove the development of increased suppressive signals in the DLS indirect pathway when the contralateral choice was tempting (Fig. [4f](https://www.nature.com/articles/s41586-022-04894-9#Fig4)). The model thus reproduced multiple features of mouse behaviour as well as the qualitative patterns of overall and interhemispheric activity observed in the mouse DLS.

We next modelled optogenetic inhibition of DLS iMSNs by decrementing the indirect pathway of the DLS sub-agent. As in mice, this led to the failure to suppress action (Fig. [4h](https://www.nature.com/articles/s41586-022-04894-9#Fig4)). Furthermore, inhibiting the 'short' action preference led to failed action suppression early, whereas inhibiting the long action preference led to failed action suppression late, in the delay period (Fig. [4i](https://www.nature.com/articles/s41586-022-04894-9#Fig4) and Extended Data Fig. [10](https://www.nature.com/articles/s41586-022-04894-9#Fig14)). In addition, unilateral inhibition also caused an increase in contralateral action (Fig. [4j](https://www.nature.com/articles/s41586-022-04894-9#Fig4)), as in the experimental data (Fig. [3f](https://www.nature.com/articles/s41586-022-04894-9#Fig3)).

Previous work has shown that the activation of dorsomedial striatum (DMS) MSNs can affect action selection[34](https://www.nature.com/articles/s41586-022-04894-9#ref-CR34 "Tai, L.-H., Lee, A. M., Benavidez, N., Bonci, A. & Wilbrecht, L. Transient stimulation of distinct subpopulations of striatal neurons mimics changes in action value. Nat. Neurosci. 15, 1281–1289 (2012)."). We thus wondered whether more medial striatal circuits might contribute to the action-promoting functions reflected in the X sub-agent. We targeted optogenetic inhibition to the DMS in separate groups of mice. In general, the behavioural effects of inhibiting DMS MSNs were modest and we observed no significant effect of inhibiting either iMSNs or dMSNs in the DMS on action suppression (Extended Data Figs. [6b](https://www.nature.com/articles/s41586-022-04894-9#Fig10) and [9](https://www.nature.com/articles/s41586-022-04894-9#Fig13)). However, we did observe a modest but significant decrease in contralateral choices after broken fixations when inhibiting DMS dMSNs. This effect was opposite in sign to that of inhibiting iMSNs in the DLS, and could be replicated in the model by unilaterally inhibiting the direct pathway of sub-agent X (Fig. [4j](https://www.nature.com/articles/s41586-022-04894-9#Fig4)). This suggests that more medial circuits contributed to an opposing function to that of the DLS, promoting specific movements when they would potentially be rewarded through—at least in part—the action of dMSNs.

## Discussion
Here we show clear activity signatures of functional opponency between neurons that initiate the two major basal ganglia pathways. In particular, we observe opposite patterns of activity in the two pathways in sensorimotor striatum when movements must be proactively and persistently suppressed.

Consistent with these data, functional magnetic resonance imaging in humans and electrophysiology in non-human primates suggest that iMSNs might proactively suppress action[35](https://www.nature.com/articles/s41586-022-04894-9#ref-CR35 "Majid, D. S. A., Cai, W., Corey-Bloom, J. & Aron, A. R. Proactive selective response suppression is implemented via the basal ganglia. J. Neurosci. 33, 13259–13269 (2013)."),[36](https://www.nature.com/articles/s41586-022-04894-9#ref-CR36 "Watanabe, M. & Munoz, D. P. Presetting basal ganglia for volitional actions. J. Neurosci. 30, 10144–10157 (2010)."),[37](https://www.nature.com/articles/s41586-022-04894-9#ref-CR37 "Ford, K. A. & Everling, S. Neural activity in primate caudate nucleus associated with pro- and antisaccades. J. Neurophysiol. 102, 2334–2341 (2009)."),[38](https://www.nature.com/articles/s41586-022-04894-9#ref-CR38 "Amita, H. & Hikosaka, O. Indirect pathway from caudate tail mediates rejection of bad objects in periphery. Sci. Adv. 5, eaaw9297 (2019)."). Leveraging genetic access to iMSNs and dMSNs in mice, our data show not only that iMSNs in the DLS contributed to action suppression, but that iMSNs, and not dMSNs, were necessary for it. In addition, action suppression relied on iMSNs in a given hemisphere at different points in time depending on task demands, indicating that subpopulations of iMSNs can be deployed to dynamically shape suppression, although we cannot rule out the possibility that a minority of basal ganglia outputs directed contralaterally might allow iMSNs to promote ipsilateral actions as well[39](https://www.nature.com/articles/s41586-022-04894-9#ref-CR39 "Parent, A. & De Bellefeuille, L. Organization of efferent projections from the internal segment of globus pallidus in primate as revealed by flourescence retrograde labeling method. Brain Res. 245, 201–213 (1982)."),[40](https://www.nature.com/articles/s41586-022-04894-9#ref-CR40 "Lee, J. & Sabatini, B. L. Striatal indirect pathway mediates exploration via collicular competition. Nature 599, 645–649 (2021)."). Although several studies have observed the co-activation of dMSNs and iMSNs around movement[2](https://www.nature.com/articles/s41586-022-04894-9#ref-CR2 "Cui, G. et al. Concurrent activation of striatal direct and indirect pathways during action initiation. Nature 494, 238–242 (2013)."),[19](https://www.nature.com/articles/s41586-022-04894-9#ref-CR19 "Markowitz, J. E. et al. The striatum organizes 3D behavior via moment-to-moment action selection. Cell 174, 44–58 (2018)."),[41](https://www.nature.com/articles/s41586-022-04894-9#ref-CR41 "Tecuapetla, F., Matias, S., Dugue, G. P., Mainen, Z. F. & Costa, R. M. Balanced activity in basal ganglia projection pathways is critical for contraversive movements. Nat. Commun. 5, 4315 (2014)."), a finding we reproduce (Extended Data Fig. [2d,e](https://www.nature.com/articles/s41586-022-04894-9#Fig6)), transient decorrelation of activity has been reported around transitions between actions in a sequence[19](https://www.nature.com/articles/s41586-022-04894-9#ref-CR19 "Markowitz, J. E. et al. The striatum organizes 3D behavior via moment-to-moment action selection. Cell 174, 44–58 (2018)."). Given our data, we hypothesize that decorrelation may arise when the brain must largely suppress actions at behavioural transitions.

Notably, recovery of function in an experimental model of Parkinson’s disease has been associated with a return to near normal levels of iMSN but not dMSN activity, consistent with some primacy for the sensorimotor indirect pathway in action production[42](https://www.nature.com/articles/s41586-022-04894-9#ref-CR42 "Parker, J. G. et al. Diametric neural ensemble dynamics in parkinsonian and dyskinetic states. Nature 557, 177–182 (2018)."). Together with our data, these results suggest that the indirect pathway can be configured in sensorimotor striatum as an inhibitory mask, specifying which actions not to produce, whereas the sensorimotor direct pathway provides a gain signal, and not an action selection signal[11](https://www.nature.com/articles/s41586-022-04894-9#ref-CR11 "Mink, J. W. The basal ganglia: focused selection and inhibition of competing motor programs. Prog. Neurobiol. 50, 381–425 (1996)."). Both pathways were more active around movements toward the contralateral side (Extended Data Fig. [2d,e](https://www.nature.com/articles/s41586-022-04894-9#Fig6)), which suggests that suppressing and promoting signals may be targeted towards nearby regions in action space, perhaps by mechanisms in other brain systems such as the cortex, thalamus and cerebellum[11](https://www.nature.com/articles/s41586-022-04894-9#ref-CR11 "Mink, J. W. The basal ganglia: focused selection and inhibition of competing motor programs. Prog. Neurobiol. 50, 381–425 (1996)."),[43](https://www.nature.com/articles/s41586-022-04894-9#ref-CR43 "Park, J., Coddington, L. T. & Dudman, J. T. Basal ganglia circuits for action specification. Annu. Rev. Neurosci. 43, 485–507 (2020)."), or circuits that involve other striatal regions.

Finally, we present a computational model to explain how patterns of neural activity arise in the DLS in relation to revealed function, as well as apparently opponent roles between more associative and more sensorimotor circuits. The basal ganglia contain parallel circuitry, carrying sensorimotor, associative and limbic information through their main axis in a largely segregated manner[7](https://www.nature.com/articles/s41586-022-04894-9#ref-CR7 "Alexander, G. E. & Crutcher, M. D. Functional architecture of basal ganglia circuits: neural substrates of parallel processing. Trends Neurosci. 13, 266–271 (1990)."),[44](https://www.nature.com/articles/s41586-022-04894-9#ref-CR44 "Alexander, G. E., DeLong, M. R. & Strick, P. L. Parallel organization of functionally segregated circuits linking basal ganglia and cortex. Annu. Rev. Neurosci. 9, 357–381 (1986)."),[45](https://www.nature.com/articles/s41586-022-04894-9#ref-CR45 "Prescott, T. J., Montes González, F. M., Gurney, K., Humphries, M. D. & Redgrave, P. A robot model of the basal ganglia: behavior and intrinsic processing. Neural Netw. 19, 31–61 (2006)."),[46](https://www.nature.com/articles/s41586-022-04894-9#ref-CR46 "Lau, B., Monteiro, T. & Paton, J. J. The many worlds hypothesis of dopamine prediction error: implications of a parallel circuit architecture in the basal ganglia. Curr. Opin. Neurobiol. 46, 241–247 (2017)."). Although different control functions have been proposed for parallel circuits, emphasis within theoretical accounts is usually placed on arbitrating between types of control depending on the context; for example, between model-based and model-free[47](https://www.nature.com/articles/s41586-022-04894-9#ref-CR47 "Daw, N. D., Niv, Y. & Dayan, P. Uncertainty-based competition between prefrontal and dorsolateral striatal systems for behavioral control. Nat. Neurosci. 8, 1704–1711 (2005)."), or Pavlovian versus instrumental control[48](https://www.nature.com/articles/s41586-022-04894-9#ref-CR48 "Dorfman, H. M. & Gershman, S. J. Controllability governs the balance between Pavlovian and instrumental action selection. Nat. Commun. 10, 5826 (2019)."). Our model highlights that parallel circuits may also learn distinct control signals that interact with each other in their development. This creates a situation within a single brain akin to a multi-agent reinforcement learning scenario: the policy of individual agents depends on both the environment and the policies of the other agents. Once there are multiple, parallel drives on behaviour, many of which may be anticipatory and conflicting[49](https://www.nature.com/articles/s41586-022-04894-9#ref-CR49 "Dayan, P., Niv, Y., Seymour, B. & Daw, N. D. The misbehavior of value and the discipline of the will. Neural Netw. 19, 1153–1160 (2006)."), the system may require a mechanism to suppress action. We note that such a parallel, multi-process view of basal ganglia function may provide a natural explanation for the existence of a suppressive indirect pathway, linking reinforcement-learning-based control to more classic proposals concerning basal ganglia circuit function[11](https://www.nature.com/articles/s41586-022-04894-9#ref-CR11 "Mink, J. W. The basal ganglia: focused selection and inhibition of competing motor programs. Prog. Neurobiol. 50, 381–425 (1996).").

## Methods

### Mice

Adult (over 2 months) male and female mice, aged 2 to 12 months, of the A2a:cre (KG139)[50](https://www.nature.com/articles/s41586-022-04894-9#ref-CR50 "Gerfen, C. R., Paletzki, R. & Heintz, N. GENSAT BAC cre-recombinase driver lines to study the functional organization of cerebral cortical and basal ganglia circuits. Neuron 80, 1368–1383 (2013)."), D1:cre (EY217)[50](https://www.nature.com/articles/s41586-022-04894-9#ref-CR50 "Gerfen, C. R., Paletzki, R. & Heintz, N. GENSAT BAC cre-recombinase driver lines to study the functional organization of cerebral cortical and basal ganglia circuits. Neuron 80, 1368–1383 (2013).") and Ai32 (RCL-ChR2(H134R)/EYFP)[51](https://www.nature.com/articles/s41586-022-04894-9#ref-CR51 "Madisen, L. et al. A toolbox of Cre-dependent optogenetic transgenic mice for light-induced activation and silencing. Nat. Neurosci. 15, 793–802 (2012).") lines were used for this study under the protocol approved by the Champalimaud Foundation Animal Welfare Body (protocol number: 2017/013), the Portuguese Veterinary General Board (Direcção-Geral de Veterinária, project approval 0421/000/000/2018) and in accordance with the European Union Directive 2010/63/EEC. Mice were group-housed before surgical procedures and single-housed after surgery in an inverted 12-h dark–light cycle at 21 °C and 50% humidity. Mice were maintained under water deprivation for all behavioural experiments (>80% body weight from baseline ad libitum period before deprivation). Experimenters were not blind to the genotype of the mice.

### Behavioural apparatus

The behavioural box (20 × 17 × 19 cm) contained three nose ports and a speaker. The behavioural box consisted of three front walls (135° angle between the centre and the side walls), two side walls and a back wall with a 90° angle between them. Each of the three front walls contained a nose port equipped with an infrared emitter–sensor pair to access port entry and exit times. The central nose port was defined as the trial initiation port, and choices were reported at the lateral nose ports. For correct trials, a 4–6-µl calibrated water reward was delivered using a solenoid valve. Tones were delivered through a speaker mounted on the centre wall. All sensors and effectors in the behavioural box were read and controlled using a microprocessor (Arduino Mega 2560, Arduino) through a custom circuit board. The task was implemented by the microprocessor, which outputted data through a serial communication port to a desktop computer running custom Python-based software. High-speed video was acquired at 120 fps and 640 × 480-pixel resolution (FL3-U3-13S2, FLIR) using Bonsai[52](https://www.nature.com/articles/s41586-022-04894-9#ref-CR52 "Lopes, G. et al. Bonsai: an event-based framework for processing and controlling data streams. Front. Neuroinform. 9, 7 (2015).").

### Behavioural task

Mice were trained to categorize interval durations as either short or long by performing right and left choices as previously described[14](https://www.nature.com/articles/s41586-022-04894-9#ref-CR14 "Soares, S., Atallah, B. V. & Paton, J. J. Midbrain dopamine neurons control judgment of time. Science 354, 1273–1277 (2016)."). In brief, mice self-initiated trials by entering the central nose port, triggering the delivery of a pair of tones (7,500 Hz, 150 ms) separated by one of six randomly uniformly sampled selected intervals (0.6, 1.05, 1.26, 1.74, 1.95 and 2.4 s or 0.6, 1.26, 1.38, 1.62, 1.74 and 2.4 s). Stable performance was usually achieved after three to four months of training. Trial availability was not signalled to the mouse but inter-trial onset interval was kept constant within each mouse (7–8 s). Thus, initiation port entries before the point that a trial became available were ineffectual. After the first tone was presented, mice were required to maintain interruption of the centre nose port infrared beam until the second tone was delivered; we refer to this action as 'fixation' throughout the text. If the mouse departed the port before the second tone, an error tone (150 ms of white noise) was played and the next trial availability delayed (time-out). We refer to these trials as ‘broken fixations’. To prevent incorrectly flagging trials as broken fixations owing to sporadic state transitions in the infrared beam, we only counted a trial as a broken fixation after the beam had been continuously uninterrupted for 50 ms. After both tones were played, mice reported their judgements by entering one of the two laterally located nose ports over the next 10 s. For intervals shorter than a 1.5-s category boundary, responses were reinforced at one of the lateral ports. For intervals longer than 1.5 s, responses were reinforced at the opposite port. Incorrect responses were followed by a burst of white noise (150 ms) and a time-out (12–18-s inter-trial onset interval). The short–long versus right–left contingencies were counterbalanced across mice. Therefore, we adopt the nomenclature of contra-short–contra-long (or ipsi-long–ipsi-short, respectively) hemisphere throughout the paper. Sessions typically lasted 2 h.

Psychometric functions were fit using a four-parameter logistic function:

$$P\\left(x\\right)=\\left(u-l\\right)\\times \\frac{{{\\rm{e}}}^{\\frac{x-b}{s}}}{{1+{\\rm{e}}}^{\\frac{x-b}{s}}}+l,$$

where *P* is the performance of the mouse on interval *x*, *u* and *l* the upper and lower asymptote of the curve, respectively, *b* the bias parameter and *s* the slope parameter.

We excluded broken fixation trials before 100 ms, as these often reflected the failure of mice to properly settle in the initiation port and rarely resulted in a subsequent choice on one of the side ports.

To calculate hazard (*H*(*k*)) of breaking fixation at a particular time bin *k* (defined between *t* and *t* *+* Δ*t*), we used the following equation:

$$H\\left(k\\right)=\\,\\frac{B(k)}{{\\sum }\_{j=k}^{T}B\\left(j\\right)+\\,{\\sum }\_{j=k}^{T}C\\left(j\\right)\\,},\\,t < k < t+\\bigtriangleup t,$$

where *B*(*k*) is the number of broken fixation trials that occurred between *t* and *t* *+* Δ*t*, \\({\\sum }\_{j=k}^{T}B(j)\\) the sum of all broken fixations that occurred in the time greater or equal to *t*, up until the longest possible interval *T* (2.4 s), and \\({\\sum }\_{j=k}^{T}C(j)\\) the sum of all completed trials that occurred from time *t* until *T*.

### Viral injections and fibre implantation

All surgeries were performed with mice under isoflurane anaesthesia (1–2% at 0.8 l min−1). We stereotaxically targeted the DLS (coordinates below) bilaterally for all viral deliveries.

After achieving stable performance (usually > 3 months), mice were allowed to regain baseline weight and were subjected to viral injection and fibre implantation in the same surgery. Mouse health was assessed daily and after at least five days, the water deprivation regime was reinstated. To make sure that subject mice recovered their pre-surgery performance before data collection sessions (photometry or optogenetics), they were gradually retrained in the task without and then with fibres attached. After reaching stable performance (1–2 weeks), data collection began. We alternated recorded or manipulated hemispheres every day.

For fibre photometry experiments, we combined mouse lines expressing Cre recombinase in either dMSNs (D1-Cre, EY217Gsat line) or iMSNs (A2a-Cre, KG139Gsat line) with Cre-dependent viral expression of the calcium indicator GCaMP6f (ref. [53](https://www.nature.com/articles/s41586-022-04894-9#ref-CR53 "Chen, T.-W. et al. Ultrasensitive fluorescent proteins for imaging neuronal activity. Nature 499, 295–300 (2013).")). Mice were injected with 300 nl of a mixture of two viruses: AAV1-Syn-Flex-GCaMP6f (titre around 1 × 1013 gc ml−1; University of Pennsylvania Vector Core) and AAV1-CAG-Flex-tdTomato (titre around 0.5 × 1012 gc ml−1; University of Pennsylvania Vector Core), at a 5:1 ratio, in DLS striatum (single injection, AP (0.5 mm anterior–posterior (AP), 2.1 mm ML,) 2.6 mm dorso–ventral (DV) from pia) using an automated-microprocessor-controlled microinjection pipette with micropipettes pulled from borosilicate capillaries (Nanoject II, Drummond Scientific). Injections were performed at 0.2 Hz with 2.3 nl injection volumes per pulse. For all injections, the micropipette was kept at the injection site 10 min before withdrawal. After injection, we implanted, bilaterally, 2 fibres (MFC\_200/245-0.53\_ZF1.25(G)\_FLT, Doric Lenses) 200 µm above the injection site.

For optogenetic inhibition experiments, we combined the same Cre lines that were used to label MSNs in the photometry experiments with Cre-dependent viral expression of the light-activated proton pump ArchT (ref. [20](https://www.nature.com/articles/s41586-022-04894-9#ref-CR20 "Han, X. et al. A high-light sensitivity optical neural silencer: development and application to optogenetic control of non-human primate cortex. Front. Syst. Neurosci. 5, 18 (2011).")) and implanted tapered optical fibres[54](https://www.nature.com/articles/s41586-022-04894-9#ref-CR54 "Pisanello, F. et al. Dynamic illumination of spatially restricted or large brain volumes via a single tapered optical fiber. Nat. Neurosci. 20, 1180–1188 (2017).") in the dorsolateral, or dorsomedial, striatum to enable inhibition of iMSN or dMSN activity. For each hemisphere in the DLS, we made two injections of AAV5-CAG-FLEX-ArchT-tdTomato (titre 1013 gc ml−1, Addgene) (500 nl, AP 0.5 mm, ML 2.1 mm, DV 2.7 mm and 3.1 mm from bregma) and implanted one fibre (Lambda-B fibre 200-μm core, 0.39 NA, 1.5 mm emitting length, Optogenix) near the injection site (AP 0.5 mm, ML 2.1 mm, DV 3.5 mm from bregma). We used an identical protocol for DMS inhibition but targeting AP 0.7 mm, ML 1.3 mm, DV 3.4 mm.

### Fibre photometry

The photometry apparatus was adapted from a previous study[15](https://www.nature.com/articles/s41586-022-04894-9#ref-CR15 "Matias, S., Lottem, E., Dugué, G. P. & Mainen, Z. F. Activity patterns of serotonin neurons underlying cognitive flexibility. eLife 6, e20552 (2017)."). For all experiments, a single blue laser was coupled to a patchcord (100 µm core diameter, 0.22 NA) and connected to a collimator adapter (EFL 4.5 mm, NA 0.50) and a neutral density filter. Dichroic mirrors were fixed inside the main unit, allowing for 473 nm light delivery and GCaMP6f and tdTomato fluorescence detection. The 473-nm light was coupled into a patchcord (200 µm core diameter, 0.48 NA) using a lens (EFL 4.5 mm, NA 0.50) and a rotatory joint. The patchcord was mated to one of two chronically implanted optical fibres (200 µm core diameter, 0.48 NA). Laser intensities at the patchcord tip, before mating to the chronically implanted fibre, were 15–40 μW. For detection of GCaMP6f fluorescence, light was collected by the lens, transmitted and reflected by the dichroics before final filtering and focusing into a photodetector. For detection of tdTomato fluorescence, light was collected by the lens and transmitted through all dichroics before final filtering and focusing into a second photodetector. Photodetector output was digitized at 1 kHz (PCIe 6351, National Instruments) and recorded using custom software in Bonsai[52](https://www.nature.com/articles/s41586-022-04894-9#ref-CR52 "Lopes, G. et al. Bonsai: an event-based framework for processing and controlling data streams. Front. Neuroinform. 9, 7 (2015).").

### Fibre photometry data analysis

All photometry data analysis was performed with custom MATLAB (Mathworks) software. Raw data were downsampled to 100 Hz and low-pass-filtered at 20 Hz. Slow fluctuations were removed by subtracting a fitted polynomial to the raw signal (order < 5). For each session, Δ*F*/*F* was calculated for both channels as Δ*F*/*F**t* = (*F**t* − *F*0)/*F*0, where *F*0 was calculated as the 10th lower percentile from the filtered signal. Similarly to previously[14](https://www.nature.com/articles/s41586-022-04894-9#ref-CR14 "Soares, S., Atallah, B. V. & Paton, J. J. Midbrain dopamine neurons control judgment of time. Science 354, 1273–1277 (2016)."), robust regression using GCaMP6f and tdTomato Δ*F*/*F* was performed and the coefficient estimates were used to calculate a predicted GCaMP6f Δ*F*/*F* based on the observed tdTomato Δ*F*/*F*. This predicted GCaMP6f Δ*F*/*F* was then subtracted to the observed GCaMP6f Δ*F*/*F* to calculate the corrected Δ*F*/*F*. To compare across sessions, each session’s corrected Δ*F*/*F* was *z*\-scored using the mean and standard deviation calculated from a baseline period (5 to 2 s before trial onset). Signals for individual trials were then re-zeroed by subtracting the average of a period of 5 to 2 s before trial onset.

To compare the rate of change of activity aligned to broken fixations to time-matched valid trials (Fig. [2k](https://www.nature.com/articles/s41586-022-04894-9#Fig2)) we began by calculating the first derivative of the corrected Δ*F*/*F* for each trial. For each broken fixation trial, we aligned the trace to the timestamp of the broken fixation and, to compare to a time-matched valid trial, we cropped the average trace of all valid trials to the same length and aligned to the time of the broken fixation. We repeated this process for all broken fixation trials, yielding a broken fixation and respective control, time-matched dataset of trials (see Extended Data Fig. [4c](https://www.nature.com/articles/s41586-022-04894-9#Fig8)).

### Acute recordings and analysis

To confirm the ability to inhibit MSNs, we performed acute recordings in the dorsal striatum of untrained mice. In brief, similarly to trained mice, we virally expressed ArchT in D1-Cre or A2a-Cre mice. After 3–5 weeks of viral expression, we implanted a small headpost and a ground pin contralateral to the recorded hemisphere. After allowing mice to recover, a small round craniotomy (1.5 mm diameter) was opened over the same coordinates as the virus injection. Recordings were performed while mice were head-restrained using custom built headbar holders and on top of a passively rotatable cylinder.

A silicon probe (ASSY 77-H2, Cambridge NeuroTech) with a tapered optical fibre glued to the back, identical to the one used for optogenetic inhibition during behaviour, was slowly lowered into the dorsal striatum. Electrophysiology and laser modulation data were digitized at 30 kHz with the Open Ephys acquisition board[55](https://www.nature.com/articles/s41586-022-04894-9#ref-CR55 "Siegle, J. H. et al. Open Ephys: an open-source, plugin-based platform for multichannel electrophysiology. J. Neural Eng. 14, 045003 (2017).") and acquired with Bonsai[52](https://www.nature.com/articles/s41586-022-04894-9#ref-CR52 "Lopes, G. et al. Bonsai: an event-based framework for processing and controlling data streams. Front. Neuroinform. 9, 7 (2015).").

Every 10 to 25 s, an interval was drawn from the set \[0.60,1.05,1.95, 2.40\] s and light was continuously delivered during that duration. The range of power used was identical to that used during the task and, similarly, was ramped off for 250 ms after the drawn delay had elapsed.

In a second batch of mice, we tested the extent of excitation and inhibition when activating MSNs using ChR2. To achieve ChR2 expression we virally expressed ChR2 (AAV9-EF1a-double floxed-hChR2(H134R)-EYFP-WPRE-HGHpA). Light intensity was set to 0.5–1 mW at the end of the fibre. The remainder of the protocol was identical.

Electrophysiology data were sorted using Kilosort2 ([https://github.com/MouseLand/Kilosort](https://github.com/MouseLand/Kilosort)) and manually curated using Phy ([https://github.com/cortex-lab/phy](https://github.com/cortex-lab/phy)).

Spike rates were calculated by binning raw spike counts in 20-ms bins.

Cells that fired, on average, less than 1/2.4 spikes s−1 (detection limit during inhibition) during the baseline period were excluded from analysis.

To determine whether a cell was modulated, we compared the firing rate in a baseline period before light delivery (−3 to −1 s) to the average firing rate during the stimuli. We computed a *t*\-test per cell and considered a cell to be significantly modulated if *P* ≤ 0.05.

To classify units as putative MSNs, we used previously described criteria[56](https://www.nature.com/articles/s41586-022-04894-9#ref-CR56 "Benhamou, L., Kehat, O. & Cohen, D. Firing pattern characteristics of tonically active neurons in rat striatum: context dependent or species divergent? J. Neurosci. 34, 2299–2304 (2014)."),[57](https://www.nature.com/articles/s41586-022-04894-9#ref-CR57 "Yael, D. et al. Haloperidol-induced changes in neuronal activity in the striatum of the freely moving rat. Front. Syst. Neurosci. 7, 110 (2013).") based on firing statistics and spike waveform morphology. We classified units as putative MSNs if the baseline firing rate was less than 10 Hz, the coefficient of variation was greater than 1.4 and the waveform duration was greater than 500 ms (Extended Data Fig. [5a](https://www.nature.com/articles/s41586-022-04894-9#Fig9)).

### Chronic recordings during task performance and analysis

To record from photo-identified indirect-pathway MSNs, we crossed A2a-Cre mice with Ai32 (ChR2 reporter line). These mice were trained in an identical manner to the mice that were used for photometry recordings and optogenetics manipulation. Once stable performance was achieved, we stopped the water deprivation protocol and allowed mice to recover their baseline weight. In the days before and after surgery we also supplemented their water with minocycline (10% w/v) (ref. [58](https://www.nature.com/articles/s41586-022-04894-9#ref-CR58 "Rennaker, R. L., Miller, J., Tang, H. & Wilson, D. A. Minocycline increases quality and longevity of chronic neural recordings. J. Neural Eng. 4, L1–L5 (2007).")). We chronically implanted a single two-shank 64-channel silicon probe (ASSY-236 H6, Cambridge Neurotech) mounted on a nanodrive shuttle (Cambridge Neurotech). In addition, we glued a tapered optical fibre (100 μm, 0.9 mm emission length, 0.22 NA, Optogenix) to the back of the probe (around 200–300 μm away from the shanks). The implant was slowly inserted in the DLS, contralateral to a long choice, in the two mice, targeting identical coordinates to the ones that were used for photometry and inhibition experiments. Finally, we chronically cemented a headstage (mini-amp-64 headstage, Cambridge Neurotech) that we connected before the start of every session. Mice were given carprofen in the days following surgery and allowed to recover for one week before training resumed.

Electrophysiological and synchronization data were digitized at 30 kHz with the Open Ephys acquisition board[55](https://www.nature.com/articles/s41586-022-04894-9#ref-CR55 "Siegle, J. H. et al. Open Ephys: an open-source, plugin-based platform for multichannel electrophysiology. J. Neural Eng. 14, 045003 (2017).") and recorded with Bonsai[52](https://www.nature.com/articles/s41586-022-04894-9#ref-CR52 "Lopes, G. et al. Bonsai: an event-based framework for processing and controlling data streams. Front. Neuroinform. 9, 7 (2015)."). Data were sorted offline using Kilosort2.5 ([https://github.com/MouseLand/Kilosort](https://github.com/MouseLand/Kilosort)) and manually curated using Phy ([https://github.com/cortex-lab/phy](https://github.com/cortex-lab/phy)).

To classify cells as putative MSNs, we used the same firing statistics and waveform criteria used in the acute recordings. In addition, we used a photo-identification protocol at the start of each session, consisting of 10 brief pulses, 2 ms, of 473-nm light at different intensities (2–10 mW measured at the end of the patchcord) and frequencies (5, 15 Hz). to photo-identify indirect-pathway MSNs. Units were considered photo-identified using an intersection of different criteria: SALT test[59](https://www.nature.com/articles/s41586-022-04894-9#ref-CR59 "Kvitsiani, D. et al. Distinct behavioural and network correlates of two interneuron types in prefrontal cortex. Nature 498, 363–366 (2013).") *P* value < 0.001, *t*\-test comparing baseline and post-laser onset (1–10 ms) firing rate yielding a *P* value < 0.01, correlation coefficient between laser-triggered waveform, non-evoked waveform > 0.85 and probability of eliciting  ≥ 1 spikes within 1–10 ms of each pulse onset > 0.1.

For all further analysis, spike counts were binned in 2-ms windows and smoothed by convolving with a gamma probability distribution kernel (shape parameter *k* = 2 and scale parameter *θ* = 25 ms).

To classify neurons on their modulation during the task we compared, for each neuron, the average delay period activity (0.6 to 2.4 s) and a corresponding baseline period (−5 to −2 s) relative to trial initiation (paired *t*\-test with *P* ≤ 0.05 as threshold).

Comparison between broken fixation and valid trials was performed in an identical manner to the photometry data (Extended Data Fig. [4](https://www.nature.com/articles/s41586-022-04894-9#Fig8)).

To relate the difference in activity between broken fixations and valid trials (ΔFRBroken–Valid) and delay period activation, relative to baseline, (ΔFRDelay–Baseline), in Fig. [2l](https://www.nature.com/articles/s41586-022-04894-9#Fig2), we took, for each unit, the average ΔFRBroken–Valid between −0.1 and 0 s aligned to broken fixation and regressed it against (ΔFRDelay–Baseline). To assess whether this is due to a selection effect dependent on delay period activity, we repeated the same analysis but using a different window aligned to broken fixations (−0.5:−0.4) (Extended Data Fig. [4d](https://www.nature.com/articles/s41586-022-04894-9#Fig8)). Second, we repeated the calculation of ΔFRBroken–Valid but this time randomly selecting half of the valid trials as a surrogate dataset for broken fixations and the remaining half to calculate our valid, null distribution. We bootstrapped the regression slope (against ΔFRDelay–Baseline) from this analysis 1,000 times and compared it against our initial outcome (*P* = 0). Both analyses indicated that our initial result was not due to sporadic correlations in the data or flooring effects from MSNs that were inactive during the delay period.

### Optogenetic manipulations during task performance

A 556-nm laser (500 mW, Optoelectronics Technology) was used as a light source to activate ArchT. In brief, the output of the laser was aligned to an acousto-optic modulator (AOM MTS110-A3-VIS, AA Opto Electronic) and fibre launched into a patchcord (200 µm core, 0.48 NA). The output of the patchcord was then connected to a power splitting rotary joint (FRJ\_1x2i\_FC-2FC\_0.5, Doric) and finally into 1 or 2 patchcords (200 µm core, 0.48 NA) that connected to the mouse’s implanted tapered fibres (Lambda-B fibre 200 μm core, 0.39 NA, 1.5 mm emitting length, Optogenix).

The light intensity was controlled by modulating the AOM using a dedicated Arduino Mega 2560 board connected to a DAC board (MCP4725, Sparkfun). Regardless of the stimulation duration, all protocols included a 250-ms linear ramping off, designed to reduce the potential for rebound excitation[60](https://www.nature.com/articles/s41586-022-04894-9#ref-CR60 "Chuong, A. S. et al. Noninvasive optical inhibition with a red-shifted microbial rhodopsin. Nat. Neurosci. 17, 1123–1129 (2014).").

The inhibition protocol was applied on a randomly selected 30% of trials. Light was continuously delivered, with the onset aligned to the initiation of a trial (centre nose port) and lasting until second-tone delivery or the exit of the subject mouse from the centre-poke, whichever occurred first. For all analyses of optogenetic manipulation data, the first 15 trials of each session were excluded. Laser power was set to be 23 to 31 mW at the end of the fibre for all mice.

For a subset of DLS direct-pathway mice (*n* = 3 D1-Cre, Extended Data Fig. [6](https://www.nature.com/articles/s41586-022-04894-9#Fig10)) and all DMS mice (*n* = 6 A2a-Cre and *n* = 6 D1-Cre), a third protocol was used in which the light was turned on at second-tone onset up until choice or 400 ms, whichever occurred first.

Each day, we changed the location of the inhibition (CS or CL; *n* = 4 DLS A2a-Cre, *n* = 6 DLS D1-Cre, *n* = 6 DMS A2a-Cre and *n* = 6 DMS D1-Cre) and, after collecting data from the unilateral manipulation conditions, we silenced both hemispheres simultaneously (*n* = 4 A2a-Cre, *n* = 4 D1-Cre, *n* = 6 DMS A2a-Cre and *n* = 6 DMS D1-Cre). For single mice, unless otherwise stated, all analyses were performed by concatenating all trials from all sessions of the same manipulation condition.

### Movement trajectories

Offline tracking of mouse position was performed using DeepLabCut[61](https://www.nature.com/articles/s41586-022-04894-9#ref-CR61 "Mathis, A. et al. DeepLabCut: markerless pose estimation of user-defined body parts with deep learning. Nat. Neurosci. 21, 1281–1289 (2018).") targeting the nape of each mouse (Fig. [1c](https://www.nature.com/articles/s41586-022-04894-9#Fig1) and Extended Data Fig. [10](https://www.nature.com/articles/s41586-022-04894-9#Fig14)). Low-confidence points (*P* < 0.5) were interpolated and tracking data were subsequently smoothed with a 10-sample median filter.

To compare movement trajectories between different conditions (Extended Data Fig. [8](https://www.nature.com/articles/s41586-022-04894-9#Fig12)), we first computed the average trajectory of a reference condition (non-stimulated and valid trials). Next, we calculated, for each trial’s trajectory, the average Euclidean distance to the reference trace.

To compute distances between positions from trials of differing duration, the longer trial of the pair was cropped to match the duration of the shorter. To compare across trial pairs of different duration, we normalized Euclidean distances by trial duration, computing the average Euclidean distance between reference and test trial per sampled frame.

We then compared these distributions to the ‘null’ distribution calculated from the same trials as the average trajectory with a two-sample Kolmogorov–Smirnov test (Extended Data Fig. [8c,d](https://www.nature.com/articles/s41586-022-04894-9#Fig12)).

### Immunohistochemistry and microscopy

Histological analysis was performed after all experiments to confirm optical fibre placement and expression patterns of transgenes. Mice were administered with a lethal dose of pentobarbital (Eutasil, 100 mg kg−1 intraperitoneally) and perfused transcardially with 4% paraformaldehyde. The brains were removed from the skull, stored for 24 h in 4% paraformaldehyde and then kept in PBS until sectioning. A vibratome or cryostat was used to section the brain into 50- or 40-µm-thick slices that were then immunostained with antibodies against GFP (A-6455, 1:1,000, Invitrogen) and tdTomato (ab125096, 1:1,000, Abcam). Finally, all slices were incubated in DAPI. Images were acquired with a confocal microscope (LSM 710, Zeiss) or a slide scanner (Axio Scan Z1, Zeiss). For electrophysiological recordings, shank placement was confirmed using DiI (V22885, Thermo Fisher Scientific).

### Statistics

Statistical analyses were performed in MATLAB or R. No statistical methods were used to predetermine sample sizes.

Data distribution was assumed to be normal. Performed statistical tests, sample size, relevant statistics and *P* values are reported throughout the text or in the respective figure caption. A summary of all tests can be found in Supplementary Table [1](https://www.nature.com/articles/s41586-022-04894-9#MOESM1).

We used a linear mixed effects model for the photometry data to account for conditions with missing subject data. We specified random intercepts per mouse and tested for fixed effects using the R package lme4 (ref. [62](https://www.nature.com/articles/s41586-022-04894-9#ref-CR62 "Bates, D., Mächler, M., Bolker, B. & Walker, S. Fitting Linear Mixed-Effects Models Using lme4. J. Stat. Softw. 67, 
https://doi.org/10.18637/jss.v067.i011
(2015).")) using data from correct single trials. To test the significance of relevant main effects, we report ANOVA *F*\-statistics with Satterthwaite adjusted degrees of freedom. We report marginal means and post-hoc contrasts (*t*\-statistics), using the R package emmeans (refs. [63](https://www.nature.com/articles/s41586-022-04894-9#ref-CR63 "Searle, S. R., Speed, F. M. & Milliken, G. A. Population marginal means in the linear model: an alternative to least squares means. Am. Stat. 34, 216–221 (1980)."),[64](https://www.nature.com/articles/s41586-022-04894-9#ref-CR64 "Lenth, R. Least-squares means: the R package lsmeans. J. Stat. Softw. 69, 
https://doi.org/10.18637/jss.v069.i01
(2016).")).

All other tests are reported throughout the text and summarized in Supplementary Table [1](https://www.nature.com/articles/s41586-022-04894-9#MOESM1). The significance level was not corrected for multiple comparisons.

### Reinforcement learning model

We constructed an actor–critic model with the goal of understanding the observed patterns of activity in DLS iMSNs and dMSNs and the functional role of DLS iMSNs in action suppression and selection revealed by optogenetic inhibition experiments. The experimental results showed that the DLS was functionally engaged in suppressing, but not promoting, specific actions during the task at times when those actions were most tempting. We thus inferred that some other region must provide the drive to act that constitutes the temptation itself. To accommodate these multiple, apparently regionally distinct, influences on behaviour, we designed a model containing two sub-agents, with access to different state transition dynamics, that interact through behaviour to solve the task.

We start by providing an overview of the sections that describe the model implementation. In the first section ('Task environment'), we begin by defining the rules that govern the real-world state transitions defined by the behavioural task paradigm itself. However, the model does not operate directly on these real-world environmental states, but, as described in the section 'State representation', contains two internal representations of the external world that are used to learn both state value functions (the critics) and action preference functions (the actors). We then define the general features of the actor–critic architecture in the ‘Actor–critic formulation’ section, describing how the two internal state representations feed into two parallel actor–critic sub-agents, both elaborated with a direct- and indirect-pathway actor component. In the ‘Learning the value of states’ section, we describe how the sub-agents each learn their own value of expected future reward given the internal state information they have access to using temporal difference learning. Next, in the ‘Actor learning in a multi-agent setting’ section, we define how a set of action preference functions, which serve as a basis for a policy for behavioural control, are learned in each sub-agent through the influence of a temporal difference RPE that is emitted by each sub-agent’s critic. Finally, in the ‘Policy definition’ section, we define how these action preference functions emitted by the two sub-agents are combined to define a policy for selecting Left, Right and Hold actions at each time step of a trial.

### Task environment

The behaviour of the mouse in the task and the underlying neural activity of the striatal populations was modelled as a reinforcement learning (RL) problem. RL models require the definition of a Markov decision process (MDP)[25](https://www.nature.com/articles/s41586-022-04894-9#ref-CR25 "Sutton, R. S. & Barto, A. G. Reinforcement Learning: an Introduction (MIT Press, 1998).") that consists of a set of states \\(P({e}\_{t+1},{r}\_{t}| {e}\_{t},{a}\_{t})\\) that gives us the probability of moving to a new state \\({e}\_{t+1}\\) and receiving a reward \\({r}\_{t}\\) after performing action \\({a}\_{t}\\).

We model the discrimination task environment by considering a linearly evolving variable \\(\\theta \\in {\\mathscr{R}}\\) that represents the passage of time since the onset of a trial, defined by the onset of the first tone that marked the beginning of interval stimuli. This variable is constrained to the interval \\(\\theta \\in \\left\[{\\theta }\_{0},{\\theta }\_{f}\\right\]\\), where \\({\\theta }\_{0}\\) is the trial initiation or interval onset, and \\({\\theta }\_{f}\\) the time point at which, if no action is taken a time-out is produced and the trial is over. We discretize this interval into a set of \\({N}\_{{\\rm{T}}}\\) bins \\({e}\_{t}\\in {\\mathscr{N}}\\) of duration \\(\\Delta \\theta =\\frac{{\\theta }\_{f}-{\\theta }\_{0}}{{N}\_{{\\rm{T}}}}\\) in milliseconds. We model the transitions of true time states as an off-diagonal transition matrix \\(P\\left({e}\_{t+1}|{e}\_{t},\\,{a}\_{t}\\right)\\), where for each true time state \\({e}\_{t}=t\\) we move to \\({e}\_{t+1}={t}\\) and where the corresponding true time is given by \\(\\theta =t\\Delta \\theta \\). In each trial, the second tone is defined in a set of *M* temporal markers \\({\\tau }\_{i}\\in {\\mathscr{R}}\\) all in the range \\(\\left\[{\\theta }\_{0},{\\theta }\_{f}\\right\]\\) and given by the values \[0.6, 1.05, 1.26, 1.38, 1.62, 1.74, 1.95, 2.4\] s, which will signal the occurrence of the second tone (interval offset) on a given trial *i* at real time *t* identified by the true time state *e**t*.

At each *e**t* the environment will accept one of three actions; choice of the short port (*a* = SHORT), choice of the long port (*a* = LONG) or perform no action, which we define as a HOLD action (*a* = HOLD). If no action other than HOLD is performed during the delay period and the correct choice is made after the second tone, a reward is delivered. If the incorrect action is performed in the post-second-tone period or if an action other than HOLD is performed during the delay period (that is, broken fixation), a punishment is delivered. Reward and punishment are defined as \\({r}\_{t}^{+}=10\\) and \\({r}\_{t}^{-}=-\\,5\\), respectively.

### State representation

Animals including mice are known to express noisy estimates of time[65](https://www.nature.com/articles/s41586-022-04894-9#ref-CR65 "Gibbon, J. Scalar expectancy theory and Weber’s law in animal timing. Psychol. Rev. 84, 279–325 (1977)."). We model this by considering that the model does not have direct access to the 'true time' state *e**t* but instead relies on an internal estimate of elapsed time given by a set of states for each sub-agent *c*, \\({s}\_{t}^{c}\\subset \\left\[0,\\ldots ,{N}\_{{\\rm{K}}}\\right\]\\in {\\mathscr{N}}\\) with total number *N*K.

This internal estimate was constructed so as to produce scalar variability in temporal estimates around the true time. To achieve this, we define a central dwell time *μ* that corresponds to a sequence of states of each sub-agent \\({s}\_{t}^{c}\\) that accurately follows the elapsed time from the experimentalist's viewpoint; that is, true time. We then draw the dwell time \\(\\Delta {\\theta }\_{i}^{d}\\), shared by both sub-agents, at each trial *i* from a Gaussian distribution given by \\(\\Delta {\\theta }\_{i}^{d}\\approx N(\\mu ,\\sigma )\\), with variance *σ* defining the range of potential dwell times. The variable \\(\\Delta {\\theta }\_{i}^{d}\\) thus represents the dwell time for the current trial, becoming discretized in a number of ‘true time’ states, *e**t*, that elapse in a single internal state, *s**t*, and is responsible for the scalar variability of internal time estimates expressed by the model across trials. Because the effect of trial to trial dwell time variability accumulates as the model progresses through states, internal variability in time estimates grows in aggregate as true time elapses.

To accommodate assumed differences in information provided by different outlying areas to circuits in distinct regions of the striatum, we constructed different mappings from environmental to internal states, *K**c* for each sub-agent \\(c\\in \\{L,{X}\\}\\) (see equations (1), (2)). Each sub-agent maps the true time state *e**t* to the internal temporal estimate of the agent given by the state \\(\\,{s}\_{t}^{c}\\). The function *K**c* maps the internal temporal estimate into two possible sets of states; post-first-tone states (or pre-second-tone states) \\({S}^{{\\rm{pre}}}\\in \\left\[0,\\ldots ,{N}\_{\\frac{K}{2}}\\,\\right\]\\subset {\\mathscr{N}}\\) and post-second-tone states \\({S}^{{\\rm{post}}}\\in \\left\[{N}\_{\\frac{K}{2}},\\ldots ,{N}\_{K}\\right\]\\subset {\\mathscr{N}}\\), with the transition between these two sets triggered by the occurrence of a tone at true time \\({\\tau }\_{i}\\). Sub-agent *c* *\=* *L* is intended to reflect lateral circuitry that includes dMSNs and iMSNs in the DLS, whereas sub-agent *c* *\=* *X* is intended to reflect the potential medial circuitry involved in generating a temptation signal in the DMS, also with its corresponding dMSN and iMSN split. The distinction between the sets \\(\\{{S}^{{\\rm{pre}}},{S}^{{\\rm{post}}}\\}\\) is what allows the model to correctly discern in which states it should perform an action or suppress all actions through the HOLD action.

The mapping *K**L*, corresponding to sub-agent *L*, produces a more veridical representation of the task environment, including whether a second tone has occurred and thus is defined in the the full set of states \\({K}^{L}:\\left\\{\\theta ,\\Delta {\\theta }\_{i}^{d},{\\tau }\_{i}\\right\\}\\to \\{{S}^{{\\rm{pre}}},{S}^{{\\rm{post}}}\\}\\) . Trial start commences a progression through post-first-tone states (that is, pre-second-tone states), and occurrence of the second tone causes a transition into a stream of post-second-tone states, through which the state progresses until a terminal state is reached when a choice is made or the maximum possible state in the trial is reached.

We define the mapping *K**L* concretely as the sequence of states given by

$${K}^{L}\\left(\\theta ,\\,\\Delta {\\theta }\_{i}^{d},{\\tau }\_{i}\\right)=\\,\\left\\{\\begin{array}{c}\\left\\lfloor \\frac{\\theta }{\\,\\Delta {\\theta }\_{i}^{d}}\\right\\rfloor ,{\\rm{if}}\\,\\theta < \\,{\\tau }\_{i}\\\\ \\left\\lfloor \\frac{\\theta }{\\,\\Delta {\\theta }\_{i}^{d}}\\right\\rfloor +J,\\,{\\rm{if}}\\,\\theta \\ge {\\tau }\_{i}\\end{array}\\right.\\,$$

(1a)

with ⌊*x*⌋ the floor function applied to *x* and *J* a jump parameter that goes from *S*pre to *S*post states.

The second mapping *K**X*, corresponding to sub-agent *X*, is unaware of second-tone events and is thus only defined in pre-second-tone states; that is, \\({K}^{X}:\\left\\{\\theta ,\\Delta {\\theta }\_{i}^{d}\\right\\}\\to {S}^{{\\rm{pre}}}\\). In this mapping, as in the previously described one, trial start commences a progression through post-first-tone states (that is, pre-second-tone states); however, unlike the previous mapping, progression through pre-second-tone states continues until a terminal state is reached either when a choice is made or when the maximum possible state in the trial is reached, regardless of second-tone occurrence. We view the mapping *K**X* as more abstract, useful for separating the world into short (<1.5 s) or long (>1.5 s) epochs and perhaps constituting a more predictive state representation[32](https://www.nature.com/articles/s41586-022-04894-9#ref-CR32 "Dayan, P. Improving generalization for temporal difference learning: the successor representation. Neural Comput. 5, 613–624 (1993)."),[33](https://www.nature.com/articles/s41586-022-04894-9#ref-CR33 "Stachenfeld, K. L., Botvinick, M. M. & Gershman, S. J. The hippocampus as a predictive map. Nat. Neurosci. 20, 1643–1653 (2017)."), yet devoid of more low-level sensed features of the environment. Mapping *K**X* also reflects a kind of information factorization, hiding information about the environment from sub-agent *M* in a manner hypothesized within hierarchical views of behavioural control to aid in generalizability[66](https://www.nature.com/articles/s41586-022-04894-9#ref-CR66 "Merel, J., Botvinick, M. & Wayne, G. Hierarchical motor control in mammals and machines. Nat. Commun. 10, 5489 (2019).").

Concretely, we define this second mapping for each trial *i* through the function

$${K}^{X}\\left(\\theta ,\\,\\Delta {\\theta }\_{i}^{d}\\right)=\\,\\left\\lfloor \\frac{\\theta }{\\,\\Delta {\\theta }\_{i}^{d}}\\right\\rfloor $$

(2a)

The full set of mappings for the set of sub-agents \\(c\\in \\{L,X\\}\\) is thus given by

$${s}\_{t}^{L}={K}^{L}\\left(\\theta ,\\Delta {\\theta }\_{i}^{d},{\\tau }\_{i}\\right)$$

(1b)

$${s}\_{t}^{X}={K}^{X}\\left(\\theta ,\\Delta {\\theta }\_{i}^{d}\\right)$$

(2b)

### Actor–critic formulation

To construct each sub-agent, we formulate an actor–critic algorithm in which, for each state representation \\(\\{{s}\_{t}^{L},{s}\_{t}^{X}\\}\\), we define a corresponding critic \\({V}^{c}\\left({s}\_{t}^{c}\\right)\\) with index \\(c\\in \\{L,{X}\\}\\) corresponding to the lateral and medial circuits, respectively, and its respective actor(s)[67](https://www.nature.com/articles/s41586-022-04894-9#ref-CR67 "Motiwala, A., Soares, S., Atallah, B. V., Paton, J. J. & Machens, C. K. Efficient coding of cognitive variables underlies dopamine response and choice behavior. Nat. Neurosci. 25, 738–748 (2022).") defined by a set of action preference[25](https://www.nature.com/articles/s41586-022-04894-9#ref-CR25 "Sutton, R. S. & Barto, A. G. Reinforcement Learning: an Introduction (MIT Press, 1998).") functions \\({A}^{p,c}({s}\_{t}^{c},{a}\_{t})\\), where the index \\(p=\\{D,I\\}\\) corresponds to the direct and indirect pathways. Both sub-agents \\(\\{L,{X}\\}\\) are constructed to contain direct- and indirect-pathway actors with opposing influences on action production. The learned action preferences are then combined into a single probabilistic policy \\(\\pi ({a|}{s}\_{t}^{L},{s}\_{t}^{X})\\) from which a decision will be sampled.

The choice of action preference algorithms for this problem is twofold; actor–critic models have been mapped onto striatal anatomy, in which striatal actors are taught by a critic that emits RPEs through dense dopaminergic projections to the striatum[26](https://www.nature.com/articles/s41586-022-04894-9#ref-CR26 "Bornstein, A. M. & Daw, N. D. Multiplicity of control in the basal ganglia: computational roles of striatal subregions. Curr. Opin. Neurobiol. 21, 374–380 (2011)."). Second, owing to the fact that the action preference functions are learned using the RPE \\({\\delta }\_{t}\\), we can define update rules onto direct- and indirect-pathway actors on the basis of previously established effects of dopamine on plasticity of synapses on striatal dMSNs and iMSNs[28](https://www.nature.com/articles/s41586-022-04894-9#ref-CR28 "Collins, A. G. E. & Frank, M. J. Opponent actor learning (OpAL): modeling interactive effects of striatal dopamine on reinforcement learning and choice incentive. Psychol. Rev. 121, 337–366 (2014)."),[29](https://www.nature.com/articles/s41586-022-04894-9#ref-CR29 "Gurney, K. N., Humphries, M. D. & Redgrave, P. A new framework for cortico-striatal plasticity: behavioural theory meets in vitro data at the reinforcement-action interface. PLoS Biol. 13, e1002034 (2015)."),[30](https://www.nature.com/articles/s41586-022-04894-9#ref-CR30 "Iino, Y. et al. Dopamine D2 receptors in discrimination learning and spine enlargement. Nature 579, 555–560 (2020)."),[31](https://www.nature.com/articles/s41586-022-04894-9#ref-CR31 "Lee, S. J. et al. Cell-type-specific asynchronous modulation of PKA by dopamine in learning. Nature 590, 451–456 (2021)."),[68](https://www.nature.com/articles/s41586-022-04894-9#ref-CR68 "Grondman, I., Busoniu, L., Lopes, G. A. D. & Babuska, R. A survey of actor-critic reinforcement learning: standard and natural policy gradients. In IEEE Transactions on Systems, Man, and Cybernetics, Part C (Applications and Reviews) Vol 42, 1291–1307 (IEEE, 2012).").

### Learning the value of states

In the usual actor–critic formulation, the critic takes the form of a state value function, defined as the expected value over a policy \\(\\pi ({a|}{s}\_{t})\\) of the sum of discounted rewards and is written as,

$${V}^{c}\\left({s}\_{t}^{c}\\right)=\\,{E}^{\\pi }\\left\[\\mathop{\\sum }\\limits\_{k=0}^{T-k-1}{\\gamma }^{k}{r}\_{t+k+1}{\\rm{|}}s={s}\_{t}^{c}\\right\]$$

(3)

with *γ* *<* 1 being the discount factor.

To update the state-values, temporal difference (TD) methods are used, with an update given by (ref. [25](https://www.nature.com/articles/s41586-022-04894-9#ref-CR25 "Sutton, R. S. & Barto, A. G. Reinforcement Learning: an Introduction (MIT Press, 1998).")):

$$V\\left({s}\_{t}\\right)\\leftarrow V\\left({s}\_{t}\\right)+\\alpha {\\delta }\_{t},$$

(4)

where *α* is the learning rate for the critic (*V* for value function) and *δ**t* the RPE defined as

$${\\delta }\_{t}={R}\_{t+1}+\\gamma V\\left({s}\_{t+1}\\right)-V({s}\_{t}).$$

(5)

In our formulation, the RPE will serve as a learning signal for all the actors that will be defined below. To make the notation explicit for the multi-agent formalization that we will expand in the following sections, we define that for each critic \\({V}^{c}\\left({s}\_{t}^{c}\\right)\\),

$${V}^{c}\\left({s}\_{t}^{c}\\right)\\leftarrow V\\left({s}\_{t}^{c}\\right)+\\alpha \\left({s}\_{t}^{c}\\right){\\delta }\_{t}^{c},$$

(6)

their corresponding value function is updated by a corresponding RPE \\({\\delta }\_{t}^{c}\\) so that the update rules for an agent consisting of multiple critics can be written as

$${\\delta }\_{t}^{c}\\,={R}\_{t+1}+\\gamma {V}^{c}\\left({s}\_{t+1}^{c}\\right)-{V}^{c}({s}\_{t}^{c}),$$

(7)

with *γ* the discount factor of the sub-agents and the learning rate defined as the inverse of the number of visits to state \\({s}\_{t}^{c}\\), \\(N({s}\_{t}^{c})\\) (ref. [25](https://www.nature.com/articles/s41586-022-04894-9#ref-CR25 "Sutton, R. S. & Barto, A. G. Reinforcement Learning: an Introduction (MIT Press, 1998).")); that is,

$$\\alpha \\left({s}\_{t}^{c}\\right)=\\frac{1}{N\\left({s}\_{t}^{c}\\right)}$$

(8)

to facilitate convergence.

### Actor learning in a multi-agent setting

To model the neural activities of the dMSNs and iMSNs observed in the data we take a multi-agent RL approach[69](https://www.nature.com/articles/s41586-022-04894-9#ref-CR69 "Buşoniu, L., Babuška, R. & De Schutter, B. in Innovations in Multi-Agent Systems and Applications - 1 (eds Srinivasan, D. & Jain, L. C.) 183–221 (Springer, 2010).") by hypothesizing that the model consists of a set of critics feeding information to different actors that represent the underlying neural activity of each striatal pathway. For this formalism, each actor can have a different viewpoint as to what is happening both in terms of their provided internal state representation and in the corresponding RPEs that each receives, being sensitive to a specific range of the available RPEs, as was previously done[28](https://www.nature.com/articles/s41586-022-04894-9#ref-CR28 "Collins, A. G. E. & Frank, M. J. Opponent actor learning (OpAL): modeling interactive effects of striatal dopamine on reinforcement learning and choice incentive. Psychol. Rev. 121, 337–366 (2014)."),[29](https://www.nature.com/articles/s41586-022-04894-9#ref-CR29 "Gurney, K. N., Humphries, M. D. & Redgrave, P. A new framework for cortico-striatal plasticity: behavioural theory meets in vitro data at the reinforcement-action interface. PLoS Biol. 13, e1002034 (2015).").

We take inspiration from biology and the known results regarding the underlying plasticity dynamics in striatal neurons so as to model the activities of the direct and indirect pathways. On the basis of a number of experimental studies, one report[29](https://www.nature.com/articles/s41586-022-04894-9#ref-CR29 "Gurney, K. N., Humphries, M. D. & Redgrave, P. A new framework for cortico-striatal plasticity: behavioural theory meets in vitro data at the reinforcement-action interface. PLoS Biol. 13, e1002034 (2015).") posits that positive changes in the overall plasticity of direct-pathway medium spiny neurons (dMSNs) are directly correlated with an increase in dopamine (DA), whereas decreases in DA concentration show a decrease in plasticity. Conversely, for indirect-pathway MSNs (iMSNs) higher DA values have the opposite effect as they reduce the change in plasticity, whereas lower concentrations of DA potentiate plasticity. Consistent findings have also been observed in the volume change of dendritic spines for dMSNs and iMSNs[30](https://www.nature.com/articles/s41586-022-04894-9#ref-CR30 "Iino, Y. et al. Dopamine D2 receptors in discrimination learning and spine enlargement. Nature 579, 555–560 (2020)."), spike-timing-dependent plasticity[27](https://www.nature.com/articles/s41586-022-04894-9#ref-CR27 "Shen, W., Flajolet, M., Greengard, P. & Surmeier, D. J. Dichotomous dopaminergic control of striatal synaptic plasticity. Science 321, 848–851 (2008).") and intracellular PKA levels[31](https://www.nature.com/articles/s41586-022-04894-9#ref-CR31 "Lee, S. J. et al. Cell-type-specific asynchronous modulation of PKA by dopamine in learning. Nature 590, 451–456 (2021)."). In addition, these two populations appear largely spatially intermixed and thus likely to receive comparable dopamine input.

We capture these plasticity rules by defining a set of nonlinear functions *f**p* that we will associate with individual actors *p*. As the amount of DA present in the MSNs modulates the change in plasticity of these cells, we will make this nonlinear function dependent on the RPE of its corresponding sub-agent *c*; that is, \\({f}^{p}({\\delta }\_{t}^{c})\\). In this manner, we are able to associate a given pathway to a specific combination of a nonlinear function *f**p* and the RPE of a given critic \\(\\,{\\delta }\_{t}^{c}\\).

Concretely, the direct-pathway actors of the DLS and X sub-agents are subject to updates via \\({f}^{D}\\left({\\delta }\_{t}^{L}\\right),{f}^{D}\\left({\\delta }\_{t}^{X}\\right)\\) and the indirect-pathway actor of the DLS and X sub-agents via \\({f}^{I}({\\delta }\_{t}^{L})\\) and \\({f}^{I}({\\delta }\_{t}^{X})\\), respectively. These functions are defined for each pathway *p* as,

$${f}^{p}\\left({\\delta }\_{t}^{c}\\right)={b}\_{0}^{p}+\\frac{{b}\_{1}^{p}}{1+{b}\_{2}^{p}{{\\rm{e}}}^{(1-{b}\_{3}^{p}{\\delta }\_{t}^{c})}},$$

(9)

where the *b* parameters are adjusted for each individual pathway. Concretely, \\({b}\_{0}^{p}\\) and \\({b}\_{1}^{p}\\) determine the vertical range of the curve and \\({b}\_{2}^{p},{b}\_{3}^{p}\\) its slope. For the L and X agents we used \\(\[{b}\_{0}^{p},{b}\_{1}^{p},{b}\_{2}^{p},{b}\_{3}^{p}\]\\) = \[−3.5, 11.5, 0.9, 1\] and \[−3.5, 11.5, 0.9, −1\] for their respective direct and indirect actors. The parameters of the indirect pathway are defined so as to transform the negative RPEs into positive update weight changes, the direct-pathway function transforms positive RPEs into positive weight changes for that actor.

In actor–critic formalisms, one needs to learn the policy in addition to the state value function. In our case we chose the action preference framework, with action preferences defined as functions *A*(*s**t*,*a**t*) at each state–action pair that will allow the agent to choose the appropriate action at each state. In the usual definition of actor–critic models, for an action *a**t* and state *s**t* the action preferences are learned through the RPE that is calculated at the current time, \\({\\delta }\_{t}\\).

The update rule for the action preference for a single actor receiving RPEs from a critic is given by

$$A({s}\_{t},{a}\_{t})\\leftarrow A({s}\_{t},{a}\_{t})+{\\alpha \\delta }\_{t}$$

(10)

In simple terms, at each update, if the action executed at state *s**t* results in a positive RPE then that action will become more likely to be performed in the future; if the RPE is negative then the likelihood of the action decreases for that state.

Inserting the aforementioned plasticity rules to drive action preference change in the model is done by slightly altering the action-preference updating learning rules defined above. We apply the pathway transfer function \\({f}^{p}({\\delta }\_{t}^{c})\\) (defined in equation ([8](https://www.nature.com/articles/s41586-022-04894-9#Equ10))) to each actor’s learning rule; that is,

$${A}^{p,c}\\left({s}\_{t}^{c},{a}\_{t}\\right)\\leftarrow {A}^{p,c}\\left({s}\_{t}^{c},{a}\_{t}\\right)+\\alpha \\left({s}\_{t}^{c}\\right){f}^{p}({\\delta }\_{t}^{c})$$

(11)

and define the learning rate for the actors in a similar manner to the critics (see equation ([8](https://www.nature.com/articles/s41586-022-04894-9#Equ10))).

Concretely, for the actors and state representations used in our model, the full set of update equations is thus:

$${A}^{D,L}\\left({s}\_{t}^{L},{a}\_{t}\\right)\\leftarrow {A}^{D,L}\\left({s}\_{t}^{L},{a}\_{t}\\right)+\\alpha \\left({s}\_{t}^{L}\\right){f}^{D}\\left({\\delta }\_{t}^{L}\\right)$$

$${A}^{I,L}\\left({s}\_{t}^{L},{a}\_{t}\\right)\\leftarrow {A}^{I,L}\\left({s}\_{t}^{L},{a}\_{t}\\right)+\\alpha \\left({s}\_{t}^{L}\\right){f}^{I}\\left({\\delta }\_{t}^{L}\\right)$$

(12)

$${A}^{D,X}\\left({s}\_{t}^{X},{a}\_{t}\\right)\\leftarrow {A}^{D,X}\\left({s}\_{t}^{X},{a}\_{t}\\right)+\\alpha \\left({s}\_{t}^{X}\\right){f}^{D}\\left({\\delta }\_{t}^{X}\\right)$$

$${A}^{I,X}\\left({s}\_{t}^{X},{a}\_{t}\\right)\\leftarrow {A}^{I,X}\\left({s}\_{t}^{X},{a}\_{t}\\right)+\\alpha \\left({s}\_{t}^{X}\\right){f}^{I}({\\delta }\_{t}^{X})$$

(13)

with the RPEs for each agent being given by two independent critics with update rules:

$${V}^{L}\\left({s}\_{t}^{L}\\right)\\leftarrow {V}^{L}\\left({s}\_{t}^{L}\\right)+\\,\\alpha \\left({s}\_{t}^{L}\\right){\\delta }\_{t}^{L}$$

(14)

$${V}^{X}\\left({s}\_{t}^{X}\\right)\\leftarrow {V}^{X}\\left({s}\_{t}^{X}\\right)+\\,\\alpha \\left({s}\_{t}^{X}\\right){\\delta }\_{t}^{X}.$$

(15)

### Policy definition

To calculate the policy as a combination of the two sub-agents we define a total action preference for the four actors as a sum of their corresponding action preferences weighed by their corresponding actor weights \\({\\omega }\_{p,c}\\):

$${A}^{T}\\left({s}\_{t}^{L},\\,{s}\_{t}^{X},{a}\_{t}\\right)=\\,\\sum \_{p,c}{\\omega }\_{p,c}{A}^{p,c}({s}\_{t}^{c},{a}\_{t}),$$

(16)

more concretely

$${A}^{T}\\left({s}\_{t}^{L},\\,{s}\_{t}^{X},{a}\_{t}\\right)=\\,{\\omega }\_{D,L}{A}^{D,L}\\left({s}\_{c}^{L},{a}\_{t}\\,\\right)+{\\omega }\_{I,L}{A}^{I,L}\\left({s}\_{c}^{L},{a}\_{t}\\right)+{\\omega }\_{D,X}{A}^{D,X}\\left({s}\_{c}^{X},{a}\_{t}\\right)+{\\omega }\_{I,X}{A}^{I,X}\\left({s}\_{c}^{X},{a}\_{t}\\right),$$

(17)

where the weights are given by \\({\\omega }\_{D,L}={-\\omega }\_{I,L}={\\omega }\_{D,X}=-\\,{\\omega }\_{I,X}=1\\)and the remaining are set to zero. Because the indirect-pathway actor has an opposite sign to the remaining sub-agents, it serves as an inhibitory gate for action execution. This idea was first proposed in ref. [11](https://www.nature.com/articles/s41586-022-04894-9#ref-CR11 "Mink, J. W. The basal ganglia: focused selection and inhibition of competing motor programs. Prog. Neurobiol. 50, 381–425 (1996)."), in which it is highlighted that the expression of movement seems to be directly correlated with the amount of downstream inhibition exerted by outputs of the basal ganglia. Later experiments using optogenetics then showed that increased activity in D2-MSNs (iMSNs) through optogenetic excitation generated a decrease of movement in mice, whereas an increase of activity in D1-MSNs (dMSNs) generated an increase in movement[8](https://www.nature.com/articles/s41586-022-04894-9#ref-CR8 "Kravitz, A. V. et al. Regulation of parkinsonian motor behaviours by optogenetic control of basal ganglia circuitry. Nature 466, 622–626 (2010).").

All of the suppressive information is taught by negative RPEs acting on the indirect-pathway action preferences. One way of looking at this function is that it represents, instead of the policy which tells agents what to do, an anti-policy that informs the model of what not to do. It serves as a dynamic map that evolves through the environment, releasing and increasing resistance to signals that push for actions to be expressed.

It is through the value of this total action preference that we define the HOLD action. Given that suppressing actions in animals is linked with higher values of indirect-pathway activity, we increase the probability of that action being performed proportionally to how negative the total action preference is as negative total action preferences are mostly a result of a dominance of the indirect-pathway actor over the remaining actors. We achieve this by, instead of learning an explicit action preference for the HOLD action as we do for the SHORT or LONG actions, triggering a condition in which if the value of the total action preference is negative, the action preference of the HOLD action will be zero.

Concretely, the hold action is thus chosen through the following conditional:

$${\\rm{if}}\\,{A}^{T}\\left({s}\_{t}^{L},\\,{s}\_{t}^{X},{a}\_{t}\\right) < 0\\,\\forall \\,{a}\_{t}\\,\\{{\\rm{SHORT}},\\,{\\rm{LONG}}\\}$$

$$\\Rightarrow {A}^{T}\\left({s}\_{t}^{L},\\,{s}\_{t}^{X},{\\rm{HOLD}}\\right)=0$$

else

$$\\Rightarrow {A}^{T}\\left({s}\_{t}^{L},\\,{s}\_{t}^{X},{\\rm{HOLD}}\\right)=-\\,{\\rm{\\infty }}$$

(18)

This definition for the HOLD action preference works in the following way: in the usual actor–critic formulation, given the discrete states *s**t*, the probability of the model choosing one of the actions *a* at a given state is given by the distribution \\(\\pi ({a|}{s}\_{t})\\). For a single actor, the actions at each observation *s**t* are chosen via a softmax of the action preference *A*(*s**t*,*a**t*); that is, the probability of a given action *α* being executed when an agent observes a state *s**t* can be obtained by sampling from the distribution given by

$$\\pi (a| {s}\_{t})=\\frac{{{\\rm{e}}}^{\\beta A({s}\_{t},{a}\_{t})}}{{\\sum }\_{j}{{\\rm{e}}}^{\\beta A({s}\_{t},{a}^{j})}},$$

(19)

where *β* is the temperature parameter controlling exploration, and the denominator contains the sum over all actions.

In our multi-agent model, we define the probability of choosing action *a* given states \\(\\left\\{{s}\_{t}^{L},{s}\_{t}^{X}\\right\\}\\) for the actions as the softmax of the total action preferences \\({A}^{T}({s}\_{t}^{L},{s}\_{t}^{X},{a}\_{t})\\)

$$\\pi (a| {s}\_{t}^{L},{s}\_{t}^{X})=\\frac{{{\\rm{e}}}^{\\beta {A}^{T}({s}\_{t}^{L},{s}\_{t}^{X},{a}\_{t})}}{{\\sum }\_{j}{{\\rm{e}}}^{\\beta {A}^{T}({s}\_{t}^{L},{s}\_{t}^{X},{a}^{j})}}$$

(20)

with the conditions for the HOLD action defined in equation ([18](https://www.nature.com/articles/s41586-022-04894-9#Equ19)). With these conditions, in the case in which the total action preference for both SHORT and LONG actions is negative and suppression dominates, the term in the denominator for the HOLD action will be one and terms for the remaining actions will have small values as the exponential function approaches zero for negative values. For the case in which suppression does not dominate, only the SHORT and LONG actions have probabilities bigger than zero, as the action preference for the HOLD action goes to −∞ (and probability zero).

### Simulation details

A detailed description of the training algorithm can be seen in Supplementary Table [2](https://www.nature.com/articles/s41586-022-04894-9#MOESM1). All simulations were performed on an 80-dimensional state-space. Each trial consisted of a trajectory with a pre-specified dwell time sampled from a Gaussian distribution with mean *μ**t* = 67 ms and variance *σ**t* = 20 ms, sampled from a predetermined set of 30 dwell times that covered the interval between *t*max = 100 ms and *t*min = 65 ms. Convergence was assessed by verifying that all value functions and action preferences showed a normalized difference between epochs under 0.01 for more than 50,000 trials, with a total number of 200,000 trials. The training set for the second-tone times (in seconds) was given by *T*train = \[0.1, 0.3, 0.5, 0.6, 0.8, 1.05, 1.26, 1.38, 1.62, 1.74, 1.95, 2.2, 2.4, 2.5\] with the decision boundary being set at 1.5 s. The learning rates \\({\\alpha }\_{V},{\\alpha }\_{A}\\) were all initialized at 20 and decreased for each state proportionally to the number of visits to each state. Rewards for correct and incorrect/broken fixation trials were set at 10 and −5, respectively.

The transfer function \\({f}^{p}({\\delta }\_{t}^{c})\\) parameters were defined as \\(\[{b}\_{0}^{p},{b}\_{1}^{p},{b}\_{2}^{p},{b}\_{3}^{p}\]\\). The values for the direct-pathway actor for both sub-agents were set at \[−3.5, 11.5, 0.9, 1\] and \[−3.5, 11.5, 0.9, −1\] for the indirect-pathway actors. The weights in equation ([18](https://www.nature.com/articles/s41586-022-04894-9#Equ19)) for each actor were all equal to 1. The discount parameter for each critic *γ* was 0.98 and the temperature of the softmax function *β* for the policy was 1.5 for both training and testing.

To simulate the effects of pathway-specific optogenetic inhibition, we generated control and manipulated datasets (1.5k trials) drawing single-trial intervals from a set identical to the one used to test the mice (*T*test \[0.6, 1.05, 1.26, 1.38, 1.62, 1.74, 1.95, 2.4\]).

### Optogenetics experiments

For all of the post-training experiments, the learning of the agents was frozen and for the control trials the weights of each agent were kept the same as during training. Two sets of experiments were performed; one in which the DLS indirect-pathway was inhibited and another in which the direct pathway of sub-agent X was inhibited. This inhibition consisted in a downscaling of the weights of the corresponding pathway weights to \\({\\omega }\_{L,I}=0.98\\) and \\({{\\rm{\\omega }}}\_{{\\rm{X}},{\\rm{D}}}=0.99\\), so as to match the effect size observed in the data. Varying these values produces qualitatively similar effects.

For each perturbed pathway, three optogenetic perturbations were performed, corresponding to each unilateral experiment and bilateral manipulation respectively, in which the weights corresponding to the relevant action (SHORT, LONG or SHORT and LONG) were scaled to the values defined above.

### Reporting summary

Further information on research design is available in the [Nature Research Reporting Summary](https://www.nature.com/articles/s41586-022-04894-9#MOESM2) linked to this paper.

## Data availability

The data and analysis code that support the findings of this study are available from the corresponding author upon reasonable request. [Source data](https://www.nature.com/articles/s41586-022-04894-9#Sec33) are provided with this paper.

## References

1.  Albin, R. L., Young, A. B. & Penney, J. B. The functional anatomy of basal ganglia disorders. *Trends Neurosci.* **12**, 366–375 (1989).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:STN:280:DyaK3c%2FltVGjsA%3D%3D)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=2479133)  [Article](https://doi.org/10.1016%2F0166-2236%2889%2990074-X)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=The%20functional%20anatomy%20of%20basal%20ganglia%20disorders&journal=Trends%20Neurosci.&volume=12&pages=366-375&publication_year=1989&author=Albin%2CRL&author=Young%2CAB&author=Penney%2CJB) 
    
2.  Cui, G. et al. Concurrent activation of striatal direct and indirect pathways during action initiation. *Nature* **494**, 238–242 (2013).
    
    [ADS](http://adsabs.harvard.edu/cgi-bin/nph-data_query?link_type=ABSTRACT&bibcode=2013Natur.494..238C)  [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC3sXhsVOqs74%3D)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=23354054)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC4039389)  [Article](https://doi.org/10.1038%2Fnature11846)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Concurrent%20activation%20of%20striatal%20direct%20and%20indirect%20pathways%20during%20action%20initiation&journal=Nature&volume=494&pages=238-242&publication_year=2013&author=Cui%2CG) 
    
3.  Schultz, W. in *Functions of the Cortico-Basal Ganglia Loop* (eds Kimura, M. & Graybiel, A. M.) 31–48 (Springer, 1995).
    
4.  Doya, K. What are the computations of the cerebellum, the basal ganglia and the cerebral cortex? *Neural Netw.* **12**, 961–974 (1999).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:STN:280:DC%2BC2sbnt1Wltw%3D%3D)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=12662639)  [Article](https://doi.org/10.1016%2FS0893-6080%2899%2900046-5)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=What%20are%20the%20computations%20of%20the%20cerebellum%2C%20the%20basal%20ganglia%20and%20the%20cerebral%20cortex%3F&journal=Neural%20Netw.&volume=12&pages=961-974&publication_year=1999&author=Doya%2CK) 
    
5.  Barkley, R. A. Behavioral inhibition, sustained attention, and executive functions: constructing a unifying theory of ADHD. *Psychol. Bull.* **121**, 65–94 (1997).
    
    [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=9000892)  [Article](https://doi.org/10.1037%2F0033-2909.121.1.65)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Behavioral%20inhibition%2C%20sustained%20attention%2C%20and%20executive%20functions%3A%20constructing%20a%20unifying%20theory%20of%20ADHD&journal=Psychol.%20Bull.&volume=121&pages=65-94&publication_year=1997&author=Barkley%2CRA) 
    
6.  Gerfen, C. R. & Surmeier, D. J. Modulation of striatal projection systems by dopamine. *Annu. Rev. Neurosci.* **34**, 441–466 (2011).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC3MXpvVyisrk%3D)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=21469956)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3487690)  [Article](https://doi.org/10.1146%2Fannurev-neuro-061010-113641)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Modulation%20of%20striatal%20projection%20systems%20by%20dopamine&journal=Annu.%20Rev.%20Neurosci.&volume=34&pages=441-466&publication_year=2011&author=Gerfen%2CCR&author=Surmeier%2CDJ) 
    
7.  Alexander, G. E. & Crutcher, M. D. Functional architecture of basal ganglia circuits: neural substrates of parallel processing. *Trends Neurosci.* **13**, 266–271 (1990).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DyaK3MXjs1Snuw%3D%3D)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=1695401)  [Article](https://doi.org/10.1016%2F0166-2236%2890%2990107-L)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Functional%20architecture%20of%20basal%20ganglia%20circuits%3A%20neural%20substrates%20of%20parallel%20processing&journal=Trends%20Neurosci.&volume=13&pages=266-271&publication_year=1990&author=Alexander%2CGE&author=Crutcher%2CMD) 
    
8.  Kravitz, A. V. et al. Regulation of parkinsonian motor behaviours by optogenetic control of basal ganglia circuitry. *Nature* **466**, 622–626 (2010).
    
    [ADS](http://adsabs.harvard.edu/cgi-bin/nph-data_query?link_type=ABSTRACT&bibcode=2010Natur.466..622K)  [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC3cXosVKhsLs%3D)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=20613723)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3552484)  [Article](https://doi.org/10.1038%2Fnature09159)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Regulation%20of%20parkinsonian%20motor%20behaviours%20by%20optogenetic%20control%20of%20basal%20ganglia%20circuitry&journal=Nature&volume=466&pages=622-626&publication_year=2010&author=Kravitz%2CAV) 
    
9.  Freeze, B. S., Kravitz, A. V., Hammack, N., Berke, J. D. & Kreitzer, A. C. Control of basal ganglia output by direct and indirect pathway projection neurons. *J. Neurosci.* **33**, 18531–18539 (2013).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC3sXhvVKjs7rF)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=24259575)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3834057)  [Article](https://doi.org/10.1523%2FJNEUROSCI.1278-13.2013)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Control%20of%20basal%20ganglia%20output%20by%20direct%20and%20indirect%20pathway%20projection%20neurons&journal=J.%20Neurosci.&volume=33&pages=18531-18539&publication_year=2013&author=Freeze%2CBS&author=Kravitz%2CAV&author=Hammack%2CN&author=Berke%2CJD&author=Kreitzer%2CAC) 
    
10.  Denny-Brown, D. & Yanagisawa, N. The role of the basal ganglia in the initiation of movement. *Res. Publ. Assoc. Res. Nerv. Ment. Dis.* **55**, 115–149 (1976).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:STN:280:DyaE2s%2FotVWnsg%3D%3D)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=826994)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=The%20role%20of%20the%20basal%20ganglia%20in%20the%20initiation%20of%20movement&journal=Res.%20Publ.%20Assoc.%20Res.%20Nerv.%20Ment.%20Dis.&volume=55&pages=115-149&publication_year=1976&author=Denny-Brown%2CD&author=Yanagisawa%2CN) 
    
11.  Mink, J. W. The basal ganglia: focused selection and inhibition of competing motor programs. *Prog. Neurobiol.* **50**, 381–425 (1996).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:STN:280:DyaK2s7lvVSksA%3D%3D)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=9004351)  [Article](https://doi.org/10.1016%2FS0301-0082%2896%2900042-1)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=The%20basal%20ganglia%3A%20focused%20selection%20and%20inhibition%20of%20competing%20motor%20programs&journal=Prog.%20Neurobiol.&volume=50&pages=381-425&publication_year=1996&author=Mink%2CJW) 
    
12.  Redgrave, P., Prescott, T. J. & Gurney, K. The basal ganglia: a vertebrate solution to the selection problem? *Neuroscience* **89**, 1009–1023 (1999).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DyaK1MXhslWqtL8%3D)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=10362291)  [Article](https://doi.org/10.1016%2FS0306-4522%2898%2900319-4)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=The%20basal%20ganglia%3A%20a%20vertebrate%20solution%20to%20the%20selection%20problem%3F&journal=Neuroscience&volume=89&pages=1009-1023&publication_year=1999&author=Redgrave%2CP&author=Prescott%2CTJ&author=Gurney%2CK) 
    
13.  Gouvêa, T. S. et al. Striatal dynamics explain duration judgments. *eLife* **4**, e11386 (2015).
    
    [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=26641377)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC4721960)  [Article](https://doi.org/10.7554%2FeLife.11386)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Striatal%20dynamics%20explain%20duration%20judgments&journal=eLife&volume=4&publication_year=2015&author=Gouv%C3%AAa%2CTS) 
    
14.  Soares, S., Atallah, B. V. & Paton, J. J. Midbrain dopamine neurons control judgment of time. *Science* **354**, 1273–1277 (2016).
    
    [ADS](http://adsabs.harvard.edu/cgi-bin/nph-data_query?link_type=ABSTRACT&bibcode=2016Sci...354.1273S)  [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC28XitVSrs7jJ)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=27940870)  [Article](https://doi.org/10.1126%2Fscience.aah5234)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Midbrain%20dopamine%20neurons%20control%20judgment%20of%20time&journal=Science&volume=354&pages=1273-1277&publication_year=2016&author=Soares%2CS&author=Atallah%2CBV&author=Paton%2CJJ) 
    
15.  Matias, S., Lottem, E., Dugué, G. P. & Mainen, Z. F. Activity patterns of serotonin neurons underlying cognitive flexibility. *eLife* **6**, e20552 (2017).
    
    [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=28322190)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC5360447)  [Article](https://doi.org/10.7554%2FeLife.20552)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Activity%20patterns%20of%20serotonin%20neurons%20underlying%20cognitive%20flexibility&journal=eLife&volume=6&publication_year=2017&author=Matias%2CS&author=Lottem%2CE&author=Dugu%C3%A9%2CGP&author=Mainen%2CZF) 
    
16.  Lima, S. Q., Hromádka, T., Znamenskiy, P. & Zador, A. M. PINP: a new method of tagging neuronal populations for identification during in vivo electrophysiological recording. *PLoS One* **4**, e6099 (2009).
    
    [ADS](http://adsabs.harvard.edu/cgi-bin/nph-data_query?link_type=ABSTRACT&bibcode=2009PLoSO...4.6099L)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=19584920)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC2702752)  [Article](https://doi.org/10.1371%2Fjournal.pone.0006099)  [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BD1MXosVKnur0%3D)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=PINP%3A%20a%20new%20method%20of%20tagging%20neuronal%20populations%20for%20identification%20during%20in%20vivo%20electrophysiological%20recording&journal=PLoS%20One&volume=4&publication_year=2009&author=Lima%2CSQ&author=Hrom%C3%A1dka%2CT&author=Znamenskiy%2CP&author=Zador%2CAM) 
    
17.  Jin, X. & Costa, R. M. Start/stop signals emerge in nigrostriatal circuits during sequence learning. *Nature* **466**, 457–462 (2010).
    
    [ADS](http://adsabs.harvard.edu/cgi-bin/nph-data_query?link_type=ABSTRACT&bibcode=2010Natur.466..457J)  [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC3cXptFGqtbs%3D)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=20651684)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3477867)  [Article](https://doi.org/10.1038%2Fnature09263)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Start%2Fstop%20signals%20emerge%20in%20nigrostriatal%20circuits%20during%20sequence%20learning&journal=Nature&volume=466&pages=457-462&publication_year=2010&author=Jin%2CX&author=Costa%2CRM) 
    
18.  Klaus, A. et al. The spatiotemporal organization of the striatum encodes action space. *Neuron* **96**, 949 (2017).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC2sXhvValtLbF)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=29144975)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC5696559)  [Article](https://doi.org/10.1016%2Fj.neuron.2017.10.031)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=The%20spatiotemporal%20organization%20of%20the%20striatum%20encodes%20action%20space&journal=Neuron&volume=96&publication_year=2017&author=Klaus%2CA) 
    
19.  Markowitz, J. E. et al. The striatum organizes 3D behavior via moment-to-moment action selection. *Cell* **174**, 44–58 (2018).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC1cXpvVemsrs%3D)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=29779950)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC6026065)  [Article](https://doi.org/10.1016%2Fj.cell.2018.04.019)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=The%20striatum%20organizes%203D%20behavior%20via%20moment-to-moment%20action%20selection&journal=Cell&volume=174&pages=44-58&publication_year=2018&author=Markowitz%2CJE) 
    
20.  Han, X. et al. A high-light sensitivity optical neural silencer: development and application to optogenetic control of non-human primate cortex. *Front. Syst. Neurosci.* **5**, 18 (2011).
    
    [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=21811444)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3082132)  [Article](https://doi.org/10.3389%2Ffnsys.2011.00018)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=A%20high-light%20sensitivity%20optical%20neural%20silencer%3A%20development%20and%20application%20to%20optogenetic%20control%20of%20non-human%20primate%20cortex&journal=Front.%20Syst.%20Neurosci.&volume=5&publication_year=2011&author=Han%2CX) 
    
21.  Nagel, G. et al. Channelrhodopsin-2, a directly light-gated cation-selective membrane channel. *Proc. Natl Acad. Sci. USA* **100**, 13940–13945 (2003).
    
    [ADS](http://adsabs.harvard.edu/cgi-bin/nph-data_query?link_type=ABSTRACT&bibcode=2003PNAS..10013940N)  [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BD3sXpsFGisbo%3D)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=14615590)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC283525)  [Article](https://doi.org/10.1073%2Fpnas.1936192100)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Channelrhodopsin-2%2C%20a%20directly%20light-gated%20cation-selective%20membrane%20channel&journal=Proc.%20Natl%20Acad.%20Sci.%20USA&volume=100&pages=13940-13945&publication_year=2003&author=Nagel%2CG) 
    
22.  Turner, R. S. & Desmurget, M. Basal ganglia contributions to motor control: a vigorous tutor. *Curr. Opin. Neurobiol.* **20**, 704–716 (2010).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC3MXmvFyitA%3D%3D)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=20850966)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3025075)  [Article](https://doi.org/10.1016%2Fj.conb.2010.08.022)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Basal%20ganglia%20contributions%20to%20motor%20control%3A%20a%20vigorous%20tutor&journal=Curr.%20Opin.%20Neurobiol.&volume=20&pages=704-716&publication_year=2010&author=Turner%2CRS&author=Desmurget%2CM) 
    
23.  Panigrahi, B. et al. Dopamine Is required for the neural representation and control of movement vigor. *Cell* **162**, 1418–1430 (2015).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC2MXhsV2lsLrL)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=26359992)  [Article](https://doi.org/10.1016%2Fj.cell.2015.08.014)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Dopamine%20Is%20required%20for%20the%20neural%20representation%20and%20control%20of%20movement%20vigor&journal=Cell&volume=162&pages=1418-1430&publication_year=2015&author=Panigrahi%2CB) 
    
24.  Dudman, J. T. & Krakauer, J. W. The basal ganglia: from motor commands to the control of vigor. *Curr. Opin. Neurobiol.* **37**, 158–166 (2016).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC28XjvVKjt7k%3D)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=27012960)  [Article](https://doi.org/10.1016%2Fj.conb.2016.02.005)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=The%20basal%20ganglia%3A%20from%20motor%20commands%20to%20the%20control%20of%20vigor&journal=Curr.%20Opin.%20Neurobiol.&volume=37&pages=158-166&publication_year=2016&author=Dudman%2CJT&author=Krakauer%2CJW) 
    
25.  Sutton, R. S. & Barto, A. G. *Reinforcement Learning: an Introduction* (MIT Press, 1998).
    
26.  Bornstein, A. M. & Daw, N. D. Multiplicity of control in the basal ganglia: computational roles of striatal subregions. *Curr. Opin. Neurobiol.* **21**, 374–380 (2011).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC3MXptVWisbg%3D)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=21429734)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3269306)  [Article](https://doi.org/10.1016%2Fj.conb.2011.02.009)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Multiplicity%20of%20control%20in%20the%20basal%20ganglia%3A%20computational%20roles%20of%20striatal%20subregions&journal=Curr.%20Opin.%20Neurobiol.&volume=21&pages=374-380&publication_year=2011&author=Bornstein%2CAM&author=Daw%2CND) 
    
27.  Shen, W., Flajolet, M., Greengard, P. & Surmeier, D. J. Dichotomous dopaminergic control of striatal synaptic plasticity. *Science* **321**, 848–851 (2008).
    
    [ADS](http://adsabs.harvard.edu/cgi-bin/nph-data_query?link_type=ABSTRACT&bibcode=2008Sci...321..848S)  [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BD1cXptlyhsLw%3D)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=18687967)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC2833421)  [Article](https://doi.org/10.1126%2Fscience.1160575)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Dichotomous%20dopaminergic%20control%20of%20striatal%20synaptic%20plasticity&journal=Science&volume=321&pages=848-851&publication_year=2008&author=Shen%2CW&author=Flajolet%2CM&author=Greengard%2CP&author=Surmeier%2CDJ) 
    
28.  Collins, A. G. E. & Frank, M. J. Opponent actor learning (OpAL): modeling interactive effects of striatal dopamine on reinforcement learning and choice incentive. *Psychol. Rev.* **121**, 337–366 (2014).
    
    [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=25090423)  [Article](https://doi.org/10.1037%2Fa0037015)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Opponent%20actor%20learning%20%28OpAL%29%3A%20modeling%20interactive%20effects%20of%20striatal%20dopamine%20on%20reinforcement%20learning%20and%20choice%20incentive&journal=Psychol.%20Rev.&volume=121&pages=337-366&publication_year=2014&author=Collins%2CAGE&author=Frank%2CMJ) 
    
29.  Gurney, K. N., Humphries, M. D. & Redgrave, P. A new framework for cortico-striatal plasticity: behavioural theory meets in vitro data at the reinforcement-action interface. *PLoS Biol.* **13**, e1002034 (2015).
    
    [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=25562526)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC4285402)  [Article](https://doi.org/10.1371%2Fjournal.pbio.1002034)  [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC28XptVCrtw%3D%3D)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=A%20new%20framework%20for%20cortico-striatal%20plasticity%3A%20behavioural%20theory%20meets%20in%20vitro%20data%20at%20the%20reinforcement-action%20interface&journal=PLoS%20Biol.&volume=13&publication_year=2015&author=Gurney%2CKN&author=Humphries%2CMD&author=Redgrave%2CP) 
    
30.  Iino, Y. et al. Dopamine D2 receptors in discrimination learning and spine enlargement. *Nature* **579**, 555–560 (2020).
    
    [ADS](http://adsabs.harvard.edu/cgi-bin/nph-data_query?link_type=ABSTRACT&bibcode=2020Natur.579..555I)  [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BB3cXltF2jsbc%3D)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=32214250)  [Article](https://doi.org/10.1038%2Fs41586-020-2115-1)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Dopamine%20D2%20receptors%20in%20discrimination%20learning%20and%20spine%20enlargement&journal=Nature&volume=579&pages=555-560&publication_year=2020&author=Iino%2CY) 
    
31.  Lee, S. J. et al. Cell-type-specific asynchronous modulation of PKA by dopamine in learning. *Nature* **590**, 451–456 (2021).
    
    [ADS](http://adsabs.harvard.edu/cgi-bin/nph-data_query?link_type=ABSTRACT&bibcode=2021Natur.590..451L)  [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BB3cXis1ygsr7I)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=33361810)  [Article](https://doi.org/10.1038%2Fs41586-020-03050-5)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Cell-type-specific%20asynchronous%20modulation%20of%20PKA%20by%20dopamine%20in%20learning&journal=Nature&volume=590&pages=451-456&publication_year=2021&author=Lee%2CSJ) 
    
32.  Dayan, P. Improving generalization for temporal difference learning: the successor representation. *Neural Comput.* **5**, 613–624 (1993).
    
    [Article](https://doi.org/10.1162%2Fneco.1993.5.4.613)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Improving%20generalization%20for%20temporal%20difference%20learning%3A%20the%20successor%20representation&journal=Neural%20Comput.&volume=5&pages=613-624&publication_year=1993&author=Dayan%2CP) 
    
33.  Stachenfeld, K. L., Botvinick, M. M. & Gershman, S. J. The hippocampus as a predictive map. *Nat. Neurosci.* **20**, 1643–1653 (2017).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC2sXhsFylurrF)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=28967910)  [Article](https://doi.org/10.1038%2Fnn.4650)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=The%20hippocampus%20as%20a%20predictive%20map&journal=Nat.%20Neurosci.&volume=20&pages=1643-1653&publication_year=2017&author=Stachenfeld%2CKL&author=Botvinick%2CMM&author=Gershman%2CSJ) 
    
34.  Tai, L.-H., Lee, A. M., Benavidez, N., Bonci, A. & Wilbrecht, L. Transient stimulation of distinct subpopulations of striatal neurons mimics changes in action value. *Nat. Neurosci.* **15**, 1281–1289 (2012).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC38Xht1Wkt7bF)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=22902719)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3951287)  [Article](https://doi.org/10.1038%2Fnn.3188)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Transient%20stimulation%20of%20distinct%20subpopulations%20of%20striatal%20neurons%20mimics%20changes%20in%20action%20value&journal=Nat.%20Neurosci.&volume=15&pages=1281-1289&publication_year=2012&author=Tai%2CL-H&author=Lee%2CAM&author=Benavidez%2CN&author=Bonci%2CA&author=Wilbrecht%2CL) 
    
35.  Majid, D. S. A., Cai, W., Corey-Bloom, J. & Aron, A. R. Proactive selective response suppression is implemented via the basal ganglia. *J. Neurosci.* **33**, 13259–13269 (2013).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC3sXhtlOjsLzO)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=23946385)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3742918)  [Article](https://doi.org/10.1523%2FJNEUROSCI.5651-12.2013)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Proactive%20selective%20response%20suppression%20is%20implemented%20via%20the%20basal%20ganglia&journal=J.%20Neurosci.&volume=33&pages=13259-13269&publication_year=2013&author=Majid%2CDSA&author=Cai%2CW&author=Corey-Bloom%2CJ&author=Aron%2CAR) 
    
36.  Watanabe, M. & Munoz, D. P. Presetting basal ganglia for volitional actions. *J. Neurosci.* **30**, 10144–10157 (2010).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC3cXhtVahsr%2FL)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=20668198)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC6633388)  [Article](https://doi.org/10.1523%2FJNEUROSCI.1738-10.2010)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Presetting%20basal%20ganglia%20for%20volitional%20actions&journal=J.%20Neurosci.&volume=30&pages=10144-10157&publication_year=2010&author=Watanabe%2CM&author=Munoz%2CDP) 
    
37.  Ford, K. A. & Everling, S. Neural activity in primate caudate nucleus associated with pro- and antisaccades. *J. Neurophysiol.* **102**, 2334–2341 (2009).
    
    [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=19692516)  [Article](https://doi.org/10.1152%2Fjn.00125.2009)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Neural%20activity%20in%20primate%20caudate%20nucleus%20associated%20with%20pro-%20and%20antisaccades&journal=J.%20Neurophysiol.&volume=102&pages=2334-2341&publication_year=2009&author=Ford%2CKA&author=Everling%2CS) 
    
38.  Amita, H. & Hikosaka, O. Indirect pathway from caudate tail mediates rejection of bad objects in periphery. *Sci. Adv.* **5**, eaaw9297 (2019).
    
    [ADS](http://adsabs.harvard.edu/cgi-bin/nph-data_query?link_type=ABSTRACT&bibcode=2019SciA....5.9297A)  [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BB3cXhtlarsr3M)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=31457095)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC6685718)  [Article](https://doi.org/10.1126%2Fsciadv.aaw9297)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Indirect%20pathway%20from%20caudate%20tail%20mediates%20rejection%20of%20bad%20objects%20in%20periphery&journal=Sci.%20Adv.&volume=5&publication_year=2019&author=Amita%2CH&author=Hikosaka%2CO) 
    
39.  Parent, A. & De Bellefeuille, L. Organization of efferent projections from the internal segment of globus pallidus in primate as revealed by flourescence retrograde labeling method. *Brain Res.* **245**, 201–213 (1982).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:STN:280:DyaL3s%2FisVWksg%3D%3D)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=7127069)  [Article](https://doi.org/10.1016%2F0006-8993%2882%2990802-2)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Organization%20of%20efferent%20projections%20from%20the%20internal%20segment%20of%20globus%20pallidus%20in%20primate%20as%20revealed%20by%20flourescence%20retrograde%20labeling%20method&journal=Brain%20Res.&volume=245&pages=201-213&publication_year=1982&author=Parent%2CA&author=Bellefeuille%2CL) 
    
40.  Lee, J. & Sabatini, B. L. Striatal indirect pathway mediates exploration via collicular competition. *Nature* **599**, 645–649 (2021).
    
    [ADS](http://adsabs.harvard.edu/cgi-bin/nph-data_query?link_type=ABSTRACT&bibcode=2021Natur.599..645L)  [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BB3MXisVSntLrI)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=34732888)  [Article](https://doi.org/10.1038%2Fs41586-021-04055-4)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Striatal%20indirect%20pathway%20mediates%20exploration%20via%20collicular%20competition&journal=Nature&volume=599&pages=645-649&publication_year=2021&author=Lee%2CJ&author=Sabatini%2CBL) 
    
41.  Tecuapetla, F., Matias, S., Dugue, G. P., Mainen, Z. F. & Costa, R. M. Balanced activity in basal ganglia projection pathways is critical for contraversive movements. *Nat. Commun.* **5**, 4315 (2014).
    
    [ADS](http://adsabs.harvard.edu/cgi-bin/nph-data_query?link_type=ABSTRACT&bibcode=2014NatCo...5.4315T)  [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC2cXitVWgsbrF)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=25002180)  [Article](https://doi.org/10.1038%2Fncomms5315)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Balanced%20activity%20in%20basal%20ganglia%20projection%20pathways%20is%20critical%20for%20contraversive%20movements&journal=Nat.%20Commun.&volume=5&publication_year=2014&author=Tecuapetla%2CF&author=Matias%2CS&author=Dugue%2CGP&author=Mainen%2CZF&author=Costa%2CRM) 
    
42.  Parker, J. G. et al. Diametric neural ensemble dynamics in parkinsonian and dyskinetic states. *Nature* **557**, 177–182 (2018).
    
    [ADS](http://adsabs.harvard.edu/cgi-bin/nph-data_query?link_type=ABSTRACT&bibcode=2018Natur.557..177P)  [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC1cXptVWktLk%3D)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=29720658)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC6526726)  [Article](https://doi.org/10.1038%2Fs41586-018-0090-6)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Diametric%20neural%20ensemble%20dynamics%20in%20parkinsonian%20and%20dyskinetic%20states&journal=Nature&volume=557&pages=177-182&publication_year=2018&author=Parker%2CJG) 
    
43.  Park, J., Coddington, L. T. & Dudman, J. T. Basal ganglia circuits for action specification. *Annu. Rev. Neurosci.* **43**, 485–507 (2020).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BB3cXnsV2rsr4%3D)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=32303147)  [Article](https://doi.org/10.1146%2Fannurev-neuro-070918-050452)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Basal%20ganglia%20circuits%20for%20action%20specification&journal=Annu.%20Rev.%20Neurosci.&volume=43&pages=485-507&publication_year=2020&author=Park%2CJ&author=Coddington%2CLT&author=Dudman%2CJT) 
    
44.  Alexander, G. E., DeLong, M. R. & Strick, P. L. Parallel organization of functionally segregated circuits linking basal ganglia and cortex. *Annu. Rev. Neurosci.* **9**, 357–381 (1986).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:STN:280:DyaL283htlKksw%3D%3D)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=3085570)  [Article](https://doi.org/10.1146%2Fannurev.ne.09.030186.002041)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Parallel%20organization%20of%20functionally%20segregated%20circuits%20linking%20basal%20ganglia%20and%20cortex&journal=Annu.%20Rev.%20Neurosci.&volume=9&pages=357-381&publication_year=1986&author=Alexander%2CGE&author=DeLong%2CMR&author=Strick%2CPL) 
    
45.  Prescott, T. J., Montes González, F. M., Gurney, K., Humphries, M. D. & Redgrave, P. A robot model of the basal ganglia: behavior and intrinsic processing. *Neural Netw.* **19**, 31–61 (2006).
    
    [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=16153803)  [MATH](http://www.emis.de/MATH-item?1092.68650)  [Article](https://doi.org/10.1016%2Fj.neunet.2005.06.049)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=A%20robot%20model%20of%20the%20basal%20ganglia%3A%20behavior%20and%20intrinsic%20processing&journal=Neural%20Netw.&volume=19&pages=31-61&publication_year=2006&author=Prescott%2CTJ&author=Montes%20Gonz%C3%A1lez%2CFM&author=Gurney%2CK&author=Humphries%2CMD&author=Redgrave%2CP) 
    
46.  Lau, B., Monteiro, T. & Paton, J. J. The many worlds hypothesis of dopamine prediction error: implications of a parallel circuit architecture in the basal ganglia. *Curr. Opin. Neurobiol.* **46**, 241–247 (2017).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC2sXhsVWmsbjK)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=28985550)  [Article](https://doi.org/10.1016%2Fj.conb.2017.08.015)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=The%20many%20worlds%20hypothesis%20of%20dopamine%20prediction%20error%3A%20implications%20of%20a%20parallel%20circuit%20architecture%20in%20the%20basal%20ganglia&journal=Curr.%20Opin.%20Neurobiol.&volume=46&pages=241-247&publication_year=2017&author=Lau%2CB&author=Monteiro%2CT&author=Paton%2CJJ) 
    
47.  Daw, N. D., Niv, Y. & Dayan, P. Uncertainty-based competition between prefrontal and dorsolateral striatal systems for behavioral control. *Nat. Neurosci.* **8**, 1704–1711 (2005).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BD2MXht1GisrfL)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=16286932)  [Article](https://doi.org/10.1038%2Fnn1560)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Uncertainty-based%20competition%20between%20prefrontal%20and%20dorsolateral%20striatal%20systems%20for%20behavioral%20control&journal=Nat.%20Neurosci.&volume=8&pages=1704-1711&publication_year=2005&author=Daw%2CND&author=Niv%2CY&author=Dayan%2CP) 
    
48.  Dorfman, H. M. & Gershman, S. J. Controllability governs the balance between Pavlovian and instrumental action selection. *Nat. Commun.* **10**, 5826 (2019).
    
    [ADS](http://adsabs.harvard.edu/cgi-bin/nph-data_query?link_type=ABSTRACT&bibcode=2019NatCo..10.5826D)  [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC1MXisVyrsbfL)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=31862876)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC6925275)  [Article](https://doi.org/10.1038%2Fs41467-019-13737-7)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Controllability%20governs%20the%20balance%20between%20Pavlovian%20and%20instrumental%20action%20selection&journal=Nat.%20Commun.&volume=10&publication_year=2019&author=Dorfman%2CHM&author=Gershman%2CSJ) 
    
49.  Dayan, P., Niv, Y., Seymour, B. & Daw, N. D. The misbehavior of value and the discipline of the will. *Neural Netw.* **19**, 1153–1160 (2006).
    
    [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=16938432)  [MATH](http://www.emis.de/MATH-item?1154.91632)  [Article](https://doi.org/10.1016%2Fj.neunet.2006.03.002)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=The%20misbehavior%20of%20value%20and%20the%20discipline%20of%20the%20will&journal=Neural%20Netw.&volume=19&pages=1153-1160&publication_year=2006&author=Dayan%2CP&author=Niv%2CY&author=Seymour%2CB&author=Daw%2CND) 
    
50.  Gerfen, C. R., Paletzki, R. & Heintz, N. GENSAT BAC cre-recombinase driver lines to study the functional organization of cerebral cortical and basal ganglia circuits. *Neuron* **80**, 1368–1383 (2013).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC3sXhvFyksrfN)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=24360541)  [Article](https://doi.org/10.1016%2Fj.neuron.2013.10.016)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=GENSAT%20BAC%20cre-recombinase%20driver%20lines%20to%20study%20the%20functional%20organization%20of%20cerebral%20cortical%20and%20basal%20ganglia%20circuits&journal=Neuron&volume=80&pages=1368-1383&publication_year=2013&author=Gerfen%2CCR&author=Paletzki%2CR&author=Heintz%2CN) 
    
51.  Madisen, L. et al. A toolbox of Cre-dependent optogenetic transgenic mice for light-induced activation and silencing. *Nat. Neurosci.* **15**, 793–802 (2012).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC38XksVenur8%3D)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=22446880)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3337962)  [Article](https://doi.org/10.1038%2Fnn.3078)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=A%20toolbox%20of%20Cre-dependent%20optogenetic%20transgenic%20mice%20for%20light-induced%20activation%20and%20silencing&journal=Nat.%20Neurosci.&volume=15&pages=793-802&publication_year=2012&author=Madisen%2CL) 
    
52.  Lopes, G. et al. Bonsai: an event-based framework for processing and controlling data streams. *Front. Neuroinform.* **9**, 7 (2015).
    
    [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=25904861)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC4389726)  [Article](https://doi.org/10.3389%2Ffninf.2015.00007)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Bonsai%3A%20an%20event-based%20framework%20for%20processing%20and%20controlling%20data%20streams&journal=Front.%20Neuroinform.&volume=9&publication_year=2015&author=Lopes%2CG) 
    
53.  Chen, T.-W. et al. Ultrasensitive fluorescent proteins for imaging neuronal activity. *Nature* **499**, 295–300 (2013).
    
    [ADS](http://adsabs.harvard.edu/cgi-bin/nph-data_query?link_type=ABSTRACT&bibcode=2013Natur.499..295C)  [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC3sXhtFalsrrI)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=23868258)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3777791)  [Article](https://doi.org/10.1038%2Fnature12354)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Ultrasensitive%20fluorescent%20proteins%20for%20imaging%20neuronal%20activity&journal=Nature&volume=499&pages=295-300&publication_year=2013&author=Chen%2CT-W) 
    
54.  Pisanello, F. et al. Dynamic illumination of spatially restricted or large brain volumes via a single tapered optical fiber. *Nat. Neurosci.* **20**, 1180–1188 (2017).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC2sXhtVantLzE)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=28628101)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC5533215)  [Article](https://doi.org/10.1038%2Fnn.4591)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Dynamic%20illumination%20of%20spatially%20restricted%20or%20large%20brain%20volumes%20via%20a%20single%20tapered%20optical%20fiber&journal=Nat.%20Neurosci.&volume=20&pages=1180-1188&publication_year=2017&author=Pisanello%2CF) 
    
55.  Siegle, J. H. et al. Open Ephys: an open-source, plugin-based platform for multichannel electrophysiology. *J. Neural Eng.* **14**, 045003 (2017).
    
    [ADS](http://adsabs.harvard.edu/cgi-bin/nph-data_query?link_type=ABSTRACT&bibcode=2017JNEng..14d5003S)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=28169219)  [Article](https://doi.org/10.1088%2F1741-2552%2Faa5eea)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Open%20Ephys%3A%20an%20open-source%2C%20plugin-based%20platform%20for%20multichannel%20electrophysiology&journal=J.%20Neural%20Eng.&volume=14&publication_year=2017&author=Siegle%2CJH) 
    
56.  Benhamou, L., Kehat, O. & Cohen, D. Firing pattern characteristics of tonically active neurons in rat striatum: context dependent or species divergent? *J. Neurosci.* **34**, 2299–2304 (2014).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC2cXisVGrtrc%3D)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=24501368)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC6608530)  [Article](https://doi.org/10.1523%2FJNEUROSCI.1798-13.2014)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Firing%20pattern%20characteristics%20of%20tonically%20active%20neurons%20in%20rat%20striatum%3A%20context%20dependent%20or%20species%20divergent%3F&journal=J.%20Neurosci.&volume=34&pages=2299-2304&publication_year=2014&author=Benhamou%2CL&author=Kehat%2CO&author=Cohen%2CD) 
    
57.  Yael, D. et al. Haloperidol-induced changes in neuronal activity in the striatum of the freely moving rat. *Front. Syst. Neurosci.* **7**, 110 (2013).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC2cXhslKhsrjJ)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=24379762)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3864134)  [Article](https://doi.org/10.3389%2Ffnsys.2013.00110)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Haloperidol-induced%20changes%20in%20neuronal%20activity%20in%20the%20striatum%20of%20the%20freely%20moving%20rat&journal=Front.%20Syst.%20Neurosci.&volume=7&publication_year=2013&author=Yael%2CD) 
    
58.  Rennaker, R. L., Miller, J., Tang, H. & Wilson, D. A. Minocycline increases quality and longevity of chronic neural recordings. *J. Neural Eng.* **4**, L1–L5 (2007).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:STN:280:DC%2BD2s3gs1Kjsg%3D%3D)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=17409469)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC2291199)  [Article](https://doi.org/10.1088%2F1741-2560%2F4%2F2%2FL01)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Minocycline%20increases%20quality%20and%20longevity%20of%20chronic%20neural%20recordings&journal=J.%20Neural%20Eng.&volume=4&pages=L1-L5&publication_year=2007&author=Rennaker%2CRL&author=Miller%2CJ&author=Tang%2CH&author=Wilson%2CDA) 
    
59.  Kvitsiani, D. et al. Distinct behavioural and network correlates of two interneuron types in prefrontal cortex. *Nature* **498**, 363–366 (2013).
    
    [ADS](http://adsabs.harvard.edu/cgi-bin/nph-data_query?link_type=ABSTRACT&bibcode=2013Natur.498..363K)  [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC3sXotFSgsbs%3D)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=23708967)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC4349584)  [Article](https://doi.org/10.1038%2Fnature12176)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Distinct%20behavioural%20and%20network%20correlates%20of%20two%20interneuron%20types%20in%20prefrontal%20cortex&journal=Nature&volume=498&pages=363-366&publication_year=2013&author=Kvitsiani%2CD) 
    
60.  Chuong, A. S. et al. Noninvasive optical inhibition with a red-shifted microbial rhodopsin. *Nat. Neurosci.* **17**, 1123–1129 (2014).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC2cXhtFSlsL3L)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=24997763)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC4184214)  [Article](https://doi.org/10.1038%2Fnn.3752)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Noninvasive%20optical%20inhibition%20with%20a%20red-shifted%20microbial%20rhodopsin&journal=Nat.%20Neurosci.&volume=17&pages=1123-1129&publication_year=2014&author=Chuong%2CAS) 
    
61.  Mathis, A. et al. DeepLabCut: markerless pose estimation of user-defined body parts with deep learning. *Nat. Neurosci.* **21**, 1281–1289 (2018).
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC1cXhsFGjtLnF)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=30127430)  [Article](https://doi.org/10.1038%2Fs41593-018-0209-y)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=DeepLabCut%3A%20markerless%20pose%20estimation%20of%20user-defined%20body%20parts%20with%20deep%20learning&journal=Nat.%20Neurosci.&volume=21&pages=1281-1289&publication_year=2018&author=Mathis%2CA) 
    
62.  Bates, D., Mächler, M., Bolker, B. & Walker, S. Fitting Linear Mixed-Effects Models Using lme4. *J. Stat. Softw*. **67**, [https://doi.org/10.18637/jss.v067.i011](https://doi.org/10.18637/jss.v067.i011) (2015).
    
63.  Searle, S. R., Speed, F. M. & Milliken, G. A. Population marginal means in the linear model: an alternative to least squares means. *Am. Stat.* **34**, 216–221 (1980).
    
    [MathSciNet](http://www.ams.org/mathscinet-getitem?mr=596242)  [MATH](http://www.emis.de/MATH-item?0468.62066)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Population%20marginal%20means%20in%20the%20linear%20model%3A%20an%20alternative%20to%20least%20squares%20means&journal=Am.%20Stat.&volume=34&pages=216-221&publication_year=1980&author=Searle%2CSR&author=Speed%2CFM&author=Milliken%2CGA) 
    
64.  Lenth, R. Least-squares means: the R package lsmeans. *J. Stat. Softw*. **69**, [https://doi.org/10.18637/jss.v069.i01](https://doi.org/10.18637/jss.v069.i01) (2016).
    
65.  Gibbon, J. Scalar expectancy theory and Weber’s law in animal timing. *Psychol. Rev.* **84**, 279–325 (1977).
    
    [Article](https://doi.org/10.1037%2F0033-295X.84.3.279)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Scalar%20expectancy%20theory%20and%20Weber%E2%80%99s%20law%20in%20animal%20timing&journal=Psychol.%20Rev.&volume=84&pages=279-325&publication_year=1977&author=Gibbon%2CJ) 
    
66.  Merel, J., Botvinick, M. & Wayne, G. Hierarchical motor control in mammals and machines. *Nat. Commun.* **10**, 5489 (2019).
    
    [ADS](http://adsabs.harvard.edu/cgi-bin/nph-data_query?link_type=ABSTRACT&bibcode=2019NatCo..10.5489M)  [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=31792198)  [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC6889345)  [Article](https://doi.org/10.1038%2Fs41467-019-13239-6)  [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC1MXitlSqt73E)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Hierarchical%20motor%20control%20in%20mammals%20and%20machines&journal=Nat.%20Commun.&volume=10&publication_year=2019&author=Merel%2CJ&author=Botvinick%2CM&author=Wayne%2CG) 
    
67.  Motiwala, A., Soares, S., Atallah, B. V., Paton, J. J. & Machens, C. K. Efficient coding of cognitive variables underlies dopamine response and choice behavior. *Nat. Neurosci.* **25**, 738–748 (2022).
    
68.  Grondman, I., Busoniu, L., Lopes, G. A. D. & Babuska, R. A survey of actor-critic reinforcement learning: standard and natural policy gradients. In *IEEE Transactions on Systems, Man, and Cybernetics, Part C (Applications and Reviews)* Vol 42, 1291–1307 (IEEE, 2012).
    
69.  Buşoniu, L., Babuška, R. & De Schutter, B. in *Innovations in Multi-Agent Systems and Applications - 1* (eds Srinivasan, D. & Jain, L. C.) 183–221 (Springer, 2010).
    
70.  Franklin, K. B. J. & Paxinos, G. *The Mouse Brain in Stereotaxic Coordinates* 3rd edn (Academic Press, 2008).
    

[Download references](https://citation-needed.springer.com/v2/references/10.1038/s41586-022-04894-9?format=refman&flavour=references)

## Acknowledgements

We thank B. Lau, J. Krakauer, E. DeWitt, B. Atallah, A. Klaus and T. Monteiro for comments on different versions of the manuscript and the entire J.J.P. laboratory for feedback during the course of this project. We also thank the ABBE Facility and the Scientific Hardware, Histopathology and Rodent Champalimaud Research Platforms for technical assistance, and B. Zarov and D. Domingues for helping with the training of some of the mice in this study. This work was developed with the support from the research infrastructure Congento, co-financed by Lisboa Regional Operational Programme (Lisboa2020), under the PORTUGAL 2020 Partnership Agreement, through the European Regional Development Fund (ERDF) and Fundação para a Ciência e Tecnologia (Portugal) under the project LISBOA-01-0145-FEDER-022170. The work was funded by an HHMI International Research Scholar Award to J.J.P. (55008745); a European Research Council Consolidator grant (DYCOCIRC - REP-772339-1) to J.J.P.; a Bial bursary for scientific research to J.J.P. (193/2016); internal support from the Champalimaud Foundation; and PhD fellowships (PD/BD/105945/2014 and PD/BD/128301/2017) from Fundação para a Ciência e Tecnologia to B.F.C. and G.G. respectively.

## Author information

Author notes

1.  Sofia Soares
    
    Present address: Department of Neurobiology, Harvard Medical School, Boston, MA, USA
    
2.  Asma Motiwala
    
    Present address: Electrical and Computer Engineering, Carnegie Mellon University, Pittsburgh, PA, USA
    

### Authors and Affiliations

1.  Champalimaud Neuroscience Programme, Champalimaud Research, Champalimaud Foundation, Lisbon, PT, Portugal
    
    Bruno F. Cruz, Gonçalo Guiomar, Sofia Soares, Asma Motiwala, Christian K. Machens & Joseph J. Paton
    

Authors

1.  Bruno F. Cruz
    
    You can also search for this author in [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=search&term=Bruno%20F.%20Cruz) [Google Scholar](http://scholar.google.co.uk/scholar?as_q=&num=10&btnG=Search+Scholar&as_epq=&as_oq=&as_eq=&as_occt=any&as_sauthors=%22Bruno%20F.%20Cruz%22&as_publication=&as_ylo=&as_yhi=&as_allsubj=all&hl=en)
    
2.  Gonçalo Guiomar
    
    You can also search for this author in [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=search&term=Gon%C3%A7alo%20Guiomar) [Google Scholar](http://scholar.google.co.uk/scholar?as_q=&num=10&btnG=Search+Scholar&as_epq=&as_oq=&as_eq=&as_occt=any&as_sauthors=%22Gon%C3%A7alo%20Guiomar%22&as_publication=&as_ylo=&as_yhi=&as_allsubj=all&hl=en)
    
3.  Sofia Soares
    
    You can also search for this author in [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=search&term=Sofia%20Soares) [Google Scholar](http://scholar.google.co.uk/scholar?as_q=&num=10&btnG=Search+Scholar&as_epq=&as_oq=&as_eq=&as_occt=any&as_sauthors=%22Sofia%20Soares%22&as_publication=&as_ylo=&as_yhi=&as_allsubj=all&hl=en)
    
4.  Asma Motiwala
    
    You can also search for this author in [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=search&term=Asma%20Motiwala) [Google Scholar](http://scholar.google.co.uk/scholar?as_q=&num=10&btnG=Search+Scholar&as_epq=&as_oq=&as_eq=&as_occt=any&as_sauthors=%22Asma%20Motiwala%22&as_publication=&as_ylo=&as_yhi=&as_allsubj=all&hl=en)
    
5.  Christian K. Machens
    
    You can also search for this author in [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=search&term=Christian%20K.%20Machens) [Google Scholar](http://scholar.google.co.uk/scholar?as_q=&num=10&btnG=Search+Scholar&as_epq=&as_oq=&as_eq=&as_occt=any&as_sauthors=%22Christian%20K.%20Machens%22&as_publication=&as_ylo=&as_yhi=&as_allsubj=all&hl=en)
    
6.  Joseph J. Paton
    
    You can also search for this author in [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=search&term=Joseph%20J.%20Paton) [Google Scholar](http://scholar.google.co.uk/scholar?as_q=&num=10&btnG=Search+Scholar&as_epq=&as_oq=&as_eq=&as_occt=any&as_sauthors=%22Joseph%20J.%20Paton%22&as_publication=&as_ylo=&as_yhi=&as_allsubj=all&hl=en)
    

### Contributions

J.J.P. and B.F.C. conceived of the experiments and wrote the manuscript. S.S. assisted in analysis of the fibre photometry data and helped revise the manuscript. B.F.C. performed all experiments and analysed the data. G.G., B.F.C. and J.J.P. conceived of the model with assistance from A.M. G.G. built the model and performed all simulations. C.K.M. provided constructive feedback about the model and helped revise the manuscript. J.J.P. supervised all aspects of the project.

### Corresponding author

Correspondence to [Joseph J. Paton](mailto:joe.paton@research.fchampalimaud.org).

## Ethics declarations

### Competing interests

The authors declare no competing financial interests.

## Peer review

### Peer review information

*Nature* thanks the anonymous reviewers for their contribution to the peer review of this work. [Peer reviewer reports](https://www.nature.com/articles/s41586-022-04894-9#FPar1) are available.

## Additional information

**Publisher’s note** Springer Nature remains neutral with regard to jurisdictional claims in published maps and institutional affiliations.

## Extended data figures and tables

### [Extended Data Fig. 1 Histological reconstruction of sites of fibre implantation for photometry, electrophysiology and optogenetic experiments in the DLS and the DMS.](https://www.nature.com/articles/s41586-022-04894-9/figures/5)

**a**–**d**, Photometry (**a**), electrophysiology (**b**) and optogenetic experiments in the DLS (**c**) and the DMS (**d**). Mice are coloured by their genotype according to the legend. For electrophysiology and optogenetics experiments, the DV coordinate is shown as the deepest position of the shanks or tapered fibre, respectively, was observed in histological slices. All coordinates were projected to the same coronal slice (AP = +0.5 from bregma) adapted from[70](https://www.nature.com/articles/s41586-022-04894-9#ref-CR70 "Franklin, K. B. J. & Paxinos, G. The Mouse Brain in Stereotaxic Coordinates 3rd edn (Academic Press, 2008)."). Behaviour metrics across genotypes (e-n). A2a-Cre and D1-Cre single mice, included in the photometry experiments, are shown in red and blue, respectively. Single-mouse psychometric curve **(e)** fits and respective parameters (see [Methods](https://www.nature.com/articles/s41586-022-04894-9#Sec7) for further details, two-tailed t-test, **f**, p = 0.935, t12 = 0.083, **g**, P = 0.17, t12 = −1.459, **h**, P = 0.823, t12 = 0.228, **i**, P = 0.826, t12 = −0.225). **j**, Overall probability of breaking fixation (all trials included) (P = 0.665, t12 = 0.445) **k**, Percentage of trials in which mice attempted to make a choice after breaking fixation (all trials included) (P = 0.703, t12 = 0.391). **l**, Probability of reporting at the “long choice” port after breaking fixation contingent on whether the mouse aborted before (<−1.5 s) or after (>1.5 s) the decision boundary (P = 0.872, t12 = −0.165). **m**, Left, Hazard of breaking fixation in time for single mice (thin curves) and overall averages within genotype (thick lines). Right, differences between the hazard of breaking fixation after and before the decision boundary(P = 0.165, t12  = 1.48). **n**, Mean velocity during the delay period from correct trials of the longest interval (2.4 s, Data from Fig. [1c](https://www.nature.com/articles/s41586-022-04894-9#Fig1), P = 0.892, t12 = −0.139). Error bars represent s.e.m. n.s. P > 0.05.

[Source data](https://www.nature.com/articles/s41586-022-04894-9#MOESM8)

### [Extended Data Fig. 2 Photometry activity during the period of active immobility and movement.](https://www.nature.com/articles/s41586-022-04894-9/figures/6)

a) Average activity across both hemispheres during the immobility period for each hemisphere (data points) relative to baseline, and across mice. Activity for iMSNs and dMSNs is shown in red and blue, respectively (n = 16 hemispheres, from 8 A2a-Cre mice, n = 10 hemispheres from 6 D1-Cre mice, only correct trials were included). **b**,**c**, Difference between average activity after the 1.5-s decision boundary, and before the 1.5-s decision boundary (>1.5 s - <1.5 s) for activity recorded in the hemisphere contralateral to the side of the long choice port (CL, contra-long, b, N = 8 A2a-Cre and 5 D1-Cre mice)) and for activity recorded in the hemisphere contralateral to the short choice port (CS, contra-short, c, N = 8 A2a-Cre and 5 D1-Cre mice)). White lines and boxes represent mean and s.e.m., respectively. d-e) Both DLS direct and indirect pathways are more active during contralateral movements. Photometry signal recorded from from A2a-Cre **(d)** and D1-Cre **(e)**, aligned to leaving the centre port during a near boundary interval (1.74s) where the same stimulus results in different choices (ipsilateral and contralateral to the recorded hemisphere, depicted as cyan and orange, respectively). Same trial selection as Fig. [2e](https://www.nature.com/articles/s41586-022-04894-9#Fig2). All boxes or shaded regions represent mean ± s.e.m.

[Source data](https://www.nature.com/articles/s41586-022-04894-9#MOESM9)

### [Extended Data Fig. 3 The photo-identified iMSN population is enriched in cells with a higher firing rate during the delay period.](https://www.nature.com/articles/s41586-022-04894-9/figures/7)

**a**, Activity profile of photo-identified indirect-pathway MSNs (photo-Ided iMSNs) and non-photo-identified putative MSNs (see [methods](https://www.nature.com/articles/s41586-022-04894-9#Sec7) for details). Each row represents a unit’s z-scored activity aligned to trial initiation that results from averaging the activity for all intervals cropped at second tone. Units are ordered by the angular position formed by the first two principal component projections. PCs were computed using a period of −2 to 2.4 s from trial initiation. **b**, Cumulative distribution of changes in firing rate during the delay period of photo-Ided iMSN (red) and all other putative MSNs (blue). Average ΔFR is significantly larger for iMSNs when compared to the distribution of non-identified cells (two-tailed t-test, P = 0.0196, t286 = 2.35). **c**, Proportion of up, down, and not modulated cells during the delay period (see [methods](https://www.nature.com/articles/s41586-022-04894-9#Sec7) for details). Proportions are significantly different between the two groups (Chi-squared test, P = 0.0115, χ22 = 8.939). **d**, Example of putative MSNs (pMSNs) classified as photo-identified. Top) Raster plot with single spikes aligned to laser pulse onset (2-ms duration). Bottom-Left) Distribution of latencies of the first spike observed in a 1–10ms after laser pulse onset. Bottom-right) mean waveform (black) and mean laser-triggered waveform (red). **e**,**h**, Distribution of: **e**, probability of observing a spike between 1 and 10ms after laser onset pulse, **f**, differences in firing rate between the baseline and 1–10ms post-pulse window, **g**, correlation coefficient (ρ) between mean waveform and mean laser-triggered waveform, **h**, median latency of the first spike in a window 1–50 ms after pulse onset (trials wherein no spike was observed in this window were not included).

[Source data](https://www.nature.com/articles/s41586-022-04894-9#MOESM10)

### [Extended Data Fig. 4 Changes of activity in the indirect pathway preceding broken fixations.](https://www.nature.com/articles/s41586-022-04894-9/figures/8)

**a**, Differences on the rate (derivative) of activity change (d(ΔF/FBrokenFixation)/dt- d(ΔF/FValid)/dt) aligned on broken fixations calculated from data recorded from A2a-Cre mice (16 hemispheres from 8 mice). **b**, Difference of mean activity (FRBrokenFixation\- FRValid, Hz) of all photo-identified units not modulated (left, N = 46 units), positively modulated (centre, N = 12 units) and negatively modulated (right, N = 31 units) during the delay period. Blue lines depict periods during which there are significant differences between the average activity average activity on broken fixations and valid trials, across cells (two-tailed, paired t-test, p \\(\\leqslant \\) 0.05). **c**, Schematic depicting the analysis performed in a) and b) in order to compared activity aligned to broken fixation trials. In brief, we took valid (black), or broken fixation (green), trials aligned to trial initiation (first-tone onset) cropped them at second tone or at the broken fixation event, respectively. We used the valid trials to compute a reference “valid trial” that reflected the average activity of all valid trials, cropped at second tone (mid, orange). Averaging available data (i.e. up until second tone) guarantees that only data from the fixation period is used, without incurring into contamination due to movement onset after the cue is delivered. We subsequently align each broken fixation trial to its occurrence (right) and take, from the reference valid trace, a time-matched fragment which we align to the same time since first tone. To compare traces aligned on broken fixation events to valid trials, we then average all broken fixation trials and the corresponding time-matched valid reference traces (see [methods](https://www.nature.com/articles/s41586-022-04894-9#Sec7)). **d**, Same analysis as in Fig. [3l](https://www.nature.com/articles/s41586-022-04894-9#Fig3) but for an epoch \[−0.5:−0.4\]s relative to broken fixation events (Linear regression, slope = −0.042, P = 0.132, t87 = −1.522). Error bars represent s.e.m. n.s. P > 0.05.

[Source data](https://www.nature.com/articles/s41586-022-04894-9#MOESM11)

### [Extended Data Fig. 5 Electrophysiological identification of putative MSNs and summary effect of opsin activation.](https://www.nature.com/articles/s41586-022-04894-9/figures/9)

**a**, Identification of putative MSNs based on firing statistics and waveform duration (see [methods](https://www.nature.com/articles/s41586-022-04894-9#Sec7)). Green data points indicate units ultimately identified as putative MSNs (pMSNs). **b**, Changes in firing rate during light delivery and baseline period versus the baseline firing rate of all recorded isolated units (Including non- putative MSN units) from A2a-Cre (red) and D1-Cre (blue) mice infected with ArchT. Significantly negatively or positively modulated cells are shown as closed and open circles, respectively. Maximum theoretical inhibition is plotted as a grey dashed line (−ΔFR = Baseline FR). **c**, Distribution of changes in firing rate (Hz) during the period of light delivery, versus baseline, for putatively labelled MSN units recorded from A2a (Red) and D1-Cre (Blue) mice expressing ArchT, outside the context of the task. Grey depicts non-significantly modulated cells, closed and open shapes depict significantly down- and upmodulated cells, respectively. **d**, Overall average peristimulus time histogram of all negatively light-modulated cells, putatively labelled as MSNs, recorded from A2a-Cre and D1-Cre mice during the ArchT acute experiment. All units were z-scored (see [methods](https://www.nature.com/articles/s41586-022-04894-9#Sec7)). Shaded coloured area depicts the time of laser illumination. **e**–**h**, Same as **b**–**d** but for mice expressing ChR2 in MSNs. **i**, Summary of overall modulation effects of ArchT versus ChR2 activation in pMSNs.

[Source data](https://www.nature.com/articles/s41586-022-04894-9#MOESM12)

### [Extended Data Fig. 6 Manipulation-induced changes in vigour and action selection depend on MSN type and striatum sub-location.](https://www.nature.com/articles/s41586-022-04894-9/figures/10)

**a**, Cartoon depicts the three different manipulated trial types:Choice Time (Delay), laser was ramped off as the second tone is played. BrokenFix Choice Time (Delay), laser was ramped off as the mouse leaves the centre port causing a broken fixation. MovementTime (Decision) laser was turned on as the second tone is played until the mouse either performs its choice or 400ms elapse, whichever occurs first. **b**, Differences in single mouse’s median choice time between inhibited and non-inhibited trials (ΔChoiceTime = ChoiceTimeManipulation - ChoiceTimeControl). For each mouse, we concatenated all sessions and split trials in manipulated versus non-manipulated. From top to bottom: two-tailed t-test, P = 0.198, t5 = 1.482; P = 0.198, t5 = 1.482; P = 0.005, t5 = 4.834; P = 0.128, t2 = 2.523; P = 0.718, t4 = 0.388; P = 0.46, t4 = −0.817; P = 0.617, t5 = −0.533; P = 0.774, t5 = −0.304; P = 0.032, t5 = 2.959; P = 0.005, t5 = 4.876; P = 0.247, t5 = 1.309; P = 0.306, t5 = 1.141. **c**, Differences in probability of reporting a contralateral choice, relative to inhibition side (ΔP = P\_ContraManipulation - P\_ContraControl). For each mouse, we concatenated sessions from sessions with unilateral perturbation and normalized choices to the side contralateral to inhibition site. From top to bottom:P = 0.597, t11 = −0.545; P = 0.427, t11 = −0.824; P = 0.259, t5 = −1.274; P = 0.149, t7 = 1.623; P << 0.001, t7 = 6.605; P = 0.365, t11 = 1.623; P = 0.028, t11 = −2.528; P = 0.94, t11 = 0.077; P = 0.933, t11 = −0.086; P = 0.985, t11 = −0.02; P = 0.143, t11 = 1.577. All boxes represent mean ± s.e.m. \*P ≤ 0.05, \*\*P ≤ 0.01, \*\*P ≤ 0.001.

[Source data](https://www.nature.com/articles/s41586-022-04894-9#MOESM13)

### [Extended Data Fig. 7 Further quantification of the effects of selective unilateral inhibition of DLS MSNs on broken fixation trials (see Fig.](https://www.nature.com/articles/s41586-022-04894-9/figures/11) [3](https://www.nature.com/articles/s41586-022-04894-9#Fig3)).

**a**,**b**, Same as Fig. [3m,q](https://www.nature.com/articles/s41586-022-04894-9#Fig3), respectively, but expressed as the hazard rate of breaking fixation (see [Methods](https://www.nature.com/articles/s41586-022-04894-9#Sec7)). **c**, Quantification of the effect shown in Fig. [3m](https://www.nature.com/articles/s41586-022-04894-9#Fig3). We calculated the hazard of breaking fixation during the period where the choice contralateral to the site of inhibition would be correct or incorrect (before/after 1.5 s and after/before 1.5 s for CS and CL, respectively). Data shown are the differences between session matched controls and manipulations. Each pair of points depicts data from the same hemisphere and the colour the site of manipulation. (contralateral\_correct: two-tailed t-test, P = 0.005, t7 = 4.055, contralateral\_incorrect: P = 0.215, t7 = −1.363, N = 8 Hemispheres). **d**, Same as a) but referent to Fig. [3q](https://www.nature.com/articles/s41586-022-04894-9#Fig3). (contralateral\_correct: two-tailed t-test, P = 0.711, t11 = 0.38, contralateral\_incorrect: P = 0.211, t11 = 1.329, N = 12 Hemispheres) **e**, Bias to report a contralateral choice after inhibition of iMSNs is not explained by the tendency of mice to make particular choices after breaking fixation early or late in the delay. Each panel, one for manipulations performed in each hemisphere, depicts the data shown in Fig. [3l](https://www.nature.com/articles/s41586-022-04894-9#Fig3) further split by whether fixation was broken before or after the 1.5-s decision boundary. All Error bars or boxes represent mean ± s.e.m. n.s. P > 0.05, \*\*P ≤ 0.01.

[Source data](https://www.nature.com/articles/s41586-022-04894-9#MOESM14)

### [Extended Data Fig. 8 Unilateral DLS indirect-pathway inhibition did not systematically affect movement trajectories across subject mice.](https://www.nature.com/articles/s41586-022-04894-9/figures/12)

. **a**, Example trajectories for a single mouse aligned to centre-out for choices to the “Long port” (red) or “Short pot” (blue) for completed trials (Left) and Broken fixation trials (Right). Trials are further broken down by whether the indirect pathway was inhibited (bottom) or not (top) in mice implanted in the DLS. **b**, same as a) but for trajectories measured during the delay period (up until second tone or broken fixation events). **c**) Quantitative differences between trajectory distributions among different conditions. In brief, we computed a mean reference trajectory from “Valid & Non-inhibited” condition and computed, for each trial from each condition, the average Euclidean distance to this reference trajectory. Values shown in the heat maps correspond to the means of these distributions. Significance was accessed by computing a two-sample Kolmogorov–Smirnov test between the reference and testing condition (P ⩽ 0.05 is reported as a red dots).

[Source data](https://www.nature.com/articles/s41586-022-04894-9#MOESM15)

### [Extended Data Fig. 9 Inhibition of DMS dMSNs has a mild effect on the probability of reporting a contralateral action, in the absence of changes in broken fixation rates.](https://www.nature.com/articles/s41586-022-04894-9/figures/13)

**a**, Overall probability of breaking fixation during dMSN inhibition experiments. Coloured and black dots represent data from laser-on and laser-off trials, respectively. “Bilateral” condition represents data from sessions wherein light was delivered bilaterally to the DMS (two-tailed t-test, P = 0.893, t5 = −0.141, N = 6 pairs of hemispheres) whereas “unilateral” represents data from sessions wherein light was delivered to a single hemisphere. (two-tailed t-test, P = 0.09, t11 = −1.861,N = 12 hemispheres. Green/Purple code for CS/CL manipulation sessions, respectively). **b**, Change in probability of registering a choice at the port contralateral to the hemisphere manipulated, after breaking fixation (ΔP = PManipulation - PControl, two-tailed t-test, P = 0.028, t11 = −2.528, N = 12 hemispheres). **c**, Quantification of the effect shown in d) (contralateral\_correct: two-tailed t-test, P = 0.076, t11 = −1.961; contralateral\_incorrect: P = 0.383, t11 = −0.909). We calculated the hazard of breaking fixation during the period where the choice contralateral to the site of inhibition would be correct or incorrect (before/after 1.5 s and after/before 1.5 s for CS and CL, respectively). **d**, Distribution of broken fixation times, expressed as the histogram of trial counts normalized over all included trials of a given condition. **e**, Change in hazard (ΔH = HManipulation - HControl, N = 12 Hemispheres) due to inhibition of the CS (green) or CL (pruple) relative to session matched control trials. **f**–**j**, Same as a-e) but for A2a-Cre mice implanted in the DMS. (f) Bilateral: two-tailed t-test, P = 0.463, t5 = 0.795, N = 6 pairs of hemispheres; Unilateral: two-tailed t-test, P = 0.233, t11 = 1.262, 12 hemispheres. g) two-tailed t-test, P = 0.985, t11 = −0.02, N = 12 hemispheres. **h**, contralateral\_correct: two-tailed t-test, P = 0.149, t11 = 1.551; contralateral\_incorrect: P = 0.207, t11 = 1.339, N = 12 hemispheres. All error bars or boxes represent mean ± s.e.m. n.s. P > 0.05, \*P ≤ 0.05.

[Source data](https://www.nature.com/articles/s41586-022-04894-9#MOESM16)

### [Extended Data Fig. 10 The model’s pattern of broken fixations when inhibiting the DLS indirect pathway.](https://www.nature.com/articles/s41586-022-04894-9/figures/14)

Same data as Fig. [4m](https://www.nature.com/articles/s41586-022-04894-9#Fig4) but expressed as hazard rate (see [Methods](https://www.nature.com/articles/s41586-022-04894-9#Sec7) for details). **a**, Hazard of breaking fixation for the control (black outline) and inhibition conditions resulting from the selective reduction of action preference values for the Indirect pathway (*A**L*,*I**(s**t**L*,*a**t**))* for the SHORT (green) or LONG (purple) actions. **b**, Change in hazard rate (ΔHR = HRManipulation\- HRControl).

## Supplementary information

### [Supplementary Tables](https://static-content.springer.com/esm/art%3A10.1038%2Fs41586-022-04894-9/MediaObjects/41586_2022_4894_MOESM1_ESM.pdf)

This file contains Supplementary Table 1: Summary of statistical tests performed in the study and additional relevant information; and Supplementary Table 2: Summary of the training procedure for the Opponent Multi-Agent Actor-Critic algorithm.

### [Reporting Summary](https://static-content.springer.com/esm/art%3A10.1038%2Fs41586-022-04894-9/MediaObjects/41586_2022_4894_MOESM2_ESM.pdf)

### [Peer Review File](https://static-content.springer.com/esm/art%3A10.1038%2Fs41586-022-04894-9/MediaObjects/41586_2022_4894_MOESM3_ESM.pdf)

## Source data

## Rights and permissions

## About this article

[![[image.svg+xml]]](https://crossmark.crossref.org/dialog/?doi=10.1038/s41586-022-04894-9)

### Cite this article

Cruz, B.F., Guiomar, G., Soares, S. *et al.* Action suppression reveals opponent parallel control via striatal circuits. *Nature* (2022). https://doi.org/10.1038/s41586-022-04894-9

[Download citation](https://citation-needed.springer.com/v2/references/10.1038/s41586-022-04894-9?format=refman&flavour=citation)

-   Received: 28 November 2019
    
-   Accepted: 23 May 2022
    
-   Published: 06 July 2022
    
-   DOI: https://doi.org/10.1038/s41586-022-04894-9
    

### Subjects

## Comments

By submitting a comment you agree to abide by our [Terms](https://www.nature.com/info/tandc.html) and [Community Guidelines](https://www.nature.com/info/community-guidelines.html). If you find something abusive or that does not comply with our terms or guidelines please flag it as inappropriate.
