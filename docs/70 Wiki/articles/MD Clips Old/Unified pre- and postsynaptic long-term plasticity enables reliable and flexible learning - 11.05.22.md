---
created: 2022-05-11T12:29:09 (UTC +02:00)
tags: []
source: https://elifesciences.org/articles/9457
author: Rui Ponte Costa, Robert C Froemke, P Jesper Sjöström, Mark CW van Rossum
---

# Unified pre- and postsynaptic long-term plasticity enables reliable and flexible learning | eLife



> ## Excerpt
> Combined pre- and postsynaptically expressed long-term plasticity of neuronal connections improves sensory discrimination, and enables rapid relearning of previously encountered information.

---
## Abstract

Although it is well known that long-term synaptic plasticity can be expressed both pre- and postsynaptically, the functional consequences of this arrangement have remained elusive. We show that spike-timing-dependent plasticity with both pre- and postsynaptic expression develops receptive fields with reduced variability and improved discriminability compared to postsynaptic plasticity alone. These long-term modifications in receptive field statistics match recent sensory perception experiments. Moreover, learning with this form of plasticity leaves a hidden postsynaptic memory trace that enables fast relearning of previously stored information, providing a cellular substrate for memory savings. Our results reveal essential roles for presynaptic plasticity that are missed when only postsynaptic expression of long-term plasticity is considered, and suggest an experience-dependent distribution of pre- and postsynaptic strength changes.

