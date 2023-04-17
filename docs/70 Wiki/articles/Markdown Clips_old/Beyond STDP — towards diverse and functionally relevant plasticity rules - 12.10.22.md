---
type: web article
creationtag: 2022-10-12 13:48
title: "Beyond STDP — towards diverse and functionally relevant plasticity rules"
URL: "https://www.sciencedirect.com/science/article/pii/S0959438818301065"
people: []
infotags: []
project:
citekey: suvrathanSTDPDiverseFunctionally2019a
---

> [!Excerpt] Beyond STDP — towards diverse and functionally relevant plasticity rules - ScienceDirect
> Synaptic plasticity, induced by the close temporal association of two neural signals, supports associative forms of learning. However, the millisecond…

---

## Highlights

•

Associative [synaptic plasticity](https://www.sciencedirect.com/topics/neuroscience/synaptic-plasticity "Learn more about synaptic plasticity from ScienceDirect's AI-generated Topic Pages") can occur in response to neural signals that are far apart in time.

•

The timescales of plasticity bridge delays that are relevant to the local circuit.

•

Timing rules for synaptic plasticity can solve the temporal credit assignment problem.

•

The rules for induction of plasticity are tuned to circuit function

Synaptic plasticity, induced by the close temporal association of two neural signals, supports associative forms of learning. However, the millisecond timescales for association often do not match the much longer delays for behaviorally relevant signals that supervise learning. In particular, information about the behavioral outcome of neural activity can be delayed, leading to a problem of temporal credit assignment. Recent studies suggest that synaptic plasticity can have temporal rules that not only accommodate the delays relevant to the circuit, but also be precisely tuned to the behavior the circuit supports. These discoveries highlight the diversity of plasticity rules, whose temporal requirements may depend on circuit delays and the contingencies of behavior.


## Introduction

Synapses are capable of long-lasting plastic changes in strength, in response to specific patterns of neural input. The rules that determine that some input patterns, and not others, result in [synaptic plasticity](https://www.sciencedirect.com/topics/neuroscience/synaptic-plasticity "Learn more about synaptic plasticity from ScienceDirect's AI-generated Topic Pages") have been the subject of extensive research, as well as much debate. It is important to understand these rules because synaptic plasticity supports behavioral learning, and is a critical part of how the brain encodes a modified behavior. Recent discoveries suggest that rather than having universal rules for plasticity, there may be a diversity of rules, and that this diversity may be determined by the function of the neural circuit that each synapse is a part of.

The search for plasticity rules has long been based on Hebb’s postulate that when a neuron repeatedly drives the activity of another, the connection between them is strengthened \[[1](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0005)\]. Hebbian plasticity addressed the question of *causality* in plasticity, but the discovery of spike timing-dependent plasticity (STDP) provided a framework for *order dependence* as well as causality. To elaborate, the STDP rule stated that if presynaptic activity preceded postsynaptic activity within a few tens of milliseconds, it resulted in the strengthening of the connecting synapse, while the converse temporal order resulted in the weakening of the synapse \[[2](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0010),[3](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0015)\] ([Figure 1](https://www.sciencedirect.com/science/article/pii/S0959438818301065#fig0005)a). 

STDP-like learning rules, in which the precise timing between presynaptic and postsynaptic neural activity is the critical determinant of the direction and degree of synaptic plasticity, are beautiful in their simplicity and have been supported by many studies, both in *ex vivo* preparations and *in vivo*, in different brain regions and in different species \[[4](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0020), [5](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0025), [6](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0030), [7](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0035), [8](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0040), [9](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0045), [10](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0050), [11](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0055)\]. 

However, the necessity for postsynaptic action potentials remains controversial \[[12](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0060), [13](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0065), [14](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0070), [15](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0075)\] and plasticity may be mediated by other depolarizing events in the postsynaptic cell \[[16](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0080)\]. In this review, therefore, plasticity rules requiring order-dependent, close temporal correlation of neural signals are referred to as STDP-like. These rules have been extensively reviewed elsewhere \[[17](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0085),[18](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0090)\], and form a fundamental core of our understanding of associative plasticity at synapses \[[7](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0035),[19](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0095), [20](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0100), [21](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0105), [22](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0110), [23](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0115), [24](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0120), [25](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0125), [26](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0130)\].

---
![[1-s2.0-S0959438818301065-gr1.jpg]]

1.  [Download : Download high-res image (206KB)](https://ars.els-cdn.com/content/image/1-s2.0-S0959438818301065-gr1_lrg.jpg "Download high-res image (206KB)")
2.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S0959438818301065-gr1.jpg "Download full-size image")

Figure 1. The short timescales of spike timing-dependent plasticity (STDP) are difficult to reconcile with the long timescales of associative learning where information about outcome is delayed. 

**(a)** Spike timing-dependent plasticity is induced when neuron A activates neuron B repeatedly. When A fires up to a few tens of milliseconds before B, the synapse between A and B is strengthened. If B fires up to a few tens of milliseconds before A, the synapse is weakened.

**(b)** Neural activity (left) leads to an outcome (middle), for example, a reward, a punishment, or a motor error. Information about the outcome is conveyed back to the neurons whose activity caused the outcome, but it comes at a long delay relative to the original, precisely timed, neural activity.

---
## Beyond STDP rules

### Relevance of plasticity to learning signals

One key difficulty with invoking STDP-like plasticity rules to support all forms of associative learning is the difference in timescale between plasticity rules, at the scale of tens of milliseconds, and the contingencies of behavioral learning, often on the timescale of minutes. Although STDP-like rules can vary between brain regions \[[19](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0095)\], this variability is not sufficient to directly bridge longer behavioral timescales. It has, however, been possible to reconcile these differences in timescale; for example, in hippocampal place cells, the timescale of hundreds of milliseconds can be compressed into the millisecond timescales relevant for STDP-type rules, in the presence of inhibition-driven theta oscillations and asymmetric excitation \[[27](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0135)\].

### The temporal credit assignment problem

During some forms of associative learning, an animal associates a neural event with information about its behavioral effect. The valence of such a signal can vary — reward, punishment and error signals all drive associative learning. For the neural circuits where such associations are made, the delayed signal about the outcome results in a problem of temporal credit assignment. How does the signal about the outcome of an action, occurring long after the relevant synaptic activity that drove the action, identify the appropriate synapses to modify ([Figure 1](https://www.sciencedirect.com/science/article/pii/S0959438818301065#fig0005)b)? It is possible to invoke STDP-like synaptic learning rules by bridging gaps in time, for example, with a synaptic eligibility trace which tags synapses for plasticity in response to a delayed reward signal, a cascade of plasticity events, or sustained responses to a stimulus \[[28](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0140), [29](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0145), [30](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0150), [31](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0155),[32<sup>•</sup>](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0160)\]. However, recent studies demonstrate that the association of neural signals temporally spaced much farther apart than STDP-like processes, are nevertheless capable of inducing [synaptic plasticity](https://www.sciencedirect.com/topics/neuroscience/synaptic-plasticity "Learn more about synaptic plasticity from ScienceDirect's AI-generated Topic Pages"). These studies describe plasticity rules that extend beyond millisecond timescales, to longer timescales that are behaviorally and physiologically relevant \[[33<sup>••</sup>](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0165),[34<sup>••</sup>](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0170)\].

## Synaptic plasticity on functionally relevant timescales

The alignment of timing rules to the function of the local circuit was recently demonstrated in the [hippocampus](https://www.sciencedirect.com/topics/neuroscience/hippocampus "Learn more about hippocampus from ScienceDirect's AI-generated Topic Pages") \[[35](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0175)\]. Pairing of entorhinal [perforant path](https://www.sciencedirect.com/topics/neuroscience/perforant-path "Learn more about perforant path from ScienceDirect's AI-generated Topic Pages") and hippocampal [Schaffer collateral](https://www.sciencedirect.com/topics/neuroscience/schaffer-collateral "Learn more about Schaffer collateral from ScienceDirect's AI-generated Topic Pages") inputs to hippocampal CA1 pyramidal neurons resulted in an enhancement of Schaffer collateral-driven [postsynaptic potentials](https://www.sciencedirect.com/topics/neuroscience/postsynaptic-potential "Learn more about postsynaptic potentials from ScienceDirect's AI-generated Topic Pages"), which arises in part from the long-term depression of feedforward inhibition onto CA1 neurons. This reduction in feedforward inhibition was localized to reduced GABA release from cholecystokinin-expressing [interneurons](https://www.sciencedirect.com/topics/neuroscience/interneuron "Learn more about interneurons from ScienceDirect's AI-generated Topic Pages") via [endocannabinoid](https://www.sciencedirect.com/topics/neuroscience/endocannabinoids "Learn more about endocannabinoid from ScienceDirect's AI-generated Topic Pages") signaling \[[35](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0175),[36](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0180)\]. During such input-timing-dependent plasticity (ITDP), pairing of the perforant path input 20 ms prior to the Schaffer collateral inputs induced heterosynaptic plasticity. Interestingly, the 20 ms delay matches both the delay caused by the neural circuit architecture as well as the period of the gamma oscillation. ITDP has also been demonstrated at CA2 pyramidal neurons, albeit with less precise tuning to the 20 ms delay. In the CA2, ITDP is mediated by depression of feedforward inhibition from parvalbumin-expressing interneurons via activation of *δ*\-opioid receptors \[[37<sup>•</sup>](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0185)\] ([Figure 2](https://www.sciencedirect.com/science/article/pii/S0959438818301065#fig0010)a).

---
![[1-s2.0-S0959438818301065-gr2.jpg]]

1.  [Download : Download high-res image (924KB)](https://ars.els-cdn.com/content/image/1-s2.0-S0959438818301065-gr2_lrg.jpg "Download high-res image (924KB)")
2.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S0959438818301065-gr2.jpg "Download full-size image")

Figure 2. Examples of synaptic plasticity tuned to the temporal requirements of the circuit and behavior. Left column: illustration of behavioral or circuit-level delays, from the studies listed on the bottom left of each row. Right column: Schematized plasticity rule based on each study, highlighting the alignment of the timing of the plasticity rule to the temporal constraint in the left column. **(a)** Input-timing-dependent heterosynaptic plasticity at CA1 neurons is tuned to the 20 ms circuit delay between direct [perforant path](https://www.sciencedirect.com/topics/neuroscience/perforant-path "Learn more about perforant path from ScienceDirect's AI-generated Topic Pages") inputs from the [entorhinal cortex](https://www.sciencedirect.com/topics/neuroscience/entorhinal-cortex "Learn more about entorhinal cortex from ScienceDirect's AI-generated Topic Pages") and delayed [Schaffer collateral](https://www.sciencedirect.com/topics/neuroscience/schaffer-collateral "Learn more about Schaffer collateral from ScienceDirect's AI-generated Topic Pages") inputs \[[35](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0175)\]. A similar timing rule exists at CA2 pyramidal neurons \[[37<sup>•</sup>](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0185)\]. (SC [PSP](https://www.sciencedirect.com/topics/neuroscience/postsynaptic-potential "Learn more about PSP from ScienceDirect's AI-generated Topic Pages"): Schaffer collateral postsynaptic potential. PP before SC is negative.) **(b)** Synaptic plasticity at cortical synapses onto lateral [amygdala](https://www.sciencedirect.com/topics/neuroscience/amygdala "Learn more about amygdala from ScienceDirect's AI-generated Topic Pages") inputs is selectively induced when thalamic and cortical inputs are separated by 15 ms, which matches the delay between inputs *in vivo* \[[38](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0190)\]. **(c)** Hippocampal CA1 place cells follow a rule for rapid induction of plasticity at synaptic inputs activated within seconds of a plateau potential, which matches the timescale of place field formation \[[34<sup>••</sup>](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0170)\]. **(d)** The STDP-like plasticity rule underlying olfactory conditioning in locusts is modified by the delayed occurrence of a reward signal \[[50<sup>••</sup>](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0250)\]. **(e)** Synaptic plasticity in the flocculus of the [cerebellum](https://www.sciencedirect.com/topics/neuroscience/cerebellum "Learn more about cerebellum from ScienceDirect's AI-generated Topic Pages") is tuned to the 120 ms delay in climbing fiber error signal during oculomotor learning \[33<sup>••</sup>\].

---

Another recent study that highlights the relevance of precise timing rules to circuit delays considers input-timing-dependent plasticity in the [amygdala](https://www.sciencedirect.com/topics/neuroscience/amygdala "Learn more about amygdala from ScienceDirect's AI-generated Topic Pages"), where coincidence of thalamic and cortical inputs to the lateral amygdala causes selective LTP of the cortico-amygdala pathway, but only when the thalamic–amygdala synapses are stimulated 15 ms before the cortico-amygdala synapses \[[38](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0190)\]. Behaviorally, the amygdala supports fear conditioning, during which information about the auditory conditioned stimulus arrives via the thalamic inputs before the cortical ones, at approximately the same 15 ms delay ([Figure 2](https://www.sciencedirect.com/science/article/pii/S0959438818301065#fig0010)b).

The circuit-specific timing rules discussed thus far show modifications to the STDP rule, adapted to relevant local circuit delays. However, these rules still act on the timescale of tens of milliseconds. Recently, a learning rule that itself spans a seconds-long timescale has been discovered in the hippocampus \[[34<sup>••</sup>](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0170),[39](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0195)\] ([Figure 2](https://www.sciencedirect.com/science/article/pii/S0959438818301065#fig0010)c). During the formation of place fields, ramp-like depolarization of CA1 neurons caused by plateau potentials led to place field firing on subsequent trials. The plasticity rule at synapses onto CA1 neurons was tested in the slice preparation, where trains of synaptic activation were paired with a postsynaptic plateau potential. The temporal interval between the two signals that was effective in driving plasticity extended asymmetrically out to seconds in both directions ([Figure 2](https://www.sciencedirect.com/science/article/pii/S0959438818301065#fig0010)c). This learning rule contradicts Hebb’s original postulate, as potentiated inputs were not causal for postsynaptic spiking. A key difference from STDP-like rules is that repeated pairing was not necessary for the induction of plasticity; just five pairings were sufficient. Critically, this novel form of plasticity can account for the rapid formation of place fields over the seconds it takes for an animal to cross a novel arena. In addition, very few trials (∼1.4) with a plateau potential were sufficient to induce a place field *in vivo*, which is also in contrast to Hebb’s postulate of repeated pairings being necessary for modification of synaptic strength. The timing requirements of such behavioral time scale plasticity (BTSP) fit well with the function of the hippocampal circuit, demonstrating that the synaptic plasticity rule itself can account for long timescales relevant for behavioral learning. It is possible, however, that more than one plasticity mechanism is recruited during the formation of place fields \[[40](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0200),[41](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0205)\].

More than twenty years ago, a similarly long timescale (hundreds of milliseconds to over a second) for induction of associative synaptic plasticity was demonstrated in the hippocampus, albeit depression rather than potentiation \[[42](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0210)\]. In this study, the usual STDP-like pre-post order of synaptic events was inverted: depolarization of the postsynaptic CA1 cell, followed by synaptic activation hundreds of milliseconds later, resulted in synaptic depression. This investigation forms part of an early set of studies describing timing rules for plasticity, often with longer timescales for association \[[43](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0215), [44](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0220), [45](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0225)\].

## Dealing with delays: neuromodulators and plasticity rules

Associative learning is often guided by signals that indicate the outcome of an action, such as reward signals. In such cases, learning may be supervised by a neuromodulatory signal rather than by synaptic activity. The timing rules for such supervised learning follow timescales whose behavioral significance is easier to understand. For example, dopamine signals evoked by stimulation of the [ventral tegmental area](https://www.sciencedirect.com/topics/neuroscience/ventral-tegmental-area "Learn more about ventral tegmental area from ScienceDirect's AI-generated Topic Pages") (VTA) can modulate the cortical representation of a tone paired with it, with the tone preceding VTA stimulation by hundreds of milliseconds \[[46](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0230)\]. The number and duration of pairings with a behaviorally relevant stimulus can be significantly different from those in STDP-like rules, or BTSP, extending to hundreds of pairings, over 20–25 days \[[47](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0235)\]. Indeed, such long timescales, both for the interstimulus interval of one pairing, and for the number of pairings itself, are likely to be relevant to the contingencies of behavioral learning. Moreover, it brings into question the relevance of precise spike timing for neural circuits where learning is supervised by delayed and temporally more diffuse neuromodulatory signals.

However, not only can neuromodulators signal relevance or reward to directly drive plasticity, they can also change the temporal requirements of precise spike timing necessary for inducing synaptic plasticity. Neuromodulatory signals encoding reward, delayed in time relative to the neural activity that caused it, have been demonstrated to interact with plasticity rules to modify the appropriate synapses \[[48<sup>••</sup>](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0240),[49](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0245)\]. In locusts, where the reward signal is the neuromodulator [octopamine](https://www.sciencedirect.com/topics/neuroscience/octopamine "Learn more about octopamine from ScienceDirect's AI-generated Topic Pages"), a local STDP rule is modified by the delayed (by one second) application of octopamine \[[50<sup>••</sup>](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0250)\]. Kenyon cell to beta-lobe neurons follow a Hebbian STDP rule that, along with [lateral inhibition](https://www.sciencedirect.com/topics/neuroscience/lateral-inhibition "Learn more about lateral inhibition from ScienceDirect's AI-generated Topic Pages"), is thought to regulate the spiking response of beta-lobe neurons. This timing rule identifies the presynaptic and postsynaptic components of the synapse to be modified — if a delayed global reward signal occurs, it interacts with the eligibility trace created by precisely timed prior synaptic activity in order to modify the appropriate synapses. Remarkably, the delayed reward modifies the plasticity rule (the curve relating synaptic plasticity to inter-event time) ([Figure 2](https://www.sciencedirect.com/science/article/pii/S0959438818301065#fig0010)d). The ability of modulatory inputs to affect plasticity has been demonstrated in several different contexts. It can play a gating role \[[51](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0255), [52](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0260), [53](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0265), [54](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0270)\] or can change the shape of the plasticity rule itself \[[32<sup>•</sup>](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0160),[55](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0275), [56](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0280), [57](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0285), [58](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0290)\].

The timing requirements for the action of a neuromodulatory signal have also been investigated in the context of dopamine’s modulation of plasticity of spine structure in [medium spiny neurons](https://www.sciencedirect.com/topics/neuroscience/medium-spiny-neuron "Learn more about medium spiny neurons from ScienceDirect's AI-generated Topic Pages") in the striatum, showing that dopamine needs to be timed 0.3–2 s after glutamatergic stimulation \[[59](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0295)\]. During such supervised learning, an eligibility trace is created, which can then be converted by neuromodulators into long-term plasticity \[[60](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0300),[61](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0305)\]. However, further investigation is needed into the timing requirements for delayed reward signals in different brain regions, and in the underlying mechanisms that can support synaptic eligibility traces and their interaction with modulatory signals. The timing of the reward signal itself can be learned \[[62](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0310),[63](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0315)\], leading to the possibility of plasticity in the timing of the learning rule.

## Synaptic plasticity tuned to behaviorally relevant delays

In the [cerebellum](https://www.sciencedirect.com/topics/neuroscience/cerebellum "Learn more about cerebellum from ScienceDirect's AI-generated Topic Pages"), a plasticity rule which is broadly tuned to associations was thought to account for long circuit delays in a manner similar to rules in the [hippocampus](https://www.sciencedirect.com/topics/neuroscience/hippocampus "Learn more about hippocampus from ScienceDirect's AI-generated Topic Pages") \[[33<sup>••</sup>](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0165)\], although on the much shorter timescales relevant to the behavior the cerebellum supports (hundreds of milliseconds instead of seconds) \[[64](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0320)\]. By contrast, we recently showed that a plasticity rule in the cerebellum can not only account for long delays, but that it can be precisely tuned to a specific, long delay appropriate to behavioral function \[[33<sup>••</sup>](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0165)\].

Cerebellar learning is guided by errors in motor performance. Within the cerebellar cortex, the teaching signal for plasticity is therefore an error signal carried by climbing fibers, synapsing onto [Purkinje cells](https://www.sciencedirect.com/topics/neuroscience/purkinje-cell "Learn more about Purkinje cells from ScienceDirect's AI-generated Topic Pages"). The original Marr-Albus theory postulated that climbing fiber error signals drive plasticity of correlated parallel fiber-to-Purkinje cell synapses \[[65](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0325),[66](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0330)\]. This form of error-signal driven heterosynaptic plasticity is anti-Hebbian in nature, in that it causes long-term depression (LTD) at the parallel fiber synapses which contributed to the error, similar to plasticity in other cerebellum-like structures \[[67](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0335)\].

We demonstrated that the plasticity rules that guide climbing fiber-driven LTD at parallel fiber-to-Purkinje cell synapses within a small, functionally homogenous region of the cerebellum, the flocculus, are different from the rules in the well-studied [cerebellar vermis](https://www.sciencedirect.com/topics/neuroscience/cerebellar-vermis "Learn more about cerebellar vermis from ScienceDirect's AI-generated Topic Pages") \[[33<sup>••</sup>](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0165)\]. In particular, plasticity was tuned to a long delay in climbing fiber error signal, which exactly matched the delay for error signals during learning *in vivo*. Specifically, LTD was induced at parallel fiber-to-Purkinje cell synapses in the flocculus if climbing fiber stimulation was repeatedly paired with parallel fiber stimulation, with the climbing fibers delayed 120 ms relative to the parallel fibers. LTD was not induced if the delay was varied by a few tens of milliseconds in either direction, suggesting the timing rule for plasticity has the precision of STDP in the cortex or the hippocampus ([Figure 2](https://www.sciencedirect.com/science/article/pii/S0959438818301065#fig0010)e).

The flocculus of the cerebellum supports forms of oculomotor learning, where the relevant error signal during learning is a slip of images on the retina. Retinal slip error signals reach the flocculus with an ∼120 ms delay, and therefore the timing rule for plasticity is tuned to the signals present during learning. The tuning of Purkinje cells within the flocculus to a specific and behaviorally relevant timing rule suggests that plasticity rules themselves can vary to account for the properties of the circuit and behavior. This is in contrast to previous theories where synaptic plasticity follows uniform, coincidence-based rules, and circuit properties account for the temporal contingencies of the relevant behavioral output.

## One timing to rule them all, and in the synapses bind them?

In addition to LTD, single-trial climbing fiber-driven plasticity in the flocculus, which may provide a substrate for trial-by-trial motor learning, was also tuned to the same 120 ms error signal delay \[[33<sup>••</sup>](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0165)\]. By contrast, the tuning of single-trial plasticity in the [cerebellar vermis](https://www.sciencedirect.com/topics/neuroscience/cerebellar-vermis "Learn more about cerebellar vermis from ScienceDirect's AI-generated Topic Pages") varied. Different cells appeared to be tuned to different climbing fiber delays, which would match the diversity of error signal modalities related to the different motor tasks supported by the vermis.

Heterogeneous plasticity rules were recently also demonstrated in Drosophila [mushroom body](https://www.sciencedirect.com/topics/neuroscience/mushroom-bodies "Learn more about mushroom body from ScienceDirect's AI-generated Topic Pages") output neurons that lie in functionally different compartments \[[68<sup>•</sup>](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0340),[69](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0345)\]. [Dopaminergic](https://www.sciencedirect.com/topics/neuroscience/dopaminergic "Learn more about Dopaminergic from ScienceDirect's AI-generated Topic Pages") neurons signaling the valence of an odor innervate anatomically distinct compartments of the mushroom body lobes. Pairing an odor with activation of dopaminergic neurons in the γ1-pedc compartment leads to depression of mushroom body output neuron (MBON) firing in response to that odor. Inverted pairing, with the dopamine activation prior to the odor delivery did not result in plasticity, replicating the temporal order of sequence-dependent associative learning. Odor-dopamine pairing depresses the input to MBONs, that is, Kenyon cell-MBON synapses. Different MBON compartments are known to be behaviorally segregated, with activation of different compartments evoking contrasting behavioral responses, such as attraction or avoidance. Strikingly, the plasticity induced by pairing an odor with dopaminergic neuron activation had timing rules for induction which varied between compartments, suggesting behaviorally relevant plasticity rules. Here, postsynaptic spiking was not necessary for plasticity and hence the timing rules for plasticity relate to the timing of the dopaminergic input.

In addition to heterogeneity at synapses of the same type, plasticity rules also vary at and between different cell types, as has been discussed in more detail elsewhere \[[70](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0350)\]. Furthermore, emerging evidence suggests that there is an unexpected molecular heterogeneity even within what has previously been considered a single cell-type. For example, in the hippocampus, there are dorso-ventral gradients of gene expression in CA1 [pyramidal cells](https://www.sciencedirect.com/topics/neuroscience/pyramidal-cell "Learn more about pyramidal cells from ScienceDirect's AI-generated Topic Pages"). In addition, the variability in gene expression among CA1 pyramidal cells may correlate with the [neural networks](https://www.sciencedirect.com/topics/neuroscience/neural-networks "Learn more about neural networks from ScienceDirect's AI-generated Topic Pages") they connect to \[[71<sup>•</sup>](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0355)\]. Indeed, diverse learning rules at what has so far been considered a single type of synaptic connection \[[33<sup>••</sup>](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0165),[68<sup>•</sup>](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0340)\] may arise because synaptic inputs arise from diverse cell populations and carry different information \[[72](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0360)\]. Thus, functionally and molecularly dissimilar cells may have been included as part of a single gross classification only because of the lack of tools to identify more fine-scaled heterogeneity.

## Conclusions

With the discovery of STDP, neuroscientists had the long-hoped-for, single learning rule, which could be applied to any spike train to predict plasticity. Indeed, STDP-like learning rules have formed a core element of models of learning. However, recent studies suggest that the timing rules for synaptic plasticity can be aligned with the behavioral and functional requirements of a circuit, contradicting the concept of plasticity rules based only on close temporal correlations.

In neural circuits where plasticity is supervised by a reward or an error signal, or where the delays in neural activity are known, it has been possible to understand the relevance of precisely timed plasticity rules. More generally, arriving at the appropriate plasticity rule for a given synapse, in a given brain region, remains a challenging problem.

Timing is only part of the picture, since there are several other parameters that form a critical part of any plasticity rule, such as the rate of neuronal firing, number of repetitions, and the cooperativity of synapses, as well as integration of more than one pair of presynaptic and postsynaptic signals \[[11](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0055),[13](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0065),[73](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0365), [74](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0370), [75](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0375)\]. Indeed, with our focus on the timescales of pairing, the timescales over which the pairings are repeated is often ignored. With the noteworthy exception of the recently discovered BTSP, associative synaptic plasticity is usually induced by repeated pairings. The number of pairings influences the degree of plasticity induced \[[76](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0380)\], and continues on the order of minutes — a timescale which may be the most relevant one to behavioral learning. Moreover, synaptic plasticity is far from being the only form of plasticity in a neural circuit \[[70](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0350),[77](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0385)\], and we do not even scratch the surface of how plasticity rules are shaped by the history of neural activity. In addition, synaptic plasticity that supports behavioral plasticity is likely to be distributed over more than one site in a neural circuit \[[78](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0390)\]. It is possible that the unifying link between plasticity rules at different synapses of a single neuron will be found by considering the intracellular mechanisms that support plasticity \[[79](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bib0395)\], or that learning rules can be best understood with more high-dimensional representations of plasticity that integrate all the forms of synaptic, intrinsic and homeostatic plasticity within a neural circuit with the dynamics of neural activity during learning.

In summary, coincidence-based rules for synaptic plasticity are no longer sufficient to explain the diversity of ways neural circuits can adapt and learn. The rules for plasticity can cover much longer timescales than previously thought and vary depending on the circuit they are embedded in, forcing both a reevaluation of the synaptic basis of learning rules as well as investigation into underlying mechanisms that can bridge long timescales.

## Funding sources

Aparna Suvrathan was supported by the Research Institute of the McGill University Health Centre and McGill University. This research was undertaken thanks in part to funding from the Canada First Research Excellence Fund, awarded to McGill University for the Healthy Brains for Healthy Lives initiative.

## Conflict of interest statement

Nothing declared.

## References and recommended reading

Papers of particular interest, published within the period of review, have been highlighted as

• of special interest

•• of outstanding interest

## Acknowledgements

I thank Jennifer L Raymond, Jesper Sjöström and Arnold Hayer for their insightful comments and suggestions and apologize to all researchers whose contributions have not been discussed here because of space limitations.

## References

[1](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0005)

D.O. Hebb

**The Organization of Behavior — A Neuropsychological Theory**

John Wiley and Sons (1949)

[2](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0010)

G.Q. Bi, M.M. Poo

**Synaptic modifications in cultured hippocampal neurons: dependence on spike timing, synaptic strength, and postsynaptic cell type**

J Neurosci, 18 (1998), pp. 10464-10472

[3](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0015)

H. Markram, J. Lubke, M. Frotscher, B. Sakmann

**Regulation of synaptic efficacy by coincidence of postsynaptic APs and EPSPs**

Science, 275 (1997), pp. 213-215

[4](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0020)

V. Jacob, D.J. Brasier, I. Erchova, D. Feldman, D.E. Shulz

**Spike timing-dependent synaptic depression in the in vivo barrel cortex of the rat**

J Neurosci, 27 (2007), pp. 1271-1284

[5](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0025)

Y. Nishimura, S.I. Perlmutter, R.W. Eaton, E.E. Fetz

**Spike-timing-dependent plasticity in primate corticospinal connections induced during free behavior**

Neuron, 80 (2013), pp. 1301-1309

[6](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0030)

J.C. Dahmen, D.E.H. Hartley, A.J. King

**Stimulus-timing-dependent plasticity of cortical frequency representation**

J Neurosci, 28 (2008), pp. 13629-13639

[7](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0035)

S. Song, L.F. Abbott

**Cortical development and remapping through spike timing-dependent plasticity**

Neuron, 32 (2001), pp. 339-350

[8](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0040)

E.P. Casula, M.C. Pellicciari, S. Picazio, C. Caltagirone, G. Koch

**Spike-timing-dependent plasticity in the human dorso-lateral prefrontal cortex**

Neuroimage, 143 (2016), pp. 204-213

[9](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0045)

S.L. Jones, M.S. To, G.J. Stuart

**Dendritic small conductance calcium-activated potassium channels activated by action potentials suppress EPSPs and gate spike-timing dependent synaptic plasticity**

Elife, 6 (2017), pp. 1-18

[10](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0050)

M.A. Urbin, R.A. Ozdemir, T. Tazoe, M.A. Perez

**Spike-timing-dependent plasticity in lower-limb motoneurons after human spinal cord injury**

J Neurophysiol, 118 (2017), pp. 2171-2180

[11](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0055)

M. Sgritta, F. Locatelli, T. Soda, F. Prestori, E.U. D’Angelo

**Hebbian spike-timing dependent plasticity at the cerebellar input stage**

J Neurosci, 37 (2017), pp. 2809-2823

[12](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0060)

J. Lisman, N. Spruston

**Questions about STDP as a general model of synaptic plasticity**

Front Synaptic Neurosci, 2 (2010), pp. 1-5

[13](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0065)

J. Lisman, N. Spruston

**Postsynaptic depolarization requirements for LTP and LTD: a critique of spike timing-dependent plasticity**

Nat Neurosci, 8 (2005), pp. 839-841

[14](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0070)

F. Gambino, S. Pagès, V. Kehayas, D. Baptista, R. Tatti, A. Carleton, A. Holtmaat

**Sensory-evoked LTP driven by dendritic plateau potentials in vivo**

Nature, 515 (2014), pp. 116-119

[15](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0075)

M.E.J. Sheffield, D.A. Dombeck

**Calcium transient prevalence across the dendritic arbour predicts place field properties**

Nature, 517 (2015), pp. 200-204

[16](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0080)

C. Clopath, W. Gerstner

**Voltage and spike timing interact in STDP — a unified model**

Front Synaptic Neurosci, 2 (2010), pp. 1-11

[17](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0085)

H. Markram, W. Gerstner, P.J. Sjöström

**Spike-timing-dependent plasticity: a comprehensive overview**

Front Synaptic Neurosci, 4 (2012), pp. 2010-2012

[18](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0090)

H. Markram, W. Gerstner, P.J. Sjöström

**A history of spike-timing-dependent plasticity**

Front Synaptic Neurosci, 3 (2011), pp. 1-24

[19](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0095)

D.E. Feldman

**The spike-timing dependence of plasticity**

Neuron, 75 (2012), pp. 556-571

[20](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0100)

P. D’Souza, S.-C. Liu, R.H.R. Hahnloser

**Perceptron learning rule derived from spike-frequency adaptation and spike-time-dependent plasticity**

Proc Natl Acad Sci U S A, 107 (2010), pp. 4722-4727

[21](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0105)

A.J. Sederberg, J.N. MacLean, S.E. Palmer

**Learning to make external sensory stimulus predictions using internal correlations in populations of neurons**

Proc Natl Acad Sci, 115 (2018), pp. 1105-1110

[22](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0110)

N. Hiratani, T. Fukai

**Detailed dendritic excitatory/inhibitory balance through heterosynaptic spike-timing-dependent plasticity**

J Neurosci, 37 (2017), pp. 12106-12122

[23](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0115)

M. Deger, A. Seeholzer, W. Gerstner

**Multi-contact synapses for stable networks: a spike-timing dependent model of dendritic spine plasticity and turnover**

Cereb Cortex, 28 (2018), pp. 1396-1415

[24](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0120)

N. Iannella, T. Launey

**Modulating STDP balance impacts the dendritic mosaic**

Front Comput Neurosci, 11 (2017), pp. 1-17

[25](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0125)

Y. Liu, L. Cui, M.K. Schwarz, Y. Dong, O.M. Schlüter

**Adrenergic gate release for spike timing-dependent synaptic potentiation**

Neuron, 93 (2017), pp. 394-408

[26](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0130)

S. Song, K.D. Miller, L.F. Abbott

**Competitive Hebbian learning through spike-timing-dependent synaptic plasticity**

Nat Neurosci, 3 (2000), pp. 919-926

[27](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0135)

M.R. Mehta, A.K. Lee, M.A. Wilson

**Role of experience and oscillations in transforming a rate code into a temporal code**

Nature, 417 (2002), pp. 741-746

[28](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0140)

P.J. Drew, L.F. Abbott

**Extending the effects of spike-timing-dependent plasticity to behavioral timescales**

Proc Natl Acad Sci, 103 (2006), pp. 8876-8881

[29](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0145)

J. Friedrich, R. Urbanczik, W. Senn

**Spatio-temporal credit assignment in neuronal population learning**

PLoS Comput Biol, 7 (2011)

[30](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0150)

D.J. Surmeier, J. Plotkin, W. Shen

**Dopamine and synaptic plasticity in dorsal striatal circuits controlling action selection**

Curr Opin Neurobiol, 19 (2009), pp. 621-628

[31](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0155)

E.M. Izhikevich

**Solving the distal reward problem through linkage of STDP and dopamine signaling**

Cereb Cortex, 17 (2007), pp. 2443-2452

[32•](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0160)

Z. Brzosko, S. Zannone, W. Schultz, C. Clopath, O. Paulsen

**Sequential neuromodulation of hebbian plasticity offers mechanism for effective reward-based navigation**

Elife, 6 (2017), pp. 1-18

A model of spatial navigation that incorporates neuromodulatory modification of synaptic plasticity rules is able to replicate navigation towards reward locations.

[33••](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0165)

A. Suvrathan, H.L. Payne, J.L. Raymond

**Timing rules for synaptic plasticity matched to behavioral function**

Neuron, 92 (2016), pp. 959-967

In contrast to what was previously thought, the timing rule for induction of synaptic plasticity in the cerebellar flocculus, which supports oculomotor learning, was tuned to the 120 ms delay for climbing fibers to convey signals about error during oculomotor learning *in vivo*. Single-trial plasticity was also tuned to a 120 ms delay in the flocculus, but showed diverse tuning in the vermis, a cerebellar sub- region which supports a range of functions with diverse error signal delays.

[34••](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0170)

K.C. Bittner, A.D. Milstein, C. Grienberger, S. Romani, J.C. Magee

**Behavioral time scale synaptic plasticity underlies CA1 place fields**

Science, 357 (2017), pp. 1033-1036

During formation of place fields, synaptic inputs to hippocampal CA neurons were potentiated after association with a plateau potential. The timescale for association could be seconds long, demonstrating a form of non-Hebbian plasticity which is induced in a few trials.

[35](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0175)

J. Basu, K.V. Srinivas, S.K. Cheung, H. Taniguchi, Z.J. Huang, S.A. Siegelbaum

**A cortico-hippocampal learning rule shapes inhibitory microcircuit activity to enhance hippocampal information flow**

Neuron, 79 (2013), pp. 1208-1221

[36](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0180)

J.T. Dudman, D. Tsay, S.A. Siegelbaum

**A role for synaptic inputs at distal dendrites: instructive signals for hippocampal long-term plasticity**

Neuron, 56 (2007), pp. 866-879

[37•](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0185)

F. Leroy, D.H. Brann, T. Meira, S.A. Siegelbaum

**Input-timing-dependent plasticity in the hippocampal CA2 region and its potential role in social memory**

Neuron, 95 (2017), pp. 1089-1102

CA2 neurons in the hippocampus show a form of input-timing-dependent plasticity, where the timing rule for plasticity is matched to the ∼20 ms delay between direct entorhinal cortex inputs and indirect Schaffer collateral inputs.

[38](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0190)

J.H. Cho, I.T. Bayazitov, E.G. Meloni, K.M. Myers, W.A. Carlezon, S.S. Zakharenko, V.Y. Bolshakov

**Coactivation of thalamic and cortical pathways induces input timing-dependent plasticity in amygdala**

Nat Neurosci, 15 (2012), pp. 113-122

[39](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0195)

K.C. Bittner, C. Grienberger, S.P. Vaidya, A.D. Milstein, J.J. Macklin, J. Suh, S. Tonegawa, J.C. Magee

**Conjunctive input processing drives feature selectivity in hippocampal CA1 neurons**

Nat Neurosci, 18 (2015), pp. 1133-1142

[40](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0200)

M.E.J. Sheffield, M.D. Adoff, D.A. Dombeck

**Increased prevalence of calcium transients across the dendritic arbor during place field formation**

Neuron, 96 (2017), pp. 490-504

[41](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0205)

J. Schiller, S. Berlin, D. Derdikman

**The many worlds of plasticity rules**

Trends Neurosci, 41 (2018), pp. 124-127

[42](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0210)

D. Debanne, B.H. Gähwiler, S.M. Thompson

**Asynchronous pre- and postsynaptic activity induces associative long-term depression in area CA1 of the rat hippocampus in vitro**

Proc Natl Acad Sci U S A, 91 (1994), pp. 1148-1152

[43](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0215)

D. Debanne, D.E. Shulz, Y. Frégnac

**Temporal constraints in associative synaptic plasticity in hippocampus and neocortex**

Can J Physiol Pharmacol, 73 (1995), pp. 1295-1311

[44](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0220)

Y. Frégnac, J.P. Burke, D. Smith, M.J. Friedlander

**Temporal covariance of pre- and postsynaptic activity regulates functional connectivity in the visual cortex**

J Neurophysiol, 71 (1994), pp. 1403-1421

[45](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0225)

D. Debanne, B.H. Gähwiler, S.M. Thompson

**Long-term synaptic plasticity between pairs of individual CA3 pyramidal cells in rat hippocampal slice cultures**

J Physiol, 507 (Pt 1) (1998), pp. 237-247

[46](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0230)

S. Bao, V.T. Chan, M.M. Merzenich

**Cortical remodelling induced by activity of ventral tegmental dopamine neurons**

Nature, 412 (2001), pp. 79-83

[47](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0235)

M.P. Kilgard, M.M. Merzenich

**Cortical map reorganization enabled by nucleus basalis activity**

Science, 279 (1998), pp. 1714-1718

[48••](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0240)

N. Frémaux, W. Gerstner

**Neuromodulated spike-timing-dependent plasticity, and theory of three-factor learning rules**

Front Neural Circuits (2016), p. 9

Review of spike-timing dependent plasticity and the effect of neuromodulatory signals, described as “neo-Hebbian three factor learning rules”.

[49](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0245)

V. Pawlak, J.R. Wickens, A. Kirkwood, J.N.D. Kerr

**Timing is not everything: neuromodulation opens the STDP gate**

Front Synaptic Neurosci, 2 (2010)

[50••](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0250)

S. Cassenaer, G. Laurent

**Conditional modulation of spike-timing-dependent plasticity for olfactory learning**

Nature, 482 (2012), pp. 47-51

A STDP-like plasticity rule at mushroom body target synapses in locusts is modified by a neuromodulator signaling reward, which is delayed by one second.

[51](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0255)

V. Pawlak, J.N.D. Kerr

**Dopamine receptor activation is required for corticostriatal spike-timing-dependent plasticity**

J Neurosci, 28 (2008), pp. 2435-2446

[52](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0260)

S. Bissiére, Y. Humeau, A. Lüthi

**Dopamine gates LTP induction in lateral amygdala by suppressing feedforward inhibition**

Nat Neurosci, 6 (2003), pp. 587-592

[53](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0265)

J.J. Couey, R.M. Meredith, S. Spijker, R.B. Poorthuis, A.B. Smit, A.B. Brussaard, H.D. Mansvelder

**Distributed network actions by nicotine increase the threshold for spike-timing-dependent plasticity in prefrontal cortex**

Neuron, 54 (2007), pp. 73-87

[54](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0270)

J.M. Schulz, P. Redgrave, J.N.J. Reynolds

**Cortico-striatal spike-timing dependent plasticity after activation of subcortical pathways**

Front Synaptic Neurosci, 2 (2010), pp. 1-13

[55](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0275)

G.H. Seol, J. Ziburkus, S. Huang, L. Song, I.T. Kim, K. Takamiya, R.L. Huganir, H.K. Lee, A. Kirkwood

**Neuromodulators control the polarity of spike-timing-dependent synaptic plasticity**

Neuron, 55 (2007), pp. 919-929

[56](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0280)

J.-C. Zhang, P.-M. Lau, G.-Q. Bi

**Gain in sensitivity and loss in temporal contrast of STDP by dopaminergic modulation at hippocampal synapses**

Proc Natl Acad Sci, 106 (2009), pp. 13028-13033

[57](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0285)

Z. Brzosko, W. Schultz, O. Paulsen

**Retroactive modulation of spike timing dependent plasticity by dopamine**

Elife, 4 (2015), pp. 1-13

[58](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0290)

W. Shen, M. Flajolet, P. Greengard, D.J. Surmeier

**Dichotomous dopaminergic control of striatal synaptic plasticity**

Science, 321 (2008), pp. 848-851

[59](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0295)

Yagishita S. Kasai, A. Hayashi-Takagi, G.C.R. Ellis-Davies, H. Urakubo, S. Ishii

**A critical time window for dopamine actions on the structural plasticity of dendritic spines**

Science, 345 (2014), pp. 1616-1621

[60](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0300)

K. He, M. Huertas, S.Z. Hong, X.X. Tie, J.W. Hell, H. Shouval, A. Kirkwood

**Distinct eligibility traces for LTP and LTD in cortical synapses**

Neuron, 88 (2015), pp. 528-538

[61](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0305)

M.A. Huertas, S.E. Schwettmann, H.Z. Shouval

**The role of multiple neuromodulators in reinforcement learning that is based on competition between eligibility traces**

Front Synaptic Neurosci, 8 (2016)

[62](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0310)

A.A. Chubykin, E.B. Roach, M.F. Bear, M.G. Hussain Shuler

**A cholinergic mechanism for reward timing within primary visual cortex**

Neuron, 77 (2013), pp. 723-735

[63](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0315)

C.H. Liu, J.E. Coleman, H. Davoudi, K. Zhang, M.G. Hussain Shuler

**Selective activation of a putative reinforcement signal conditions cued interval timing in primary visual cortex**

Curr Biol, 25 (2015), pp. 1551-1561

[64](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0320)

P. Safo, W.G. Regehr

**Timing dependence of the induction of cerebellar LTD**

Neuropharmacology, 54 (2008), pp. 213-218

[65](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0325)

J.S. Albus

**A theory of cerebellar function**

Math Biosci, 10 (1971), pp. 25-61

[66](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0330)

D. Marr

**A theory of cerebellar cortex**

J Physiol, 202 (1969), pp. 437-470

[67](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0335)

C.C. Bell, V. Han, Y. Sugawara, K. Grant

**Synaptic plasticity in a cerebellum-like structure depends on temporal order**

Nature, 387 (1997), pp. 278-281

[68•](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0340)

T. Hige, Y. Aso, M.N. Modi, G.M. Rubin, G.C. Turner

**Heterosynaptic plasticity underlies aversive olfactory learning in Drosophila**

Neuron, 88 (2015), pp. 985-998

At Drosophila mushroom body output neurons, synaptic plasticity induced by associative, order-dependent pairing of odor and activation of dopaminergic neurons, follows different plasticity rules in functionally distinct compartments.

[69](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0345)

Y. Aso, D. Hattori, Y. Yu, R.M. Johnston, N.A. Iyer, T.T.B. Ngo, H. Dionne, L.F. Abbott, R. Axel, H. Tanimoto, *et al.*

**The neuronal architecture of the mushroom body provides a logic for associative learning**

Elife, 3 (2014), p. e04577

[70](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0350)

S.B. Nelson, G.G. Turrigiano

**Strength through diversity**

Neuron, 60 (2008), pp. 477-482

[71•](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0355)

M.S. Cembrowski, J.L. Bachman, L. Wang, K. Sugino, B.C. Shields, N. Spruston

**Spatial gene-expression gradients underlie prominent heterogeneity of CA1 pyramidal neurons**

Neuron, 89 (2016), pp. 351-368

A gradient of dorso-ventral transcriptional heterogeneity exists at CA1 pyramidal neurons.

[72](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0360)

P.J. Sjöström, M. Häusser

**A cooperative switch determines the sign of synaptic plasticity in distal dendrites of neocortical pyramidal neurons**

Neuron, 51 (2006), pp. 227-238

[73](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0365)

P.J. Sjöström, G.G. Turrigiano, S.B. Nelson

**Rate, timing, and cooperativity jointly determine cortical synaptic plasticity**

Neuron, 32 (2001), pp. 1149-1164

[74](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0370)

H.X. Wang, R.C. Gerkin, D.W. Nauen, G.Q. Bi

**Coactivation and timing-dependent integration of synaptic potentiation and depression**

Nat Neurosci, 8 (2005), pp. 187-193

[75](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0375)

R.C. Froemke, Y. Dan

**Spike-timing-dependent synaptic modification induced by natural spike trains**

Nature, 416 (2002), pp. 433-438

[76](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0380)

C. Chen, R.F. Thompson

**Temporal specificity of long-term depression in parallel fiber-Purkinje synapses in rat cerebellar slice**

Learn Mem, 2 (1995), pp. 185-198

[77](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0385)

R.P. Costa, B.E.P. Mizusaki, P.J. Sjöström, M.C.W. van Rossum

**Functional consequences of pre- and postsynaptic expression of synaptic plasticity**

Philos Trans R Soc B Biol Sci, 372 (2017)

[78](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0390)

P. Cognigni, J. Felsenberg, S. Waddell

**Do the right thing: neural network mechanisms of memory formation, expression and update in Drosophila**

Curr Opin Neurobiol, 49 (2018), pp. 51-58

[79](https://www.sciencedirect.com/science/article/pii/S0959438818301065#bbib0395)

H. Shouval

**Spike timing dependent plasticity: a consequence of more fundamental learning rules**

Front Comput Neurosci, 4 (2010), pp. 1-13

## Cited by (20)

[View Abstract](https://www.sciencedirect.com/science/article/abs/pii/S0959438818301065)

© 2018 Published by Elsevier Ltd.