[https://doi.org/10.7554/eLife.09457.001](https://doi.org/10.7554/eLife.09457.001)

[

## eLife digest

](https://elifesciences.org/articles/9457#)

Throughout life, animals must learn how to respond accurately to new sensations and environments, while retaining knowledge of previous experiences. Learning is widely believed to modify the connections (called synapses) between neurons of the cerebral cortex and other brain areas. This process is known as synaptic plasticity. Experimentally, presynaptic and postsynaptic changes have been identified, but it is not known what advantages there are to changing both components when, in principle, changing either might suffice.

To investigate this, Costa et al. developed a mathematical model of synaptic plasticity that captured both pre- and postsynaptic changes, based on a number of experiments over the last decade from recordings in the rat sensory cortices.

There were two major findings from this model. First, if both presynaptic and postsynaptic changes occur, the modeling results indicated that sensory perception could become more precise, as has been recently found in the rat auditory system. Second, because the details of presynaptic and postsynaptic changes are different, previously triggered changes leave behind a type of memory trace that allows apparently forgotten information to be rapidly relearned.

Interestingly, similar asymmetries have been reported in other brain regions. One future challenge is to understand whether these findings constitute a general principle of plasticity in the brain.

[https://doi.org/10.7554/eLife.09457.002](https://doi.org/10.7554/eLife.09457.002)

[

## Main text

](https://elifesciences.org/articles/9457#)

Survival depends on learning accurate actions in response to sensory stimuli while remaining capable to quickly adapt in dynamic environments. The neural substrate of learning is believed to be long-term synaptic plasticity ([Pawlak et al., 2013](https://elifesciences.org/articles/9457#bib38); [Nabavi et al., 2014](https://elifesciences.org/articles/9457#bib35)). After decades of debate ([MacDougall and Fine, 2013](https://elifesciences.org/articles/9457#bib28); [Padamsey and Emptage, 2014](https://elifesciences.org/articles/9457#bib37)), it has become increasingly clear that expression of long-term synaptic plasticity can be either pre- or postsynaptic or both ([Zakharenko et al., 2001](https://elifesciences.org/articles/9457#bib58); [Bayazitov et al., 2007](https://elifesciences.org/articles/9457#bib3); [Sjöström et al., 2007](https://elifesciences.org/articles/9457#bib46); [Loebel et al., 2013](https://elifesciences.org/articles/9457#bib27); [Yang and Calakos, 2013](https://elifesciences.org/articles/9457#bib57)). However, the functional consequences of this segregation into pre- and postsynaptically expressed plasticity have remained unclear. To investigate this, we developed a biologically tuned spike-timing-dependent plasticity (STDP) model, that in contrast to earlier models ([Gerstner et al., 1996](https://elifesciences.org/articles/9457#bib18); [Song et al., 2000](https://elifesciences.org/articles/9457#bib47); [Senn et al., 2001](https://elifesciences.org/articles/9457#bib40); [Seung, 2003](https://elifesciences.org/articles/9457#bib41); [Froemke et al., 2006](https://elifesciences.org/articles/9457#bib16); [Pfister and Gerstner, 2006](https://elifesciences.org/articles/9457#bib39); [Leibold and Bendels, 2009](https://elifesciences.org/articles/9457#bib25); [Clopath et al., 2010](https://elifesciences.org/articles/9457#bib9); [Carvalho and Buonomano, 2011](https://elifesciences.org/articles/9457#bib7); [Graupner and Brunel, 2012](https://elifesciences.org/articles/9457#bib20); [Albers et al., 2013](https://elifesciences.org/articles/9457#bib1)), involves both loci of expression.

Inspired by earlier work ([Song et al., 2000](https://elifesciences.org/articles/9457#bib47); [Pfister and Gerstner, 2006](https://elifesciences.org/articles/9457#bib39)), this phenomenological model relies on exponentially decaying traces of the pre- and postsynaptic spike trains, *X* and *Y* ([Figure 1A,B](https://elifesciences.org/articles/9457#fig1)). The presynaptic trace *x*+ tracks past presynaptic activity, for example, glutamate binding to postsynaptic NMDA receptors. When presynaptic activity *x*+ is rapidly followed by postsynaptic spikes, unblocking NMDA receptors, postsynaptically expressed long-term potentiation (LTP) is triggered and increases the postsynaptic factor *q*, which can be interpreted as the quantal amplitude. Conversely, the postsynaptic trace *y*+ represents prior postsynaptic activity, for example, retrograde nitric oxide (NO) signalling, which when paired with presynaptic spikes leads to presynaptically expressed LTP ([Sjöström et al., 2007](https://elifesciences.org/articles/9457#bib46)). Finally, the trace *y*− tracks postsynaptic activity such as endocannabinoid (eCB) retrograde release and elicits presynaptically expressed long-term depression (LTD) when coincident with presynaptic spikes ([Sjöström et al., 2003](https://elifesciences.org/articles/9457#bib44)). Presynaptically expressed plasticity is conveyed by long-term changes in the presynaptic factor *P* ([Markram et al., 1998](https://elifesciences.org/articles/9457#bib31)), which can be interpreted as the presynaptic release probability (see ‘Materials and methods’).

  [![](https://iiif.elifesciences.org/lax/09457%2Felife-09457-fig1-v4.tif/full/617,/0/default.jpg)](https://iiif.elifesciences.org/lax/09457%2Felife-09457-fig1-v4.tif/full/1500,/0/default.jpg)

###### Unified model of pre- and postsynaptically expressed STDP.

(**A**) The synaptic weight is the product of a presynaptic factor *P* and a postsynaptic factor *q*. Long-term modifications in *P* and *q* are governed by interactions between the pre- and postsynaptic spike …

[https://doi.org/10.7554/eLife.09457.003](https://doi.org/10.7554/eLife.09457.003)

The model parameters were tuned to an extensive data set of plasticity experiments of monosynaptic connections between neocortical layer-5 pyramidal cells ([Sjöström et al., 2001](https://elifesciences.org/articles/9457#bib43), [2003](https://elifesciences.org/articles/9457#bib44), [2007](https://elifesciences.org/articles/9457#bib46)). Homeostatic scaling of the postsynaptic amplitude *q* was included to counterbalance postsynaptic potentiation (see ‘Materials and methods’) ([Turrigiano et al., 1998](https://elifesciences.org/articles/9457#bib51)). The resulting model not only captures the timing and frequency dependence of the synaptic strength changes ([Figure 1C](https://elifesciences.org/articles/9457#fig1) and [Figure 1—figure supplement 1](https://elifesciences.org/articles/09457/figures#fig1s1)), but also its pre- as well as postsynaptic expression ([Figure 1D,E](https://elifesciences.org/articles/9457#fig1)). It thus captures the observed cross-scale interactions between short and long-term synaptic plasticity ([Sjöström et al., 2003](https://elifesciences.org/articles/9457#bib44), [2007](https://elifesciences.org/articles/9457#bib46)). Short-term depression becomes weaker after LTD and stronger after LTP ([Figure 1F,G](https://elifesciences.org/articles/9457#fig1)). We validated the model against experiments with pharmacological blockade of presynaptic LTD or LTP (see ‘Materials and methods’). Abolishing presynaptic LTP by NO blockade reduced total potentiation as only the postsynaptic potentiation component was left ([Sjöström et al., 2007](https://elifesciences.org/articles/9457#bib46)). Likewise, with the presynaptic trace *y*+ disabled, presynaptic LTP was blocked, while the synaptic dynamics remained unchanged ([Figure 1H](https://elifesciences.org/articles/9457#fig1) and [Figure 1—figure supplement 3A](https://elifesciences.org/articles/09457/figures#fig1s3)). Conversely, simulated blockade of presynaptic LTD during LTP induction gave rise to stronger presynaptic potentiation and short-term depression, as observed experimentally during eCB blockade ([Sjöström et al., 2007](https://elifesciences.org/articles/9457#bib46)) ([Figure 1H](https://elifesciences.org/articles/9457#fig1) and [Figure 1—figure supplement 3B](https://elifesciences.org/articles/09457/figures#fig1s3)).

We first investigated the functional consequences of unified pre- and postsynaptically expressed STDP on the postsynaptic responses during cortical receptive field development. We simulated receptive field development of a postsynaptic neuron receiving 100 synaptic inputs (‘Materials and methods’). Presynaptic activity was described by Poisson processes with rates spatially distributed according to a Gaussian profile ([Figure 2A](https://elifesciences.org/articles/9457#fig2)). We defined inputs near the peak of the Gaussian profile as *on*, and those far away from the peak as *off*. After learning, *on* neurons had increased *q* and *P*, while *off* neurons had reduced *q* and *P* ([Figure 2A](https://elifesciences.org/articles/9457#fig2)). During learning, the changes in *q* are preceded by changes in *P* ([Figure 2C](https://elifesciences.org/articles/9457#fig2)). To quantify the effect of the plasticity on the postsynaptic neuron, we stimulate a given input and calculated the signal-to-noise ratio (SNR) of the first postsynaptic response amidst background noise (see ‘Materials and methods’). A high SNR means that the response can be easily distinguished from the background. After learning, only *on* inputs had developed a high SNR ([Figure 2B](https://elifesciences.org/articles/9457#fig2)). Although both high and low *P* yielded low variance ([Figure 2—figure supplement 1](https://elifesciences.org/articles/09457/figures#fig2s1)), high *P* was required for high SNR ([Figure 2C](https://elifesciences.org/articles/9457#fig2)).

  [![](https://iiif.elifesciences.org/lax/09457%2Felife-09457-fig2-v4.tif/full/617,/0/default.jpg)](https://iiif.elifesciences.org/lax/09457%2Felife-09457-fig2-v4.tif/full/1500,/0/default.jpg)

###### Unified pre- and postsynaptic plasticity improves receptive field discriminability.

(**A**) Synaptic input rates follow a Gaussian spatial profile (solid grey line). Initially, the presynaptic factor *P* (top) and the postsynaptic factor *q* (bottom) are uniformly distributed (dashed …

[https://doi.org/10.7554/eLife.09457.007](https://doi.org/10.7554/eLife.09457.007)

To further assess the discriminability of the first postsynaptic response, we used classification analysis (see ‘Materials and methods’), which revealed that *on* inputs obtained a near-perfect discrimination ([Figure 2D](https://elifesciences.org/articles/9457#fig2)) over a range of background noise levels ([Figure 2—figure supplement 1](https://elifesciences.org/articles/09457/figures#fig2s1)). However, a model with only postsynaptic LTP, increasing *q* only, did not yield as reliable synaptic transmission (blue curve in [Figure 2C,D](https://elifesciences.org/articles/9457#fig2))—maximal reliability required presynaptic LTP in addition. This is because, the variance of the first postsynaptic response increases quadratically with the postsynaptic factor *q* (see ‘Materials and methods’). Our learning rule compensates for this increase in variance by also increasing the presynaptic factor *P*, thus making postsynaptic responses reliable and easier to discriminate. The increased discriminability does not only hold for the first response, but generalizes when considering the sum of the first *k* postsynaptic responses. Furthermore, the benefit of unified STDP remained when we compared the temporal information transmission across a range of presynaptic frequencies ([Figure 2—figure supplement 2](https://elifesciences.org/articles/09457/figures#fig2s2)) ([Fuhrmann et al., 2002](https://elifesciences.org/articles/9457#bib17); [Testa-Silva et al., 2014](https://elifesciences.org/articles/9457#bib50)).

The change in SNR and variability is consistent with recent sensory perception experiments ([Froemke et al., 2013](https://elifesciences.org/articles/9457#bib15)) in which pairing a tone with nucleus basalis stimulation led to an increased mean and a decreased variability of synaptic responses ([Figure 2—figure supplement 3](https://elifesciences.org/articles/09457/figures#fig2s3)). Mapped to the parameters of the model, both *q* and *P* of the potentiated *on* responses increased (see ‘Materials and methods’). Conversely, *off* responses that were depressed, decreased in *P* and did not significantly change in *q* ([Figure 2—figure supplement 3](https://elifesciences.org/articles/09457/figures#fig2s3)), consistent with the initial modifications that the model predicts ([Figure 2C](https://elifesciences.org/articles/9457#fig2)). Therefore, unified pre- and postsynaptically expressed plasticity can account for the improved sensory perception after learning observed experimentally ([Froemke et al., 2013](https://elifesciences.org/articles/9457#bib15)). Furthermore our model suggests that both pre- and postsynaptic components should depend on sensory experience, in agreement with prior findings ([Finnerty et al., 1999](https://elifesciences.org/articles/9457#bib14); [Cheetham et al., 2014](https://elifesciences.org/articles/9457#bib8)).

Plasticity should also allow the organism to quickly adapt to changing environments. Expression of layer-5 pyramidal cell STDP is curiously asymmetric: LTP is both pre- and postsynaptic ([Sjöström et al., 2007](https://elifesciences.org/articles/9457#bib46)), whereas LTD is expressed only presynaptically on the slice experiments timescale ([Sjöström et al., 2003](https://elifesciences.org/articles/9457#bib44)). In addition, presynaptic modifications are stronger than postsynaptic LTP ([Figure 1D,E](https://elifesciences.org/articles/9457#fig1)). To explore the consequences of this asymmetry, we extended the above network to study development when high rate inputs alternate between two locations. The neuron learned each receptive field by changes in the presynaptic factor *P* and the postsynaptic factor *q* ([Figure 3A–C](https://elifesciences.org/articles/9457#fig3)). When the stimulus location changed, however, the postsynaptic memory trace decayed only very slowly as a result of homeostatic scaling ([Figure 3B](https://elifesciences.org/articles/9457#fig3)). As a result, the neuron could rapidly relearn the previously acquired receptive field by just increasing *P*, which amounted to a 10-fold decrease in time to learn ([Figure 3D,E](https://elifesciences.org/articles/9457#fig3)). Unified pre- and postsynaptically expressed STDP thus allows for learning of new information while retaining hidden traces of prior experience.

  [![](https://iiif.elifesciences.org/lax/09457%2Felife-09457-fig3-v4.tif/full/617,/0/default.jpg)](https://iiif.elifesciences.org/lax/09457%2Felife-09457-fig3-v4.tif/full/1500,/0/default.jpg)

###### Unified pre- and postsynaptic STDP displays rapid relearning of previously experienced stimuli.

(**A**) The presynaptic factor *P* follows the switching between two stimuli (red and blue profiles, arrows indicate switching time-points). (**B**) The postsynaptic factor *q*, however, is not erased and a …

[https://doi.org/10.7554/eLife.09457.011](https://doi.org/10.7554/eLife.09457.011)

Interestingly, spine changes in layer-5 pyramidal cells of visual cortex outlast sensory experience ([Hofer et al., 2008](https://elifesciences.org/articles/9457#bib23)), thus providing a structural substrate for the psychological phenomenon known as memory savings ([Ebbinghaus, 1913](https://elifesciences.org/articles/9457#bib13)). As synaptic structure and synaptic weight are closely correlated ([Matsuzaki et al., 2001](https://elifesciences.org/articles/9457#bib32); [Holtmaat and Svoboda, 2009](https://elifesciences.org/articles/9457#bib24)), the memory savings mediated by structural spine plasticity ([Hofer et al., 2008](https://elifesciences.org/articles/9457#bib23)) are reminiscent of those provided by our unified plasticity model.

Here we have focused on neocortical data. Models based on synaptic traces are flexible and can describe both neocortical and hippocampal plasticity data ([Pfister and Gerstner, 2006](https://elifesciences.org/articles/9457#bib39), and [Appendix 1](https://elifesciences.org/articles/9457#app1)). We therefore expect that our modelling framework should also be able to capture plasticity in other brain regions, although with different parameters. For example, there are several key differences in the expression locus and in the speed of pre- and postsynaptic changes in hippocampus ([Bayazitov et al., 2007](https://elifesciences.org/articles/9457#bib3)). In cerebellum, there is evidence for the opposite asymmetry of expression, with LTP being pre- and postsynaptic, but LTD only postsynaptic ([Wang and Linden, 2000](https://elifesciences.org/articles/9457#bib55); [Lev-Ram et al., 2003](https://elifesciences.org/articles/9457#bib26)).

In our work, memory savings are a consequence of the postsynaptic weight decay occurring on a much slower timescale than the presynaptic modifications. This arrangement, however, is not crucial for the predicted rapid relearning. What is necessary is that the synaptic strength is the product of pre- and postsynaptic components (*w* = *Pq*) and that these components evolve on different timescales. For example, fast postsynaptic changes combined with slow presynaptic changes would allow for the corresponding presynaptic trace of previous experience, which indeed could be the case in the cerebellum ([Wang and Linden, 2000](https://elifesciences.org/articles/9457#bib55); [Lev-Ram et al., 2003](https://elifesciences.org/articles/9457#bib26)). Taken together, these findings suggest that plasticity expression asymmetry is not particular to neocortical layer-5 pyramidal cells, but rather a general functional principle that extends across different brain regions. Interestingly, similar functions can also be performed by neuronal inhibition, such as sharpening receptive fields ([Wilson et al., 2012](https://elifesciences.org/articles/9457#bib56)), keeping hidden memories in recurrent neural networks ([Vogels et al., 2011](https://elifesciences.org/articles/9457#bib53)), and acting as a substrate for memory savings in the cerebellum ([Medina et al., 2001](https://elifesciences.org/articles/9457#bib33)).

The existence of both pre- and postsynaptic expression of long-term synaptic plasticity has been enigmatic. Although it has been known that changes in release probability play a key role in determining the transmission of information across synapses ([Otmakhov et al., 1993](https://elifesciences.org/articles/9457#bib36); [Stevens and Wang, 1994](https://elifesciences.org/articles/9457#bib48); [Carvalho and Buonomano, 2011](https://elifesciences.org/articles/9457#bib7)), our theoretical treatment is the first to show that combined pre- and postsynaptic expression of long-term synaptic plasticity provides the brain with reliable sensory detection and the ability to quickly relearn previously experienced stimuli.

### Materials and methods

#### Short- and long-term synaptic plasticity model

##### Short-term plasticity model

[Request a detailed protocol](https://bio-protocol.org/eLIFErap09457?item=s1-1-1)

To model short-term synaptic plasticity, we used the Tsodyks-Markram model with facilitation ([Markram et al., 1998](https://elifesciences.org/articles/9457#bib31)). This model is defined by the following ODEs

(1) $<math><mrow><mfrac><mrow><mi>d</mi><mi>r</mi><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow></mrow><mrow><mi>d</mi><mi>t</mi></mrow></mfrac><mo>=</mo><mfrac><mrow><mn>1</mn><mo>−</mo><mi>r</mi><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow></mrow><mi>D</mi></mfrac><mo>−</mo><mi>p</mi><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow><mi>r</mi><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow><mi>X</mi><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow><mo>,</mo></mrow></math>$

(2) $<math><mrow><mfrac><mrow><mi>d</mi><mi>p</mi><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow></mrow><mrow><mi>d</mi><mi>t</mi></mrow></mfrac><mo>=</mo><mfrac><mrow><mi>P</mi><mo>−</mo><mi>p</mi><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow></mrow><mi>F</mi></mfrac><mo>+</mo><mi>P</mi><mrow><mo>[</mo><mrow><mn>1</mn><mo>−</mo><mi>p</mi><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow></mrow><mo>]</mo></mrow><mi>X</mi><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow><mo>.</mo></mrow></math>$

The first equation models the vesicle depletion process, where the (normalized) number of vesicles *r* is decreased by an amount *p*(*t*)*r*(*t*) after a presynaptic spike from the train $<math id="inf2"><mi>X</mi><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow><mo>=</mo><msub><mo>∑</mo><msub><mi>t</mi><mtext>pre</mtext></msub></msub><mi>δ</mi><mrow><mo>(</mo><mi>t</mi><mo>−</mo><msub><mi>t</mi><mtext>pre</mtext></msub><mo>)</mo></mrow></math>$. Between spikes *r* recovers to 1 with a depression time constant *D*. The second equation models the dynamics of the presynaptic factor *p* which increases an amount *P*\[1 − *p*\] after every presynaptic spike, decaying back to baseline presynaptic factor *P* with a facilitation time constant *F*. By varying the synaptic dynamics parameters *D*, *F* and *P*, one can obtain different synaptic dynamics. We used typical values for pyramidal-onto-pyramidal synapses ([Costa et al., 2013](https://elifesciences.org/articles/9457#bib11)), *D* = 200 ms and *F* = 50 ms, while *P* is modified by long-term plasticity as below. The average number of vesicles released per spike is *r*(*t*)*p*(*t*), which can be interpreted as the presynaptic strength.

#### Long-term plasticity model

[Request a detailed protocol](https://bio-protocol.org/eLIFErap09457?item=s1-2)

In layer-5 pyramidal to pyramidal cell synapses, timing-dependent LTD is presynaptically expressed. It is mediated by the coincidence between a postsynaptic signal (eCB release) and a presynaptic signal (presynaptic NMDA receptor activation) ([Sjöström et al., 2003](https://elifesciences.org/articles/9457#bib44), [2004](https://elifesciences.org/articles/9457#bib45); [Bender and Feldman, 2006](https://elifesciences.org/articles/9457#bib4); [Yang and Calakos, 2013](https://elifesciences.org/articles/9457#bib57)). LTP is driven by postsynaptic coincidence detection of the combined binding of glutamate and postsynaptic depolarization ([Bender and Feldman, 2006](https://elifesciences.org/articles/9457#bib4); [Sjöström et al., 2007](https://elifesciences.org/articles/9457#bib46); [Shouval et al., 2010](https://elifesciences.org/articles/9457#bib42)), promoting an increase in the number and/or properties of postsynaptic AMPA receptors ([Malinow and Malenka, 2002](https://elifesciences.org/articles/9457#bib29)). However, timing-dependent LTP also has a presynaptic component, mediated by postsynaptic diffusion of NO ([Hardingham and Fox, 2006](https://elifesciences.org/articles/9457#bib22); [Sjöström et al., 2007](https://elifesciences.org/articles/9457#bib46); [Hardingham et al., 2013](https://elifesciences.org/articles/9457#bib21); [Yang and Calakos, 2013](https://elifesciences.org/articles/9457#bib57)).

Our phenomenological triplet model of long-term modification of pre- and postsynaptic components has three synaptic traces, two postsynaptic (*y*+ and *y*−) and one presynaptic (*x*+), which increase upon a post- or presynaptic spike, respectively (see [Appendix 1](https://elifesciences.org/articles/9457#app1) for a more detailed comparison with the triplet model ([Pfister and Gerstner, 2006](https://elifesciences.org/articles/9457#bib39))). The traces are obtained by filtering the spike trains with a first-order low-pass filter. We defined the postsynaptic depression trace

(3) $<math><mrow><mfrac><mrow><mi>d</mi><msub><mi>y</mi><mo>−</mo></msub><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow></mrow><mrow><mi>d</mi><mi>t</mi></mrow></mfrac><mo>=</mo><mfrac><mrow><mo>−</mo><msub><mi>y</mi><mo>−</mo></msub><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow></mrow><mrow><msub><mi>τ</mi><mrow><msub><mi>y</mi><mo>−</mo></msub></mrow></msub></mrow></mfrac><mo>+</mo><mi>Y</mi><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow><mo>,</mo></mrow></math>$

the postsynaptic potentiation trace

(4) $<math><mrow><mfrac><mrow><mi>d</mi><msub><mi>y</mi><mo>+</mo></msub><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow></mrow><mrow><mi>d</mi><mi>t</mi></mrow></mfrac><mo>=</mo><mfrac><mrow><mo>−</mo><msub><mi>y</mi><mo>+</mo></msub><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow></mrow><mrow><msub><mi>τ</mi><mrow><msub><mi>y</mi><mo>+</mo></msub></mrow></msub></mrow></mfrac><mo>+</mo><mi>Y</mi><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow><mo>,</mo></mrow></math>$

and the presynaptic potentiation trace

(5) $<math><mrow><mfrac><mrow><mi>d</mi><msub><mi>x</mi><mo>+</mo></msub><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow></mrow><mrow><mi>d</mi><mi>t</mi></mrow></mfrac><mo>=</mo><mfrac><mrow><mo>−</mo><msub><mi>x</mi><mo>+</mo></msub><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow></mrow><mrow><msub><mi>τ</mi><mrow><msub><mi>x</mi><mo>+</mo></msub></mrow></msub></mrow></mfrac><mo>+</mo><mi>X</mi><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow><mo>.</mo></mrow></math>$

The long-term modification in the weight is achieved by modifying the postsynaptic factor *q* and the presynaptic factor *P*. The postsynaptic factor is modified with every postsynaptic spike *Y* according to

(6) $<math><mstyle displaystyle="true" scriptlevel="0"><mrow><mi mathvariant="normal">Δ</mi><mi>q</mi><mo>=</mo><msub><mi>c</mi><mrow><mo>+</mo></mrow></msub><munder><mrow><munder><mrow><msub><mi>x</mi><mrow><mo>+</mo></mrow></msub><mo stretchy="false">(</mo><mi>t</mi><mo stretchy="false">)</mo><mi>y</mi><mi mathvariant="normal">_</mi><mspace width="thinmathspace"></mspace><mo stretchy="false">(</mo><mi>t</mi><mo>−</mo><mi>ϵ</mi><mo stretchy="false">)</mo><mi>Y</mi><mo stretchy="false">(</mo><mi>t</mi><mo stretchy="false">)</mo></mrow><mo>⏟</mo></munder></mrow><mrow><msubsup><mtext>Triplet</mtext><mrow><mtext>post</mtext></mrow><mrow><mtext>LTP</mtext></mrow></msubsup></mrow></munder><mo>,</mo></mrow></mstyle></math>$

where *c*+ is a constant that sets the amount of postsynaptic LTP. The *y*− trace is evaluated at (*t* − *ϵ*), so that the value of the respective synaptic trace is readout before being updated. The triplet character of this rule is expressed by the fact that it contains the presynaptic component once, but the postsynaptic activity twice (*Y* and filtered version *y*−). This ensures that LTP only takes place when the postsynaptic spike follows both a presynaptic spike and a preceding postsynaptic spike ([Pfister and Gerstner, 2006](https://elifesciences.org/articles/9457#bib39)). As a result, low pairing frequencies do not lead to LTP, as *y*− will have decayed, consistent with data ([Sjöström et al., 2001](https://elifesciences.org/articles/9457#bib43)).

Similarly, the presynaptic factor is modified whenever the presynaptic cell is active according to

(7) $<math><mstyle displaystyle="true" scriptlevel="0"><mrow><mi mathvariant="normal">Δ</mi><mi>P</mi><mo>=</mo><mo>−</mo><mi>d</mi><mi mathvariant="normal">_</mi><mspace width="thinmathspace"></mspace><munder><mrow><munder><mrow><mi>y</mi><mi mathvariant="normal">_</mi><mspace width="thinmathspace"></mspace><mo stretchy="false">(</mo><mi>t</mi><mo stretchy="false">)</mo><msub><mi>y</mi><mo>+</mo></msub><mo stretchy="false">(</mo><mi>t</mi><mo stretchy="false">)</mo><mi>X</mi><mo stretchy="false">(</mo><mi>t</mi><mo stretchy="false">)</mo></mrow><mo>⏟</mo></munder></mrow><mrow><msubsup><mtext>Triplet</mtext><mrow><mtext>pre</mtext></mrow><mrow><mtext>LTD</mtext></mrow></msubsup></mrow></munder><mo>+</mo><msub><mi>d</mi><mo>+</mo></msub><mspace width="thinmathspace"></mspace><munder><mrow><munder><mrow><msub><mi>x</mi><mo>+</mo></msub><mspace width="thinmathspace"></mspace><mo stretchy="false">(</mo><mi>t</mi><mo>−</mo><mi>ϵ</mi><mo stretchy="false">)</mo><msub><mi>y</mi><mo>+</mo></msub><mo stretchy="false">(</mo><mi>t</mi><mo stretchy="false">)</mo><mi>X</mi><mo stretchy="false">(</mo><mi>t</mi><mo stretchy="false">)</mo></mrow><mo>⏟</mo></munder></mrow><mrow><msubsup><mtext>Triplet</mtext><mrow><mtext>pre</mtext></mrow><mrow><mtext>LTP</mtext></mrow></msubsup></mrow></munder><mo>.</mo></mrow></mstyle></math>$

For plasticity in *P* to occur, the presynaptic spikes *X* readout the postsynaptic traces (presynaptic coincidence detection), *y*−*y*+ for presynaptic LTD and *x*+*y*+ for presynaptic LTP. *d*− and *d*+ are constants that set the amount of presynaptic LTD and LTP, respectively. While presynaptic LTD has a triplet form, it contains two postsynaptic traces and the raw presynaptic spike train. Therefore it does not vanish at low frequencies. Equivalently, this term could be written as a doublet rule with a double exponential as the presynaptic trace.

The total synaptic strength is a product of both pre- and postsynaptic factors

(8) $<math><mrow><mi>w</mi><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow><mo>=</mo><mi>q</mi><mi>p</mi><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow><mi>r</mi><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow><mo>.</mo></mrow></math>$

For a synapse that has not been stimulated recently this simplifies to *w* = *Pq*.

Being a probability we hard-bounded *P* = \[0, 1\]. The postsynaptic factor *q* had a lower bound of 0, and an upper bound of 2. Alternatively a soft-bounded rule could be used ([van Rossum et al., 2012](https://elifesciences.org/articles/9457#bib52)). In the data used to fit the model (see below), postsynaptic homosynaptic LTD was not apparent on the timescale of the experiment. Because it seems unrealistic that the postsynaptic factor *q* never decreases, slow homeostasic scaling of the postsynaptic factor was included for network simulations ([Turrigiano et al., 1998](https://elifesciences.org/articles/9457#bib51)). This prevents weakly active synapses from potentiating the postsynaptic factor *q*. It was modelled as a postsynaptic subtractive normalization, so that the total change in *q* of synapse *i* was equal to $<math id="inf3"><mstyle displaystyle="true" scriptlevel="0"><mrow><mi mathvariant="normal">Δ</mi><msub><mi>q</mi><mi>i</mi></msub><mo>−</mo><mi>α</mi><mfrac><mn>1</mn><mi>N</mi></mfrac><msubsup><mo movablelimits="false">∑</mo><mrow><mi>j</mi><mo>=</mo><mn>1</mn></mrow><mrow><mi>N</mi></mrow></msubsup><mrow><mi mathvariant="normal">Δ</mi><msub><mi>q</mi><mi>j</mi></msub></mrow></mrow></mstyle></math>$ ([Miller and MacKay, 1994](https://elifesciences.org/articles/9457#bib34)). The only condition on the speed *α* for it to be consistent with the data, is that it should not lead to noticable homeostasis on the timescale of the experiments. For computational efficiency we used *α* = 0.075, which is still orders of magnitude faster than what has been observed in homeostasis experiments. The exact form of slow normalization (*α* → 0) does not affect the qualitative behavior of the model. Note that the timescale of the slow normalization determines how long the memory savings effects are present.

To speed up the numerical implementations, we integrated the synaptic traces between the pre- and postsynaptic spikes. In the following equations, we label the presynaptic spikes with *k* and the postsynaptic ones with *l*.

(9) $<math><msubsup><mi>y</mi><mo>−</mo><mrow><mi>l</mi><mo>+</mo><mn>1</mn></mrow></msubsup><mo>=</mo><msubsup><mi>y</mi><mrow><mo>−</mo><mo> </mo></mrow><mi>l</mi></msubsup><mtext> exp</mtext><mrow><mo>(</mo><mo>−</mo><mfrac><mrow><mtext>Δ</mtext><msub><mi>t</mi><mtext>post</mtext></msub></mrow><msub><mi>τ</mi><msub><mi>y</mi><mo>−</mo></msub></msub></mfrac><mo>)</mo></mrow><mo>+</mo><mn>1</mn><mo>,</mo></math>$

(10) $<math><msubsup><mi>y</mi><mo>+</mo><mrow><mi>l</mi><mo>+</mo><mn>1</mn></mrow></msubsup><mo>=</mo><msubsup><mi>y</mi><mrow><mo>+</mo><mo> </mo></mrow><mi>l</mi></msubsup><mtext> exp</mtext><mrow><mo>(</mo><mo>−</mo><mfrac><mrow><mtext>Δ</mtext><msub><mi>t</mi><mtext>post</mtext></msub></mrow><msub><mi>τ</mi><msub><mi>y</mi><mo>+</mo></msub></msub></mfrac><mo>)</mo></mrow><mo>+</mo><mn>1</mn><mo>,</mo></math>$

(11) $<math><msubsup><mi>x</mi><mo>+</mo><mrow><mi>k</mi><mo>+</mo><mn>1</mn></mrow></msubsup><mo>=</mo><msubsup><mi>x</mi><mo>+</mo><mi>k</mi></msubsup><mo> </mo><mtext> exp</mtext><mrow><mo>(</mo><mo>−</mo><mfrac><mrow><mtext>Δ</mtext><msub><mi>t</mi><mtext>pre</mtext></msub></mrow><msub><mi>τ</mi><msub><mi>x</mi><mo>+</mo></msub></msub></mfrac><mo>)</mo></mrow><mo>+</mo><mn>1.</mn></math>$

We subsequently integrated the model between pre- and postsynaptic spikes

(12) $<math><msub><mi>q</mi><mrow><mi>l</mi><mo>+</mo><mn>1</mn></mrow></msub><mo>=</mo><msub><mi>q</mi><mi>l</mi></msub><mo>+</mo><msub><mi>c</mi><mo>+</mo></msub><msubsup><mi>x</mi><mrow><mo>+</mo><mo> </mo></mrow><mi>k</mi></msubsup><mtext> exp</mtext><mrow><mo>(</mo><mo>−</mo><mfrac><mrow><mtext>Δ</mtext><msub><mi>t</mi><mrow><mtext>post</mtext><mo>−</mo><mtext>pre</mtext></mrow></msub></mrow><msub><mi>τ</mi><msub><mi>x</mi><mo>+</mo></msub></msub></mfrac><mo>)</mo></mrow><msubsup><mi>y</mi><mrow><mo>−</mo><mo> </mo></mrow><mi>l</mi></msubsup><mtext> exp</mtext><mrow><mo>(</mo><mo>−</mo><mfrac><mrow><mtext>Δ</mtext><msub><mi>t</mi><mtext>post</mtext></msub></mrow><msub><mi>τ</mi><msub><mi>y</mi><mo>−</mo></msub></msub></mfrac><mo>)</mo></mrow><mo>,</mo></math>$

(13) $<math><msub><mi>P</mi><mrow><mi>k</mi><mo>+</mo><mn>1</mn></mrow></msub><mo>=</mo><msub><mi>P</mi><mi>k</mi></msub><mo>−</mo><msub><mi>d</mi><mo>−</mo></msub><msubsup><mi>y</mi><mo>−</mo><mi>l</mi></msubsup><mtext> exp</mtext><mrow><mo>(</mo><mo>−</mo><mfrac><mrow><mtext>Δ</mtext><msub><mi>t</mi><mrow><mtext>pre</mtext><mo>−</mo><mtext>post</mtext></mrow></msub></mrow><msub><mi>τ</mi><msub><mi>y</mi><mo>−</mo></msub></msub></mfrac><mo>)</mo></mrow><msubsup><mi>y</mi><mrow><mo>+</mo><mo> </mo></mrow><mi>l</mi></msubsup><mtext> exp</mtext><mrow><mo>(</mo><mo>−</mo><mfrac><mrow><mtext>Δ</mtext><msub><mi>t</mi><mrow><mtext>pre</mtext><mo>−</mo><mtext>post</mtext></mrow></msub></mrow><msub><mi>τ</mi><msub><mi>y</mi><mo>+</mo></msub></msub></mfrac><mo>)</mo></mrow><mo>+</mo><msub><mi>d</mi><mo>+</mo></msub><msubsup><mi>y</mi><mrow><mo>+</mo><mo> </mo></mrow><mi>l</mi></msubsup><mtext> exp</mtext><mrow><mo>(</mo><mo>−</mo><mfrac><mrow><mtext>Δ</mtext><msub><mi>t</mi><mrow><mtext>pre</mtext><mo>−</mo><mtext>post</mtext></mrow></msub></mrow><msub><mi>τ</mi><msub><mi>y</mi><mo>+</mo></msub></msub></mfrac><mo>)</mo></mrow><msubsup><mi>x</mi><mrow><mo>+</mo><mo> </mo></mrow><mi>k</mi></msubsup><mtext> exp</mtext><mrow><mo>(</mo><mo>−</mo><mfrac><mrow><mtext>Δ</mtext><msub><mi>t</mi><mtext>pre</mtext></msub></mrow><msub><mi>τ</mi><msub><mi>x</mi><mo>+</mo></msub></msub></mfrac><mo>)</mo></mrow><mo>,</mo></math>$

where Δ*t*post−pre is the time between the current postsynaptic spike and the last presynaptic spike, Δ*t*post is the time between the current postsynaptic spike and the last one, and similarly for Δ*t*pre−post and Δ*t*pre. Finally, we also integrated the STP ([Equations 1, 2](https://elifesciences.org/articles/9457#equ1)) between presynaptic spikes *k* and *k* + 1, a time Δ*t*pre apart, yielding

(14) $<math><mrow><msub><mi>r</mi><mrow><mi>k</mi><mo>+</mo><mn>1</mn></mrow></msub><mo>=</mo><mn>1</mn><mo>−</mo><mrow><mo>[</mo><mrow><mn>1</mn><mo>−</mo><msub><mi>r</mi><mi>k</mi></msub><mrow><mo>(</mo><mrow><mn>1</mn><mo>−</mo><msub><mi>p</mi><mi>k</mi></msub></mrow><mo>)</mo></mrow></mrow><mo>]</mo></mrow><mtext>exp</mtext><mrow><mo>(</mo><mrow><mo>−</mo><mfrac><mrow><mtext>Δ</mtext><msub><mi>t</mi><mrow><mtext>pre</mtext></mrow></msub></mrow><mi>D</mi></mfrac></mrow><mo>)</mo></mrow><mo>,</mo></mrow></math>$

(15) $<math><mrow><msub><mi>p</mi><mrow><mi>k</mi><mo>+</mo><mn>1</mn></mrow></msub><mo>=</mo><mi>P</mi><mo>+</mo><msub><mi>p</mi><mi>k</mi></msub><mrow><mo>[</mo><mrow><mn>1</mn><mo>−</mo><mi>P</mi></mrow><mo>]</mo></mrow><mtext>exp</mtext><mrow><mo>(</mo><mrow><mo>−</mo><mfrac><mrow><mtext>Δ</mtext><msub><mi>t</mi><mrow><mtext>pre</mtext></mrow></msub></mrow><mi>F</mi></mfrac></mrow><mo>)</mo></mrow><mo>.</mo></mrow></math>$

with initial conditions *r*0 = 1 and *p*0 = *P*.

#### Model fitting to in vitro plasticity data

[Request a detailed protocol](https://bio-protocol.org/eLIFErap09457?item=s1-3)

We fitted the free parameters of the long-term plasticity model ***θ*** = {*d*−, *τ**y*−, *d*+, *τ**y*+, *c*+, *τ**x*+} to the frequency- and timing-dependent slice STDP data of layer-5 pyramidal cells ([Sjöström et al., 2001](https://elifesciences.org/articles/9457#bib43)). Parameters are shown in [Table 1](https://elifesciences.org/articles/9457#tbl1). Rather than fitting to changes in the weight *w*, we fitted directly to modifications in *P* and *q* (see [Equations 21, 22](https://elifesciences.org/articles/9457#equ21) for our estimators of *P* and *q*). This was done by minimizing the mean squared error between the data and the experiments for both *P* and *q* (as shown in [Figure 1](https://elifesciences.org/articles/9457#fig1))

(16) $<math><mrow><mi mathvariant="bold-italic">θ</mi><mo>=</mo><msub><mrow><mtext>argmin</mtext></mrow><mi mathvariant="bold-italic">θ</mi></msub><mfrac><mn>1</mn><mi>N</mi></mfrac><munderover><mstyle displaystyle="true"><mo>∑</mo></mstyle><mi>j</mi><mi>N</mi></munderover><mrow><mo>[</mo><mrow><msup><mrow><mrow><mo>(</mo><mrow><mfrac><mrow><msubsup><mi>P</mi><mrow><mtext>model</mtext></mrow><mrow><mtext>after</mtext></mrow></msubsup></mrow><mrow><msubsup><mi>P</mi><mrow><mtext>model</mtext></mrow><mrow><mtext>before</mtext></mrow></msubsup></mrow></mfrac><mo>−</mo><mfrac><mrow><msubsup><mi>P</mi><mrow><mtext>data</mtext></mrow><mrow><mtext>after</mtext></mrow></msubsup></mrow><mrow><msubsup><mi>P</mi><mrow><mtext>data</mtext></mrow><mrow><mtext>before</mtext></mrow></msubsup></mrow></mfrac></mrow><mo>)</mo></mrow></mrow><mn>2</mn></msup><mo>+</mo><msup><mrow><mrow><mo>(</mo><mrow><mfrac><mrow><msubsup><mi>q</mi><mrow><mtext>model</mtext></mrow><mrow><mtext>after</mtext></mrow></msubsup></mrow><mrow><msubsup><mi>q</mi><mrow><mtext>model</mtext></mrow><mrow><mtext>before</mtext></mrow></msubsup></mrow></mfrac><mo>−</mo><mfrac><mrow><msubsup><mi>q</mi><mrow><mtext>data</mtext></mrow><mrow><mtext>after</mtext></mrow></msubsup></mrow><mrow><msubsup><mi>q</mi><mrow><mtext>data</mtext></mrow><mrow><mtext>before</mtext></mrow></msubsup></mrow></mfrac></mrow><mo>)</mo></mrow></mrow><mn>2</mn></msup></mrow><mo>]</mo></mrow><mo>,</mo></mrow></math>$

where *N* denotes the number of protocols fitted, 10 in total (5 different pairing frequencies with −10 ms or +10 ms relative timing, see below). For induction protocols at high frequencies (≥10 Hz), pre- and postsynaptic spike trains consisted of five spikes that were paired 15 times at 0.1 Hz. Low-frequency pairings (0.1 Hz) were done with a single pre- and postsynaptic spike (as in [Sjöström et al., 2001](https://elifesciences.org/articles/9457#bib43)). Before plasticity induction, *P* and *q* were set to 0.5 and 1, respectively. For the interaction of STP and STDP simulations ([Figure 1F,G](https://elifesciences.org/articles/9457#fig1)), we used a standard passive neuron model with a membrane time constant of 25 ms.

Unified pre- and postsynaptic spike-timing-dependent plasticity (STDP) model parameters

[https://doi.org/10.7554/eLife.09457.012](https://doi.org/10.7554/eLife.09457.012)

| Parameter | *d*− | *τ**y*− (ms) | *d*+ | *τ**y*+ (ms) | *c*+ | *τ**x*+ (ms) |
| --- | --- | --- | --- | --- | --- | --- |
| Young rat visual cortex | 0.1771 | 32.7 | 0.1548 | 230.2 | 0.0618 | 66.6 |

1.  The model was fitted to data from young rat visual cortex ([Sjöström et al., 2001](https://elifesciences.org/articles/9457#bib43)).
    

Comparison between unified pre- and postsynaptic STDP model and different versions of the *triplet* model (for simplicity we removed the function arguments) ([Pfister and Gerstner, 2006](https://elifesciences.org/articles/9457#bib39))

[https://doi.org/10.7554/eLife.09457.013](https://doi.org/10.7554/eLife.09457.013)

|  | *LTD* | *LTP*1 | *LTP*2 |
| --- | --- | --- | --- |
| pre-post STDP | *X d*−*y*−*y*+ | *X d*+*y*+*x*+ | *Y c*+*x*+*y*− |
| minimal HC Triplet | $<math id="inf4"><mrow><mi>X</mi><mtext> </mtext><msubsup><mi>A</mi><mn>2</mn><mo>−</mo></msubsup><msub><mi>y</mi><mn>1</mn></msub></mrow></math>$ | $<math id="inf6"><mrow><mi>Y</mi><mtext> </mtext><msubsup><mi>A</mi><mn>2</mn><mo>+</mo></msubsup><msub><mi>x</mi><mn>1</mn></msub></mrow></math>$ | $<math id="inf8"><mrow><mi>Y</mi><mtext> </mtext><msubsup><mi>A</mi><mn>3</mn><mo>+</mo></msubsup><msub><mi>x</mi><mn>1</mn></msub><msub><mi>y</mi><mn>2</mn></msub></mrow></math>$ |
| minimal VC Triplet | $<math id="inf10"><mrow><mi>X</mi><mtext> </mtext><msubsup><mi>A</mi><mn>2</mn><mo>−</mo></msubsup><msub><mi>y</mi><mn>1</mn></msub></mrow></math>$ | – | $<math id="inf12"><mrow><mi>Y</mi><mtext> </mtext><msubsup><mi>A</mi><mn>3</mn><mo>+</mo></msubsup><msub><mi>x</mi><mn>1</mn></msub><msub><mi>y</mi><mn>2</mn></msub></mrow></math>$ |

Without further fitting this model also captured pharmacological blockade of the plasticity traces. In the model, we simulated the experimental effects of pharmacological blockade by setting the relevant parameter or variable to 0. Specifically, we simulated the effects of blocking two different retrograde messenger systems shown to be involved in STDP in layer-5 pyramidal cell pairs, eCB signaling ([Sjöström et al., 2003](https://elifesciences.org/articles/9457#bib44)) and NO signaling ([Sjöström et al., 2007](https://elifesciences.org/articles/9457#bib46)). To reproduce pharmacological blockade experiments, we used high-frequency pairing (50 Hz) with +10 ms delay, which is comparable with our frequency-dependent results and approximates the long depolarizing currents used in [Sjöström et al. (2007)](https://elifesciences.org/articles/9457#bib46). Blocking eCB receptors prevents presynaptic LTD ([Sjöström et al., 2003](https://elifesciences.org/articles/9457#bib44)). By setting *d*− = 0 presynaptic LTD was disabled. This reveals presynaptic LTP and enhances short-term depression ([Figure 1—figure supplement 3](https://elifesciences.org/articles/09457/figures#fig1s3)), consistent with experimental evidence ([Sjöström et al., 2007](https://elifesciences.org/articles/9457#bib46)), as the drugs used are likely to block presynaptic eCB receptors. In contrast, blocking NO decreases LTP but does not affect short-term synaptic dynamics ([Sjöström et al., 2007](https://elifesciences.org/articles/9457#bib46)) ([Figure 1—figure supplement 3A](https://elifesciences.org/articles/09457/figures#fig1s3)). We simulated this by setting *y*+ = 0, so that both presynaptic components were absent.

#### Stochastic synaptic responses and in vitro *P* and *q* estimation

[Request a detailed protocol](https://bio-protocol.org/eLIFErap09457?item=s1-4)

The release of neurotransmitter was assumed to follow a standard binomial model ([Del Castillo and Katz, 1954](https://elifesciences.org/articles/9457#bib12))

(17) $<math><mrow><msub><mi>P</mi><mrow><mtext>syn</mtext></mrow></msub><mrow><mo>(</mo><mrow><mi>X</mi><mo>=</mo><mi>k</mi></mrow><mo>)</mo></mrow><mo>=</mo><mrow><mo>(</mo><mrow><mtable><mtr><mtd><mi>N</mi></mtd></mtr><mtr><mtd><mi>k</mi></mtd></mtr></mtable></mrow><mo>)</mo></mrow><msup><mi>P</mi><mi>k</mi></msup><msup><mrow><mrow><mo>(</mo><mrow><mn>1</mn><mo>−</mo><mi>P</mi></mrow><mo>)</mo></mrow></mrow><mrow><mi>N</mi><mo>−</mo><mi>k</mi></mrow></msup><mo>,</mo></mrow></math>$

which defines the probability of having *k* successful events (neurotransmitter release) given *N* trials (release sites) with equal probability *P*.

The mean synaptic response is scaled by a postsynaptic factor *q*, which can be related to the quantal amplitude so that

(18) $<math><mrow><msub><mi>μ</mi><mrow><mtext>syn</mtext></mrow></msub><mo>=</mo><mi>P</mi><mi>q</mi><mi>N</mi><mo>,</mo></mrow></math>$

and the variance is

(19) $<math><mrow><msubsup><mi>σ</mi><mrow><mtext>syn</mtext></mrow><mn>2</mn></msubsup><mo>=</mo><msup><mi>q</mi><mn>2</mn></msup><mi>N</mi><mi>P</mi><mrow><mo>(</mo><mrow><mn>1</mn><mo>−</mo><mi>P</mi></mrow><mo>)</mo></mrow><mo>.</mo></mrow></math>$

Following the binomial release model ([Equation 18](https://elifesciences.org/articles/9457#equ18)), *μ*syn ([Equation 19](https://elifesciences.org/articles/9457#equ19)) and $<math id="inf14"><mrow><msubsup><mi>σ</mi><mrow><mtext>syn</mtext></mrow><mn>2</mn></msubsup></mrow></math>$ ([Equation 20](https://elifesciences.org/articles/9457#equ20)),

(20) $<math><mrow><mi>P</mi><mo>=</mo><mfrac><mrow><msub><mi>μ</mi><mrow><mtext>syn</mtext></mrow></msub></mrow><mrow><mi>N</mi><mi>q</mi></mrow></mfrac><mo>,</mo></mrow></math>$

and

(21) $<math><mrow><mi>q</mi><mo>=</mo><mfrac><mrow><msubsup><mi>σ</mi><mrow><mtext>syn</mtext></mrow><mn>2</mn></msubsup></mrow><mrow><msub><mi>μ</mi><mrow><mtext>syn</mtext></mrow></msub></mrow></mfrac><mo>+</mo><mfrac><mrow><msub><mi>μ</mi><mrow><mtext>syn</mtext></mrow></msub></mrow><mi>N</mi></mfrac><mo>.</mo></mrow></math>$

The number of release sites *N* is believed to change only after a few hours ([Bolshakov et al., 1997](https://elifesciences.org/articles/9457#bib5); [Saez and Friedlander, 2009](https://elifesciences.org/articles/9457#bib49)). As the slice synaptic plasticity experiments analysed here lasted only up to 1.5 hr ([Sjöström et al., 2001](https://elifesciences.org/articles/9457#bib43)) and we were interested in the relative changes we assumed constant *N* = 5.5 in our analysis below, as estimated in [Markram et al. (1997)](https://elifesciences.org/articles/9457#bib30) using data from the same connection type we used to fit our model. [Equations 21, 22](https://elifesciences.org/articles/9457#equ21) were used to estimate *P* and *q* from in vitro plasticity data (see above), respectively (dataset deposited at Dryad data repository at [http://dx.doi.org/10.5061/dryad.p286g](http://dx.doi.org/10.5061/dryad.p286g) \[[Costa et al., 2015](https://elifesciences.org/articles/9457#bib10)\]). Note that because the data had to be reanalized in full there are minor differences in the mean weights previously published ([Sjöström et al., 2001](https://elifesciences.org/articles/9457#bib43)).

We verified our *P* and *q* extraction method by analysing short-term plasticity experiments with pharmacological manipulation of presynaptic release or of postsynaptic gain ([Figure 1—figure supplement 2A](https://elifesciences.org/articles/09457/figures#fig1s2), [Sjöström et al., 2003](https://elifesciences.org/articles/9457#bib44)), and experiments with pharmacological blockade of pre- or postsynaptic long-term plasticity ([Figure 1—figure supplement 2B](https://elifesciences.org/articles/09457/figures#fig1s2), [Sjöström et al., 2007](https://elifesciences.org/articles/9457#bib46)) ([Figure 1—figure supplement 2A,B](https://elifesciences.org/articles/09457/figures#fig1s2)). In addition, long-term changes in *P* but not in *q* were inversely correlated with changes in paired-pulse ratio, as expected ([Figure 1—figure supplement 2C,D](https://elifesciences.org/articles/09457/figures#fig1s2)). Taken together, these results lend experimental support to our binomial-distribution-based approach for extracting *P* and *q* to tune changes in the pre- and postsynaptic modifications of our unified STDP model ([Figure 1D,E](https://elifesciences.org/articles/9457#fig1)).

#### Analysis of in vivo data

[Request a detailed protocol](https://bio-protocol.org/eLIFErap09457?item=s1-5)

We extracted the effective *P* and *q* from the in vivo data obtained by [Froemke et al. (2013)](https://elifesciences.org/articles/9457#bib15). Again using a binomial model, we obtained estimators for their variability measure given by *v* = *q* (1 − *P*) and the mean by *μ* = *PqN*. To ease comparison with our simulations we set the initial *P* to the same initial condition used in our simulations *P* = 0.5 ([Costa et al., 2013](https://elifesciences.org/articles/9457#bib11)). We then obtained the initial $<math id="inf15"><mrow><mi>N</mi><mo>=</mo><mfrac><mrow><mo>|</mo><mi>μ</mi><mo>|</mo></mrow><mrow><mi>q</mi><mi>P</mi></mrow></mfrac></mrow></math>$ and the initial $<math id="inf16"><mrow><mi>q</mi><mo>=</mo><mfrac><mi>v</mi><mrow><mrow><mo>(</mo><mrow><mn>1</mn><mo>−</mo><mi>P</mi></mrow><mo>)</mo></mrow></mrow></mfrac></mrow></math>$. For the after pairing data we allowed both pre- and postsynaptic factors *P* and *q* to change, while *N* was fixed to the values extracted before pairing ([Bolshakov et al., 1997](https://elifesciences.org/articles/9457#bib5)). The estimations after learning were obtained as $<math id="inf17"><mrow><mi>q</mi><mo>=</mo><mi>v</mi><mo>+</mo><mfrac><mrow><mo>|</mo><mi>μ</mi><mo>|</mo></mrow><mi>N</mi></mfrac></mrow></math>$ and $<math id="inf18"><mrow><mi>P</mi><mo>=</mo><mfrac><mrow><mo>|</mo><mi>μ</mi><mo>|</mo></mrow><mrow><mi>N</mi><mi>q</mi></mrow></mfrac></mrow></math>$. We used these estimators to extract *q* and *P* from measurements for both the depression experienced for the unpaired (best before pairing) receptive field position and the potentiated paired position ([Froemke et al., 2013](https://elifesciences.org/articles/9457#bib15)). After pairing, the effective *q* of the potentiated (‘on’) response increased from $<math id="inf19"><mrow><msubsup><mi>q</mi><mrow><mtext>before</mtext></mrow><mrow><mtext>on</mtext></mrow></msubsup><mo>=</mo><mn>23</mn><mo>.</mo><mn>3</mn><mtext> pA</mtext></mrow></math>$ to $<math id="inf20"><mrow><msubsup><mi>q</mi><mrow><mtext>after</mtext></mrow><mrow><mtext>on</mtext></mrow></msubsup><mo>=</mo><mn>27</mn><mo>.</mo><mn>1</mn><mtext> pA</mtext></mrow></math>$ (+16.3%), while *P* increased from $<math id="inf21"><mrow><msubsup><mi>P</mi><mrow><mtext>before</mtext></mrow><mrow><mtext>on</mtext></mrow></msubsup><mo>=</mo><mn>0</mn><mo>.</mo><mn>5</mn></mrow></math>$ to $<math id="inf22"><mrow><msubsup><mi>P</mi><mrow><mtext>after</mtext></mrow><mrow><mtext>on</mtext></mrow></msubsup><mo>=</mo><mn>0</mn><mo>.</mo><mn>73</mn></mrow></math>$ (+46%). Responses that were depressed (‘off’), typically the original best frequency, yielded no statistically significant change in $<math id="inf23"><mrow><msubsup><mi>q</mi><mrow><mtext>before</mtext></mrow><mrow><mtext>off</mtext></mrow></msubsup></mrow></math>$, while $<math id="inf24"><mrow><msubsup><mi>P</mi><mrow><mtext>before</mtext></mrow><mrow><mtext>off</mtext></mrow></msubsup><mo>=</mo><mn>0</mn><mo>.</mo><mn>5</mn></mrow></math>$ and $<math id="inf25"><mrow><msubsup><mi>P</mi><mrow><mtext>after</mtext></mrow><mrow><mtext>off</mtext></mrow></msubsup><mo>=</mo><mn>0</mn><mo>.</mo><mn>40</mn></mrow></math>$ (−20%) ([Figures 2](https://elifesciences.org/articles/9457#fig2), [Figure 2—figure supplement 1](https://elifesciences.org/articles/09457/figures#fig2s1) and [Figure 2—figure supplement 3](https://elifesciences.org/articles/09457/figures#fig2s3)). To ease comparison with the postsynaptic factor in the simulations we scaled the experimentally obtained *q* such that before plasticity it was 1. We compared models where we allowed both *P* and *q* to change or only one of them, the lower variability estimation error was obtained by the one where both factors change ([Figure 2—figure supplement 3E](https://elifesciences.org/articles/09457/figures#fig2s3)). The estimation error was calculated as $<math id="inf26"><mfrac><mn>1</mn><mi>N</mi></mfrac><msubsup><msup><mo>∑</mo><mtext></mtext></msup><mi>i</mi><mi>N</mi></msubsup><msup><mrow><mo>(</mo><msubsup><mi>v</mi><mtext>real</mtext><mi>i</mi></msubsup><mo>−</mo><msubsup><mi>v</mi><mtext>estimated</mtext><mi>i</mi></msubsup><mo>)</mo></mrow><mn>2</mn></msup></math>$, where *N* is the number of data points.

#### Synaptic signal detection

[Request a detailed protocol](https://bio-protocol.org/eLIFErap09457?item=s1-6)

We calculated the SNR of a synaptic response defined here by a random variable *s*, amidst additive background noise defined by the random variable *n* as follows

(22) $<math><msub><mtext>SNR</mtext><mtext>syn</mtext></msub><mo>=</mo><mn>2</mn><mfrac><msup><mrow><mo>(</mo><mrow><mo>⟨</mo><mi>s</mi><mo>⟩</mo></mrow><mo>−</mo><mrow><mo>⟨</mo><mi>n</mi><mo>⟩</mo></mrow><mo>)</mo></mrow><mn>2</mn></msup><mrow><msubsup><mi>σ</mi><mi>s</mi><mn>2</mn></msubsup><mo>+</mo><msubsup><mi>σ</mi><mi>n</mi><mn>2</mn></msubsup></mrow></mfrac><mo>,</mo></math>$

It is assumed that $<math id="inf27"><mrow><mi>n</mi><mo>∼</mo><mi mathvariant="script">𝒩</mi><mrow><mo>(</mo><mrow><mn>0</mn><mo>,</mo><msubsup><mi>σ</mi><mi>n</mi><mn>2</mn></msubsup></mrow><mo>)</mo></mrow></mrow></math>$ and we also used the Gaussian approximation to the binomial release model specified above, $<math id="inf28"><mrow><mi>s</mi><mo>∼</mo><mi mathvariant="script">𝒩</mi><mrow><mo>(</mo><mrow><mi>P</mi><mi>q</mi><mi>N</mi><mo>,</mo><msup><mi>q</mi><mn>2</mn></msup><mi>N</mi><mi>P</mi><mrow><mo>(</mo><mrow><mn>1</mn><mo>−</mo><mi>P</mi></mrow><mo>)</mo></mrow><mo>+</mo><msubsup><mi>σ</mi><mi>n</mi><mn>2</mn></msubsup></mrow><mo>)</mo></mrow></mrow></math>$, from which follows the SNR of the first postsynaptic response

(23) $<math><msub><mtext>SNR</mtext><mtext>syn</mtext></msub><mo>=</mo><mn>2</mn><mfrac><msup><mrow><mo>(</mo><mi>P</mi><mi>q</mi><mi>N</mi><mo>)</mo></mrow><mn>2</mn></msup><mrow><msup><mi>q</mi><mn>2</mn></msup><mi>N</mi><mi>P</mi><mrow><mo>(</mo><mn>1</mn><mo>−</mo><mi>P</mi><mo>)</mo></mrow><mo>+</mo><mn>2</mn><msubsup><mi>σ</mi><mi>n</mi><mn>2</mn></msubsup></mrow></mfrac><mo>.</mo></math>$

In [Figure 2](https://elifesciences.org/articles/9457#fig2), we used $<math id="inf29"><mrow><msubsup><mi>σ</mi><mi>n</mi><mn>2</mn></msubsup><mo>=</mo><mn>0</mn><mo>.</mo><mn>5</mn></mrow></math>$. Variance of the *k*\-th postsynaptic response is given by $<math id="inf30"><mrow><msubsup><mi>σ</mi><mrow><msup><mrow><mtext>syn</mtext></mrow><mtext>k</mtext></msup></mrow><mn>2</mn></msubsup><mo>=</mo><msup><mi>q</mi><mn>2</mn></msup><mi>N</mi><msub><mi>r</mi><mi>k</mi></msub><msub><mi>p</mi><mi>k</mi></msub><mrow><mo>(</mo><mrow><mn>1</mn><mo>−</mo><msub><mi>r</mi><mi>k</mi></msub><msub><mi>p</mi><mi>k</mi></msub></mrow><mo>)</mo></mrow></mrow></math>$ ([Figure 2—figure supplement 2A](https://elifesciences.org/articles/09457/figures#fig2s2)). The SNR of the *k*\-th postsynaptic response is

(24) $<math><msubsup><mtext>SNR</mtext><mtext>syn</mtext><mi>k</mi></msubsup><mo>=</mo><mn>2</mn><mfrac><msup><mrow><mo>(</mo><msub><mi>r</mi><mi>k</mi></msub><msub><mi>p</mi><mi>k</mi></msub><mi>q</mi><mi>N</mi><mo>)</mo></mrow><mn>2</mn></msup><mrow><msup><mi>q</mi><mn>2</mn></msup><mi>N</mi><msub><mi>r</mi><mi>k</mi></msub><msub><mi>p</mi><mi>k</mi></msub><mrow><mo>(</mo><mn>1</mn><mo>−</mo><msub><mi>r</mi><mi>k</mi></msub><msub><mi>p</mi><mi>k</mi></msub><mo>)</mo></mrow><mo>+</mo><mn>2</mn><msubsup><mi>σ</mi><mi>n</mi><mn>2</mn></msubsup></mrow></mfrac><mo>,</mo></math>$

where *p**k* and *r**k* are given by [Equations 15, 16](https://elifesciences.org/articles/9457#equ15), respectively. The SNR of the sum of the first *K* responses, evoked at a given presynaptic firing rate *ρ* therefore equals

(25) $<math><mstyle displaystyle="true" scriptlevel="0"><mrow><msubsup><mtext>SNR</mtext><mrow><mtext>syn</mtext></mrow><mrow><mi>ρ</mi></mrow></msubsup><mo>=</mo><mn>2</mn><mfrac><msup><mrow><mo>(</mo><mrow><msubsup><mo movablelimits="false">∑</mo><mrow><mi>k</mi><mo>=</mo><mn>0</mn></mrow><mrow><mi>K</mi><mo>−</mo><mn>1</mn></mrow></msubsup><mrow><msub><mi>r</mi><mi>k</mi></msub><msub><mi>p</mi><mi>k</mi></msub><mi>q</mi><mi>N</mi></mrow></mrow><mo>)</mo></mrow><mn>2</mn></msup><mrow><msubsup><mo movablelimits="false">∑</mo><mrow><mi>k</mi><mo>=</mo><mn>0</mn></mrow><mrow><mi>K</mi><mo>−</mo><mn>1</mn></mrow></msubsup><mrow><msup><mi>q</mi><mn>2</mn></msup><mi>N</mi><msub><mi>r</mi><mi>k</mi></msub><msub><mi>p</mi><mi>k</mi></msub><mo stretchy="false">(</mo><mn>1</mn><mo>−</mo><msub><mi>r</mi><mi>k</mi></msub><msub><mi>p</mi><mi>k</mi></msub><mo stretchy="false">)</mo><mo>+</mo><mn>2</mn><msubsup><mo movablelimits="false">∑</mo><mrow><mi>k</mi><mo>=</mo><mn>0</mn></mrow><mrow><mi>K</mi><mo>−</mo><mn>1</mn></mrow></msubsup><mrow><msubsup><mi>σ</mi><mrow><mi>n</mi></mrow><mrow><mn>2</mn></mrow></msubsup></mrow></mrow></mrow></mfrac><mo>.</mo></mrow></mstyle></math>$

After unified STDP the first response has a higher amplitude and the second one a much lower amplitude due to synaptic depression. Combined with the background noise, the SNR can drop when the second or further responses are included. However, the SNR of the summed response will always be larger than when only postsynaptic modifications are made (see [Figure 2—figure supplement 2B](https://elifesciences.org/articles/09457/figures#fig2s2)). This holds for any frequency, [Figure 2—figure supplement 2C](https://elifesciences.org/articles/09457/figures#fig2s2) and carries over to an information theoretic analysis of the response, [Figure 2—figure supplement 2D](https://elifesciences.org/articles/09457/figures#fig2s2).

Next, we used ROC analysis to compute the *false alarm* and *detection* probability of the first postsynaptic response

(26) $<math><mrow><msub><mi>p</mi><mrow><mtext>false alarm</mtext></mrow></msub><mo>=</mo><msup><mstyle displaystyle="true"><mrow><mstyle displaystyle="true"><mrow><msubsup><mo>∫</mo><mi>T</mi><mrow><mo>+</mo><mi>∞</mi></mrow></msubsup><mrow><msub><mi>P</mi><mi>n</mi></msub><mrow><mo>(</mo><mi>r</mi><mo>)</mo></mrow><mi>d</mi><mi>r</mi><mo>=</mo><mfrac><mn>1</mn><mn>2</mn></mfrac><mtext>erfc</mtext><mrow><mo>(</mo><mrow><mfrac><mi>T</mi><mrow><msqrt><mrow><mn>2</mn><msubsup><mi>σ</mi><mi>n</mi><mn>2</mn></msubsup></mrow></msqrt></mrow></mfrac></mrow><mo>)</mo></mrow></mrow></mrow></mstyle></mrow></mstyle><mtext></mtext></msup><mo>,</mo></mrow></math>$

(27) $<math><mrow><msub><mi>p</mi><mrow><mtext>detection</mtext></mrow></msub><mo>=</mo><msup><mstyle displaystyle="true"><mrow><mstyle displaystyle="true"><mrow><msubsup><mo>∫</mo><mi>T</mi><mrow><mo>+</mo><mi>∞</mi></mrow></msubsup><mrow><msub><mi>P</mi><mi>s</mi></msub><mrow><mo>(</mo><mi>r</mi><mo>)</mo></mrow><mi>d</mi><mi>r</mi><mo>=</mo><mfrac><mn>1</mn><mn>2</mn></mfrac><mtext>erfc</mtext><mrow><mo>(</mo><mrow><mfrac><mrow><mi>T</mi><mo>−</mo><mi>P</mi><mi>q</mi><mi>N</mi></mrow><mrow><msqrt><mrow><mn>2</mn><msup><mi>q</mi><mn>2</mn></msup><mi>N</mi><mi>P</mi><mrow><mo>(</mo><mrow><mn>1</mn><mo>−</mo><mi>P</mi></mrow><mo>)</mo></mrow><mo>+</mo><msubsup><mi>σ</mi><mi>n</mi><mn>2</mn></msubsup></mrow></msqrt></mrow></mfrac></mrow><mo>)</mo></mrow></mrow></mrow></mstyle></mrow></mstyle><mtext></mtext></msup><mo>.</mo></mrow></math>$

where *T* is the discrimination threshold, and erfc is the complementary error function defined as $<math id="inf31"><mrow><mtext>erfc</mtext><mrow><mo>(</mo><mi>x</mi><mo>)</mo></mrow><mo>=</mo><mfrac><mn>2</mn><mrow><msqrt><mi>π</mi></msqrt></mrow></mfrac><mstyle displaystyle="true"><mrow><msubsup><mo>∫</mo><mi>x</mi><mi>∞</mi></msubsup><mrow><msup><mi>e</mi><mrow><mo>−</mo><msup><mi>t</mi><mn>2</mn></msup></mrow></msup><mi>d</mi><mi>t</mi></mrow></mrow></mstyle></mrow></math>$. To assess the overall discriminability, we used *p*discrimination, which is the area under the ROC curve (AUC). The AUC was computed by integrating over the ROC curve using the trapezoid method (see [Figure 2D](https://elifesciences.org/articles/9457#fig2)). Given that *N* is a simple constant we set it to 1, unless otherwise stated (see data inference above).

#### Receptive field development

[Request a detailed protocol](https://bio-protocol.org/eLIFErap09457?item=s1-7)

For the receptive field development simulations, we used a feedforward network with 100 presynaptic neurons *j* with Poisson statistics and a single integrate-and-fire postsynaptic neuron. The postsynaptic neuron was modelled as an adaptive exponential integrate-and-fire neuron model ([Brette and Gerstner, 2005](https://elifesciences.org/articles/9457#bib6)). Model parameters were as reported in [Brette and Gerstner (2005)](https://elifesciences.org/articles/9457#bib6); [Badel et al. (2008)](https://elifesciences.org/articles/9457#bib2) and synapses were modelled as input currents. The firing rate of the presynaptic Poisson neurons was modelled using a Gaussian profile, defined as

(28) $<math><mrow><mi>ρ</mi><mrow><mo>(</mo><mrow><mi>j</mi><mo>;</mo><mi>p</mi><mo>,</mo><mi>σ</mi></mrow><mo>)</mo></mrow><mo>=</mo><msub><mi>ρ</mi><mrow><mtext>min</mtext></mrow></msub><mo>+</mo><mrow><mo>(</mo><mrow><msub><mi>ρ</mi><mrow><mtext>max</mtext></mrow></msub><mo>−</mo><msub><mi>ρ</mi><mrow><mtext>min</mtext></mrow></msub></mrow><mo>)</mo></mrow><msup><mtext>e</mtext><mrow><mfrac><mrow><mo>−</mo><msup><mrow><mrow><mo>(</mo><mrow><mi>j</mi><mo>−</mo><mi>p</mi></mrow><mo>)</mo></mrow></mrow><mn>2</mn></msup></mrow><mrow><mn>2</mn><msup><mi>σ</mi><mn>2</mn></msup></mrow></mfrac></mrow></msup><mo>.</mo></mrow></math>$

where *ρ* is the rate in the Poisson neuron model *j*, *p* the input position for which the rate is maximal, and *σ* = 5 Hz the distribution spread. *ρ**max* and *ρ**min* are the maximum and minimum rates, and were set to *ρ*max = 50 Hz and *ρ*min = 3 Hz. We scaled *d*−, *d*+ and *c*+ by a factor 0.15 to yield a smoother receptive field development. *q* was bounded between 0 nA and 20 nA, so that the synaptic input is appropriately scaled for the neuron model used. The network was simulated for 100 s to achieve convergence. For the memory savings experiment, we interleaved two receptive field positions. Results for receptive development and memory savings were averaged over 10 runs. The response of the postsynaptic neuron ([Figure 3C](https://elifesciences.org/articles/9457#fig3)) was assessed by presenting each stimulus alone with long-term synaptic plasticity inactive. Receptive field simulations were implemented in simulator Brian 1.41 ([Goodman and Brette, 2008](https://elifesciences.org/articles/9457#bib19)). Code for running and plotting the savings experiment is available online ([http://modeldb.yale.edu/184487](http://modeldb.yale.edu/184487)).

#### Statistical comparison

[Request a detailed protocol](https://bio-protocol.org/eLIFErap09457?item=s1-8)

Results are reported as mean ± SEM. Statistical comparisons were made with Student's *t*\-test for equal means, if data was normally distributed as assessed using Kolmogorov–Smirnov test, Mann–Whitney U non-parametric test was used otherwise. For multiple comparisons we applied ANOVA or Kruskal–Wallis test for normally or non-normally distributed data, respectively. For correlation analysis the Spearman's coefficient was used together with one-tailed Student's *t*\-test. Significance levels are \*p < 0.05, \*\*p < 0.01, and \*\*\*p < 0.001.

[

## Appendix 1

](https://elifesciences.org/articles/9457#)

### Comparison between unified pre- and postsynaptic STDP model, and triplet STDP model ([Pfister and Gerstner, 2006](https://elifesciences.org/articles/9457#bib39))

Our model has some similarities with the triplet-STDP model introduced in [Pfister and Gerstner (2006)](https://elifesciences.org/articles/9457#bib39), however note that the triplet model does not distinguish between pre- and postsynaptic components of expression. The triplet model is defined by the following components: presynaptic traces, *x*1 and *x*2, and postsynaptic traces *y*1 and *y*2. The weight changes are modelled as a combination of pair and triplet components (*full Triplet* model) as follows

(29) $<math><mrow><mtext>Δ</mtext><msup><mi>w</mi><mo>−</mo></msup><mo>=</mo><mo>−</mo><mi>X</mi><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow><msub><mi>y</mi><mn>1</mn></msub><mrow><mo>[</mo><mrow><msubsup><mi>A</mi><mn>2</mn><mo>−</mo></msubsup><mo>+</mo><msubsup><mi>A</mi><mn>3</mn><mo>−</mo></msubsup><mtext> </mtext><msub><mi>x</mi><mn>2</mn></msub><mrow><mo>(</mo><mrow><mi>t</mi><mo>−</mo><mi mathvariant="italic">ϵ</mi></mrow><mo>)</mo></mrow></mrow><mo>]</mo></mrow><mo>,</mo></mrow></math>$

(30) $<math><mrow><mtext>Δ</mtext><msup><mi>w</mi><mo>+</mo></msup><mo>=</mo><mi>Y</mi><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow><msub><mi>x</mi><mn>1</mn></msub><mrow><mo>[</mo><mrow><msubsup><mi>A</mi><mn>2</mn><mo>+</mo></msubsup><mo>+</mo><msubsup><mi>A</mi><mn>3</mn><mo>+</mo></msubsup><mtext> </mtext><msub><mi>y</mi><mn>2</mn></msub><mrow><mo>(</mo><mrow><mi>t</mi><mo>−</mo><mi mathvariant="italic">ϵ</mi></mrow><mo>)</mo></mrow></mrow><mo>]</mo></mrow><mo>.</mo></mrow></math>$

However, to fit the intra-pairing frequency observed in the young rat visual cortex (VC) ([Sjöström et al., 2001](https://elifesciences.org/articles/9457#bib43)), a reduced model ($<math id="inf32"><mrow><msubsup><mi>A</mi><mn>3</mn><mo>−</mo></msubsup><mo>=</mo><mn>0</mn></mrow></math>$ and $<math id="inf33"><mrow><msubsup><mi>A</mi><mn>2</mn><mo>+</mo></msubsup><mo>=</mo><mn>0</mn></mrow></math>$) was found to be sufficient (*minimal VC Triplet*) ([Pfister and Gerstner, 2006](https://elifesciences.org/articles/9457#bib39))

(31) $<math><mrow><mtext>Δ</mtext><msup><mi>w</mi><mo>−</mo></msup><mo>=</mo><mo>−</mo><mi>X</mi><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow><msubsup><mi>A</mi><mn>2</mn><mo>−</mo></msubsup><mtext> </mtext><msub><mi>y</mi><mn>1</mn></msub><mo>,</mo></mrow></math>$

(32) $<math><mrow><mtext>Δ</mtext><msup><mi>w</mi><mo>+</mo></msup><mo>=</mo><mi>Y</mi><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow><msubsup><mi>A</mi><mn>3</mn><mo>+</mo></msubsup><mtext> </mtext><msub><mi>x</mi><mn>1</mn></msub><msub><mi>y</mi><mn>2</mn></msub><mrow><mo>(</mo><mrow><mi>t</mi><mo>−</mo><mi mathvariant="italic">ϵ</mi></mrow><mo>)</mo></mrow><mo>.</mo></mrow></math>$

Moreover, another slightly more complex model ($<math id="inf34"><mrow><msubsup><mi>A</mi><mn>3</mn><mo>−</mo></msubsup><mo>=</mo><mn>0</mn></mrow></math>$) was found to be able to capture triplet and quadruplet experiments performed in the hippocampus (HC) ([Wang et al., 2005](https://elifesciences.org/articles/9457#bib54)) (*minimal HC Triplet*)

(33) $<math><mrow><mtext>Δ</mtext><msup><mi>w</mi><mo>−</mo></msup><mo>=</mo><mo>−</mo><mi>X</mi><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow><msubsup><mi>A</mi><mn>2</mn><mo>−</mo></msubsup><msub><mi>y</mi><mn>1</mn></msub><mo>,</mo></mrow></math>$

(34) $<math><mrow><mtext>Δ</mtext><msup><mi>w</mi><mo>+</mo></msup><mo>=</mo><mi>Y</mi><mrow><mo>(</mo><mi>t</mi><mo>)</mo></mrow><msub><mi>x</mi><mn>1</mn></msub><mrow><mo>[</mo><mrow><msubsup><mi>A</mi><mn>2</mn><mo>+</mo></msubsup><mo>+</mo><msubsup><mi>A</mi><mn>3</mn><mo>+</mo></msubsup><msub><mi>y</mi><mn>2</mn></msub><mrow><mo>(</mo><mrow><mi>t</mi><mo>−</mo><mi mathvariant="italic">ϵ</mi></mrow><mo>)</mo></mrow></mrow><mo>]</mo></mrow><mo>.</mo></mrow></math>$

Interestingly, our model also has two LTP and one LTD components, that can be mapped onto the *minimal HC Triplet* (see [Table 2](https://elifesciences.org/articles/9457#tbl2)). However, to capture the pharmacological blockade experiments reported in [Sjöström et al. (2007)](https://elifesciences.org/articles/9457#bib46), we needed three triplets, rather than one triplet and two doublets as in the *minimal HC Triplet* model.

[

## Data availability

](https://elifesciences.org/articles/9457#)

The following data sets were generated

[

## References

](https://elifesciences.org/articles/9457#)

[

## Decision letter

](https://elifesciences.org/articles/9457#)

Thank you for submitting your work entitled “Unified pre- and postsynaptic long-term plasticity enables reliable and flexible learning” for peer review at *eLife*. Your submission has been favorably evaluated by Eve Marder (Senior Editor) and three reviewers, one of whom is a member of our Board of Reviewing Editors.

The reviewers have discussed the reviews with one another and the Reviewing Editor has drafted this decision to help you prepare a revised submission.

All three reviewers found aspects of the improvement in SNR confusing. I think this can be remedied with textual changes not requiring additional experiments or simulations (although if additional simulations – e.g. addressing Reviewer #3's concerns about frequency – will help to clarify, these could presumably be included). All three reviews are included below in the hopes that this will aid in clarifying the manuscript.

*Reviewer #1:*

This is a carefully done, compact paper with a crisp message that offers a potential solution to an important problem in neuroscience. Although there is now broad agreement that pre- and postsynaptic plasticity mechanisms can coexist at many central synapses, the functional benefit of this is unclear. The authors here adapt prior models of spike-timing-dependent plasticity to take account of the experimentally determined properties of pre- and postsynaptic expression mechanisms for plasticity. They show two functional benefits. First, the two mechanisms better account for observed improvements in sensory discrimination with learning and second, the dual mechanism permits much more rapid relearning when the stimuli being learned change with time.

I have no major concerns.

*Reviewer #2:*

It is really good to see a model of this detail and rigor combining the pre and post-synaptic aspects of plasticity and to see that we have finally arrived at a point where it is accepted that pre and post-synaptic elements show plasticity. My comments are going to be fairly minor but I hope that the authors will make some effort to tackle them because it will probably help communicate the ideas.

The first point is that the model seeks to explain the advantages of presynaptic plasticity. One of these is the decrease in variance in developing receptive fields another is retained information or savings on reversal of plasticity. Unfortunately, having raked through the formulae a few times, I cannot see where this comes from. In [Figure 3](https://elifesciences.org/articles/9457#fig3), the relearning occurs more quickly because the post-synaptic factor decays slowly. Can the authors explain in more detail why presynaptic plasticity improves relearning? Also, could it not (theoretically) be achieved another way, say by increasing the duration of the post-synaptic factor? I am still missing what is unique about the disposition of the presynaptic plasticity.

I am not disputing the premise, however. It may well be that the slower turnover of presynaptic terminals compared to spines allows faster relearning. I believe that Finnerty and colleagues have done some work on this and they should probably be mentioned in this paper.

The second point is that the main body of the paper seems to be over very quickly. I was left searching for more text. There are several points that could be more fully discussed, including the elements that are explicitly missing from the model and what the impact might be. For example, how does inhibition and plasticity of inhibition impact the outcome and how might the time course of structural plasticity modify the model. On the second point, the Matsuzaki reference deals with structure and synaptic weight post-synaptically but not pre-synaptically. It would also be useful to hear how the model might fit different structures - would more presynaptic plasticity be warranted in layer 5 pyramidal cells than in hippocampus for example?

*Reviewer #3:*

This paper presents a theoretical model for STDP that incorporates both a pre- and post-synaptic expression locus. To date the vast majority of models have focused on implementations of LTP and LTD that simply scale the value of the synaptic weight, but do not alter short-term synaptic plasticity-thus altering the temporal profile of EPSPs. Importantly the model is based on, and captures, the experimental data which strongly suggests that there are pre- and postsynaptic expression mechanisms. Together the paper is highly novel and provides important data-based insights to our understanding of synaptic plasticity.

It is very interesting that the rule results in better discrimination. What is not clear is why? That is, why does a higher P value provide improve SNR? Yes, the first presynaptic spike generates a large reliable EPSP, but the subsequent spikes are less reliable and depressed. The SNR and ROC analyses were analytical, but I'm struggling to understand how these analyses can capture the true SNR and discriminability without taking into account the firing rate of the presynaptic units. Discriminability must depend in part of on the frequency of the Poisson inputs (and the D and F time constants)-but as it stands the analysis is based on the probabilistic nature of P, that is, essentially only for the first spike. Either I'm missing something, or an analysis based on the actual simulations (which take into account the timing of the spikes) should be performed. This is probably a minor issue, however, as [Figure 3C](https://elifesciences.org/articles/9457#fig3) makes it clear the discriminability based on firing rate is excellent.

Based on [Figure 3A](https://elifesciences.org/articles/9457#fig3), P seems to saturate at 1, meaning that there is little or no release for the next 200 ms. This is one reason the SNR calculation may be misleading. It would be useful to show postsynaptic trace segments during stimulation as part of this figure.

I think some readers, particularly, those accustomed to the hippocampal field, will be unfamiliar with the strong evidence that there are presynaptic components to STDP. So I think it is important to strengthen their argument a bit, and perhaps mention that, these studies are based on neocortical data, and that there is likely a difference between hippocampal and neocortical STDP.

[https://doi.org/10.7554/eLife.09457.016](https://doi.org/10.7554/eLife.09457.016)

[

## Author response

](https://elifesciences.org/articles/9457#)

*All three reviewers found aspects of the improvement in SNR confusing. I think this can be remedied with textual changes not requiring additional experiments or simulations (although if additional simulations – e.g. addressing Reviewer #3's concerns about frequency – will help to clarify, these could presumably be included). All three reviews are included below in the hopes that this will aid in clarifying the manuscript*.

These are important points. We have modified the manuscript considerably to address this. First, we have now clarified how the SNR is calculated. Briefly, it is the ratio between the synaptic signal (i.e. the first EPSP) and background noise. We have also further clarified why presynaptic plasticity is important in improving the SNR.

Additionally, in response to Reviewer 3, we have extended our SNR analysis for trains of input. Finally, we also calculated the information transmission at different frequencies for dynamics synapses, as proposed by [Fuhrmann et al. 2002](https://elifesciences.org/articles/9457#bib17). This is part of the new [Figure 2–figure supplement 3](https://elifesciences.org/articles/09457/figures#fig2s3), which shows that SNR and information transmission increases across different frequencies, when both pre- and postsynaptic plasticity occurs, but not when only postsynaptic plasticity occurs.

Reviewer #2:

*The first point is that the model seeks to explain the advantages of presynaptic plasticity. One of these is the decrease in variance in developing receptive fields another is retained information or savings on reversal of plasticity. Unfortunately, having raked through the formulae a few times, I cannot see where this comes from*.

We have tried to improve the intuition behind both sets of results. For the change in variance this is now clarified. For the savings result, we clarified the explanation of our results.

*In*[*Figure 3*](https://elifesciences.org/articles/9457#fig3)*, the relearning occurs more quickly because the post-synaptic factor decays slowly. Can the authors explain in more detail why presynaptic plasticity improves relearning? Also, could it not (theoretically) be achieved another way, say by increasing the duration of the post-synaptic factor? I am still missing what is unique about the disposition of the presynaptic plasticity*.

Yes, the rapid relearning occurs because the postsynaptic weight decay is slower than the presynaptic modifications. In theory this could be achieved by other mechanisms; however, our model was in fact inspired by the experimental observation that the presynaptic modifications are bidirectional (expressing both LTP and LTD) while the postsynaptic modifications are not (and express only LTP), at least on the timescale of whole-cell recording experiments. We have now clarified this further. Interestingly, there is some evidence for such a reversal in the cerebellum and different locus expression pattern in the hippocampus (see Discussion).

*I am not disputing the premise, however. It may well be that the slower turnover of presynaptic terminals compared to spines allows faster relearning. I believe that Finnerty and colleagues have done some work on this and they should probably be mentioned in this paper*.

We have now cited Cheetham et al. (Cereb Cortex 2014) and Finnerty et al. (Nature 1999) in the Discussion, mentioning that changes in experience can affect both pre- and postsynaptic structures, which appear to be consistent with our model, although perhaps with different time constants.

*The second point is that the main body of the paper seems to be over very quickly. I was left searching for more text. There are several points that could be more fully discussed, including the elements that are explicitly missing from the model and what the impact might be. For example, how does inhibition and plasticity of inhibition impact the outcome and how might the time course of structural plasticity modify the model. On the second point, the Matsuzaki reference deals with structure and synaptic weight post-synaptically but not pre-synaptically*.

The [Hofer et al. 2008](https://elifesciences.org/articles/9457#bib23) paper only looks at postsynaptic structure, but their results are consistent with our predictions (i.e. that the postsynapse should outlast input changes). Given the Matsuzaki results, our results might explain their results on the postsynaptic side. Our model further predicts that the presynapse should gate the input, which might be reflected in the structure of the presynapse. However, to the best of our knowledge, this has not been tested before. We have added a reference to the review by Holtmaat, Nature Reviews Neuroscience, 2009.

*It would also be useful to hear how the model might fit different structures - would more presynaptic plasticity be warranted in layer 5 pyramidal cells than in hippocampus for example?*

Thank you for pointing this out. We have added a discussion on this. Briefly, in analogy with the triplet model results from [Pfister et al. 2006](https://elifesciences.org/articles/9457#bib39), we argue that our modeling framework should apply to those brain regions as well. However, model parameters will be different, the consequences of which will be difficult to know without detailed studies.

Reviewer #3:

*It is very interesting that the rule results in better discrimination. What is not clear is why? That is, why does a higher P value provide improve SNR? Yes, the first presynaptic spike generates a large reliable EPSP, but the subsequent spikes are less reliable and depressed. The SNR and ROC analyses were analytical, but I'm struggling to understand how these analyses can capture the true SNR and discriminability without taking into account the firing rate of the presynaptic units. Discriminability must depend in part of on the frequency of the Poisson inputs (and the D and F time constants)-but as it stands the analysis is based on the probabilistic nature of P, that is, essentially only for the first spike. Either I'm missing something, or an analysis based on the actual simulations (which take into account the timing of the spikes) should be performed. This is probably a minor issue, however, as*[*Figure 3C*](https://elifesciences.org/articles/9457#fig3)*makes it clear the discriminability based on firing rate is excellent*.

*Based on*[*Figure 3A*](https://elifesciences.org/articles/9457#fig3)*, P seems to saturate at 1, meaning that there is little or no release for the next 200 ms. This is one reason the SNR calculation may be misleading. It would be useful to show postsynaptic trace segments during stimulation as part of this figure*.

We thank the reviewer for highlighting this. We have now clarified that the SNR and discrimination analysis was done for the first EPSP alone. A full characterization of the information transmission requires numerous assumptions about the neural code and the input statistics. Even so, we have now included a supplement to [Figure 2–figure supplement 3](https://elifesciences.org/articles/09457/figures#fig2s3), showing how SNR and information transmission is improved by our learning rule when short-term plasticity is considered.

*I think some readers, particularly, those accustomed to the hippocampal field, will be unfamiliar with the strong evidence that there are presynaptic components to STDP. So I think it is important to strengthen their argument a bit, and perhaps mention that, these studies are based on neocortical data, and that there is likely a difference between hippocampal and neocortical STDP*.

We have now clarified this in the Discussion.

[https://doi.org/10.7554/eLife.09457.017](https://doi.org/10.7554/eLife.09457.017)

[

## Article and author information

](https://elifesciences.org/articles/9457#)

### Author details

1.  #### Rui Ponte Costa
    
    1.  Institute for Adaptive and Neural Computation, School of Informatics, University of Edinburgh, Edinburgh, United Kingdom
    2.  Neuroinformatics Doctoral Training Centre, School of Informatics, University of Edinburgh, Edinburgh, United Kingdom
    3.  The Research Institute of the McGill University Health Centre, Department of Neurology and Neurosurgery, McGill University, Montreal, Canada
    4.  Centre for Neural Circuits and Behaviour, University of Oxford, Oxford, United Kingdom
    
    ##### Contribution
    
    RPC, Conception and design, Analysis and interpretation of data, Drafting or revising the article
    
    ##### For correspondence
    
    [rui.costa@cncb.ox.ac.uk](mailto:rui.costa@cncb.ox.ac.uk)
    
    ##### Competing interests
    
    The authors declare that no competing interests exist.
    
      [![ORCID icon](https://elifesciences.org/assets/patterns/img/icons/orcid.10f6112b.png)"This ORCID iD identifies the author of this article:" 0000-0003-2595-2027](https://orcid.org/0000-0003-2595-2027)
    
2.  #### Robert C Froemke
    
    1.  Skirball Institute for Biomolecular Medicine, Departments of Otolaryngology, Neuroscience and Physiology, New York University School of Medicine, New York, United States
    2.  Center for Neural Science, New York University, New York, United States
    
    ##### Contribution
    
    RCF, Analysis and interpretation of data, Drafting or revising the article
    
    ##### Competing interests
    
    The authors declare that no competing interests exist.
    
3.  #### P Jesper Sjöström
    
    The Research Institute of the McGill University Health Centre, Department of Neurology and Neurosurgery, McGill University, Montreal, Canada
    
    ##### Contribution
    
    PJS, Co-senior author, Conception and design, Analysis and interpretation of data, Drafting or revising the article
    
    ##### Contributed equally with
    
    Mark CW van Rossum
    
    ##### Competing interests
    
    The authors declare that no competing interests exist.
    
      [![ORCID icon](https://elifesciences.org/assets/patterns/img/icons/orcid.10f6112b.png)"This ORCID iD identifies the author of this article:" 0000-0001-7085-2223](https://orcid.org/0000-0001-7085-2223)
    
4.  #### Mark CW van Rossum
    
    Institute for Adaptive and Neural Computation, School of Informatics, University of Edinburgh, Edinburgh, United Kingdom
    
    ##### Contribution
    
    MCWvR, Co-senior author, Conception and design, Analysis and interpretation of data, Drafting or revising the article
    
    ##### Contributed equally with
    
    P Jesper Sjöström
    
    ##### Competing interests
    
    The authors declare that no competing interests exist.
    
      [![ORCID icon](https://elifesciences.org/assets/patterns/img/icons/orcid.10f6112b.png)"This ORCID iD identifies the author of this article:" 0000-0001-6525-6814](https://orcid.org/0000-0001-6525-6814)
    

### Funding

#### Engineering and Physical Sciences Research Council (EP/F500385/1)

-   Rui Ponte Costa

#### Medical Research Council

-   Rui Ponte Costa

#### Biotechnology and Biological Sciences Research Council (BB/F529254/1)

-   Rui Ponte Costa

#### Fundação para a Ciência e a Tecnologia (SFRH/BD/60301/2009)

-   Rui Ponte Costa

#### National Institute on Deafness and Other Communication Disorders (DC009635)

-   Robert C Froemke

#### Albert Einstein College of Medicine of Yeshiva University (Hirschl/Weill-Caulier Career Research Award)

-   Robert C Froemke

#### Alfred P. Sloan Foundation (Sloan Research Fellowship)

-   Robert C Froemke

#### National Institute on Deafness and Other Communication Disorders (DC012557)

-   Robert C Froemke

#### European Commission (243914)

-   P Jesper Sjöström

#### Canada Foundation for Innovation (28331)

-   P Jesper Sjöström

#### Canadian Institutes of Health Research (126137)

-   P Jesper Sjöström

#### Natural Sciences and Engineering Research Council of Canada (418546-2)

-   P Jesper Sjöström

The funders had no role in study design, data collection and interpretation, or the decision to submit the work for publication.

### Acknowledgements

We thank Gary Bhumbra, Megan Carey, Claudia Clopath, Wulfram Gerstner, Matthias Hennig, Robert Legenstein, Wolfgang Maass, Miha Pelko, Jean-Pascal Pfister, Paolo Puggioni, João Sacramento, Walter Senn, Lukas Solanka, the Sjöström lab, the Vogels lab and the Center for Neural Circuits and Behaviour for useful discussions. We thank Michelle Giugliano for sharing his code to calculate synaptic information transmission with dynamic synapses.

### Reviewing Editor

1.  Sacha B Nelson, Brandeis University, United States

### Publication history

1.  Received: June 15, 2015
2.  Accepted: August 25, 2015
3.  Accepted Manuscript published: [August 26, 2015 (version 1)](https://elifesciences.org/articles/09457v1)
4.  Version of Record published: [September 29, 2015 (version 2)](https://elifesciences.org/articles/09457v2)
5.  Version of Record updated: [November 30, 2016 (version 3)](https://elifesciences.org/articles/09457v3)
6.  Version of Record updated: [June 20, 2017 (version 4)](https://elifesciences.org/articles/09457)

### Copyright

© 2015, Costa et al.

This article is distributed under the terms of the [Creative Commons Attribution License](http://creativecommons.org/licenses/by/4.0/), which permits unrestricted use and redistribution provided that the original author and source are credited.

[

## Metrics

](https://elifesciences.org/articles/9457#)

-   4,290
    
    Page views
    
-   899
    
    Downloads
    
-   32
    
    Citations
    

Article citation count generated by polling the highest count across the following sources: [Scopus](https://www.scopus.com/inward/citedby.uri?partnerID=HzOxMe3b&scp=84943744054&origin=inward), [PubMed Central](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4584257/), [Crossref](https://doi.org/10.7554/eLife.09457).

## Download links
