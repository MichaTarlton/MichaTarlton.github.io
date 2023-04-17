---
created: 2022-05-10T18:44:08 (UTC +02:00)
tags: []
source: https://www.sciencedirect.com/science/article/pii/S0959438818301028
author: Scott Waddell, Jesper Sjöström
---

# Computational roles of plastic probabilistic synapses - ScienceDirect



> ## Excerpt
> The probabilistic nature of synaptic transmission has remained enigmatic. However, recent developments have started to shed light on why the brain may…

---
[![Elsevier](https://sdfestaticassets-eu-west-1.sciencedirectassets.com/prod/14ae1d96d11fc29cfae0a45bff4a1ec56ae7a56a/image/elsevier-non-solus.png)](https://www.sciencedirect.com/journal/current-opinion-in-neurobiology "Go to Current Opinion in Neurobiology on ScienceDirect")

[![Current Opinion in Neurobiology](https://ars.els-cdn.com/content/image/1-s2.0-S0959438818X00051-cov150h.gif)](https://www.sciencedirect.com/journal/current-opinion-in-neurobiology/vol/54/suppl/C)

## Highlights

•

Computational and experimental research suggest that synapses adapt their transmission statistics during learning.

•

Optimisation of probabilistic synapses occurs jointly in presynaptic and postsynaptic terminals during [synaptic plasticity](https://www.sciencedirect.com/topics/neuroscience/synaptic-plasticity "Learn more about synaptic plasticity from ScienceDirect's AI-generated Topic Pages").

•

Recent developments in statistical learning point to a reevaluation of the function of probabilistic synapses in cortical circuits.

•

Insights on the biology of probabilistic synapses may inspire new learning algorithms.

The probabilistic nature of synaptic transmission has remained enigmatic. However, recent developments have started to shed light on why the brain may rely on probabilistic synapses. Here, we start out by reviewing experimental evidence on the specificity and plasticity of synaptic response statistics. Next, we overview different computational perspectives on the function of plastic probabilistic synapses for constrained, statistical and deep learning. We highlight that all of these views require some form of optimisation of probabilistic synapses, which has recently gained support from theoretical analysis of long-term synaptic plasticity experiments. Finally, we contrast these different computational views and propose avenues for future research. Overall, we argue that the time is ripe for a better understanding of the computational functions of probabilistic synapses.

-   [**Previous**](https://www.sciencedirect.com/science/article/pii/S0959438818300795)
-   [**Next**](https://www.sciencedirect.com/science/article/pii/S0959438818301119)

## Introduction

Animals have evolved in uncertain environments. For example, they have adapted to distinguish nutrition sources of different shapes, sizes, colours and tastes. Such perceptual uncertainty should be encoded by the brain to enable accurate decision making \[[1](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0005),[2•](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0010),[3](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0015)\]. This link between perception and decision is presumably achieved through communication between different brain areas, which ultimately relies on [synaptic transmission](https://www.sciencedirect.com/topics/neuroscience/synaptic-transmission "Learn more about synaptic transmission from ScienceDirect's AI-generated Topic Pages") \[[4](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0020),[5](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0025)\]. Synaptic transmission is inherently stochastic: a presynaptic action potential may or may not trigger [neurotransmitter release](https://www.sciencedirect.com/topics/neuroscience/neurotransmitter-release "Learn more about neurotransmitter release from ScienceDirect's AI-generated Topic Pages") that in turn binds to [postsynaptic receptors](https://www.sciencedirect.com/topics/neuroscience/postsynaptic-receptor "Learn more about postsynaptic receptors from ScienceDirect's AI-generated Topic Pages") \[[6•](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0030)\]. For synaptic transmission to successfully trigger a behavioural decision synaptic response statistics should be tuned during learning \[[4](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0020),[7](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0035),[5](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0025)\]. However, it has remained unclear exactly which aspects of probabilistic synapses should be modified during learning.

There is wide evidence of plasticity occurring at the key components that underlie synaptic transmission statistics. For example, not only does plasticity change the properties and number of postsynaptic receptors, but also the intricate presynaptic machinery responsible for stochastic neurotransmitter release \[[8](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0040),[7](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0035)\]. Because [synaptic plasticity](https://www.sciencedirect.com/topics/neuroscience/synaptic-plasticity "Learn more about synaptic plasticity from ScienceDirect's AI-generated Topic Pages") is believed to underlie learning \[[4](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0020),[5](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0025)\], this body of experimental work suggests that the brain shapes probabilistic synapses as animals adapt to the environment. This has important theoretical implications \[[9•](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0045),[10](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0050),[11••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0055),[12••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0060)\], but most computational models of learning and synaptic plasticity have considered only changes in the mean synaptic weight (e.g. \[[13](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0065), [14](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0070), [15](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0075)\]). Below we review recent experimental and theoretical developments on the plasticity and computation roles of probabilistic synapses.

## Specificity of synaptic transmission statistics

The probabilistic nature of [synaptic transmission](https://www.sciencedirect.com/topics/neuroscience/synaptic-transmission "Learn more about synaptic transmission from ScienceDirect's AI-generated Topic Pages") has been described as a binomial process \[[16](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0080),[6•](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0030),[7](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0035)\], which is parametrised by the (i) number of synaptic release sites *N*, (ii) presynaptic release probability *P**rel* and (iii) quantal amplitude *q* — proportional to the number of [postsynaptic receptors](https://www.sciencedirect.com/topics/neuroscience/postsynaptic-receptor "Learn more about postsynaptic receptors from ScienceDirect's AI-generated Topic Pages") [7](https://www.sciencedirect.com/science/article/pii/S0959438818301028#fn0005) ([Figure 1](https://www.sciencedirect.com/science/article/pii/S0959438818301028#fig0005)a-i). Together these three parameters define the statistics of synaptic responses, with mean given by *NqP*rel and variance by *Nq*2*P*rel(1 − *P*rel) ([Figure 1](https://www.sciencedirect.com/science/article/pii/S0959438818301028#fig0005)a-i).

![Figure 1](https://ars.els-cdn.com/content/image/1-s2.0-S0959438818301028-gr1.jpg)

1.  [Download : Download high-res image (680KB)](https://ars.els-cdn.com/content/image/1-s2.0-S0959438818301028-gr1_lrg.jpg "Download high-res image (680KB)")
2.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S0959438818301028-gr1.jpg "Download full-size image")

Figure 1. Specificity and plasticity of probabilistic synapses. **(a)** Throughout the brain virtually every synapse is probabilistic. (i) When a presynaptic spike (blue vertical line on the left) occurs a presynaptic vesicle (blue circles) *may* [release neurotransmitters](https://www.sciencedirect.com/topics/neuroscience/neurotransmitter-release "Learn more about release neurotransmitters from ScienceDirect's AI-generated Topic Pages") (red dots) that bind to [postsynaptic receptors](https://www.sciencedirect.com/topics/neuroscience/postsynaptic-receptor "Learn more about postsynaptic receptors from ScienceDirect's AI-generated Topic Pages") (red) which elicits a [postsynaptic potential](https://www.sciencedirect.com/topics/neuroscience/postsynaptic-potential "Learn more about postsynaptic potential from ScienceDirect's AI-generated Topic Pages") (PSP; PSPs of different amplitudes are represented by the small vertical blue lines). The key parameters that determine the statistics of probabilistic synaptic responses are the number of presynaptic release sites (*N*, groups of vesicles in blue), release probability (*P*rel, blue arrows) and quantal amplitude which is proportional to the number of postsynaptic receptors, *q*, red). This process is typically modelled as a binomial probability distribution (orange histogram, with *N* = 5, *P*rel = 0.5 and *q* = 1 for illustration), which in the limit of large *N* can be approximated as a Gaussian distribution (black line) with mean=*NqP*rel and variance=*Nq*2*P*rel(1 − *P*rel). (ii) Simplified representation of cortical circuits, with both excitatory (black) and inhibitory (purple) synapses and neuron types. Each synaptic connection is stochastic (represented as a Gaussian distribution). Two different inhibitory cell-types are represented: [somatostatin](https://www.sciencedirect.com/topics/neuroscience/somatostatin "Learn more about somatostatin from ScienceDirect's AI-generated Topic Pages") (SST, dashed green circle) and [parvalbumin](https://www.sciencedirect.com/topics/neuroscience/parvalbumin "Learn more about parvalbumin from ScienceDirect's AI-generated Topic Pages") (PV, black circle); here these two separate inhibitory cell-types are represented as overlapping circles for simplicity. Note that different connections exhibit statistics of different means and variances (see main text for more details). **(b)** Long-term plasticity of probabilistic synapses. (i) Different induction protocols have been shown to trigger changes in the probability of postsynaptic responses. Schematic on the left represents presynaptic and postsynaptic spikes in a spike-timing-dependent plasticity protocol, which depending on the timing between presynaptic and postsynaptic spikes (Δ*t*) as well as the inter-spike interval (ISI) may lead to long-term potentiation (LTP) or depression (LTD). This in turn changes not only the mean synaptic response, but also its variance. (ii) Modifications to probabilistic synapses during plasticity are known to rely on specific retrograde (e.g. [endocannabinoids](https://www.sciencedirect.com/topics/neuroscience/endocannabinoids "Learn more about endocannabinoids from ScienceDirect's AI-generated Topic Pages") (eCB) and [nitric oxide](https://www.sciencedirect.com/topics/neuroscience/nitric-oxide "Learn more about nitric oxide from ScienceDirect's AI-generated Topic Pages") (NO)) and anterograde signals (glutamate (Glu)). (iii) Behavioural outcomes (e.g. reward) may rely on [neuromodulation](https://www.sciencedirect.com/topics/neuroscience/neuromodulation "Learn more about neuromodulation from ScienceDirect's AI-generated Topic Pages") (e.g. Dopamine) to regulate plasticity at probabilistic synapses.

The exact mean and variance of synaptic transmission depends on where the synapse is located. In cortical circuits the statistics (e.g. means and variances) of synaptic responses exhibit a high degree of variability that depends on cell-type \[[17](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0085)\], connection-type \[[17](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0085), [18](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0090), [19](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0095)\], layer \[[17](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0085),[20](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0100)\], brain area \[[21](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0105)\], age \[[22](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0110)\], and even species \[[23](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0115)\]. For example, excitatory synapses from thalamic projections onto layer-4 [granule cells](https://www.sciencedirect.com/topics/neuroscience/granule-cell "Learn more about granule cells from ScienceDirect's AI-generated Topic Pages") are more reliable \[[24](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0120)\] than synapses between layer-5 [pyramidal cells](https://www.sciencedirect.com/topics/neuroscience/pyramidal-cell "Learn more about pyramidal cells from ScienceDirect's AI-generated Topic Pages") \[[19](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0095)\]. Remarkably, connections from pyramidal cells onto lateral inhibitory cells can also be dramatically different: synapses onto somatostatin-positive [interneurons](https://www.sciencedirect.com/topics/neuroscience/interneuron "Learn more about interneurons from ScienceDirect's AI-generated Topic Pages") cells communicate with a low basal release probability, whereas synapses onto parvalbumin-positive interneurons are stronger with higher release probability \[[18](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0090),[19](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0095)\] ([Figure 1](https://www.sciencedirect.com/science/article/pii/S0959438818301028#fig0005)a-ii). Such high specificity of probabilistic synapses suggests that they are modified during learning.

## Plasticity of probabilistic synapses

Accumulating evidence suggests that [synaptic plasticity](https://www.sciencedirect.com/topics/neuroscience/synaptic-plasticity "Learn more about synaptic plasticity from ScienceDirect's AI-generated Topic Pages") underlies learning in the brain \[[4](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0020),[5](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0025)\]. Synaptic plasticity not only modifies the mean synaptic response, but also its variance ([Figure 1](https://www.sciencedirect.com/science/article/pii/S0959438818301028#fig0005)b). In particular, it has been shown that long-term synaptic plasticity leads to changes in both the presynapse by modifying *P*rel and the postsynapse by modifying *q* \[[7](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0035)\] ([Figure 1](https://www.sciencedirect.com/science/article/pii/S0959438818301028#fig0005)a,b-i). After a decade-long debate, today it is widely accepted that both presynaptic and postsynaptic physiology can be modified during long-term potentiation (LTP) and depression (LTD) \[[8](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0040),[7](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0035)\]. However, exactly how much each component is changed can have a dramatic impact on the [synaptic transmission](https://www.sciencedirect.com/topics/neuroscience/synaptic-transmission "Learn more about synaptic transmission from ScienceDirect's AI-generated Topic Pages") statistics \[[12••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0060)\]. Using a synaptic plasticity model tuned to presynaptic and postsynaptic plasticity Costa et al. \[[12••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0060)\] demonstrated that both mean and variance of synaptic responses are regulated both *in vitro* and in [perceptual learning](https://www.sciencedirect.com/topics/neuroscience/perceptual-learning "Learn more about perceptual learning from ScienceDirect's AI-generated Topic Pages") experiments performed in the primary auditory cortex of rats \[[25](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0125)\]. In addition, there are homeostatic forms of plasticity at the presynapse that compensate for altered [postsynaptic function](https://www.sciencedirect.com/topics/neuroscience/postsynaptic-function "Learn more about postsynaptic function from ScienceDirect's AI-generated Topic Pages") \[[26](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0130)\] and modifications to the number of release sites *N* during long-term plasticity \[[27](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0135),[28••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0140)\], which may also shape the synaptic transmission statistics.

Although the expression of synaptic plasticity can be presynaptic, its induction usually depends on postsynaptic activity \[[29](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0145)\]. This implies the need for retrograde signals that communicate with the presynapse. Two main signals have been identified: [nitric oxide](https://www.sciencedirect.com/topics/neuroscience/nitric-oxide "Learn more about nitric oxide from ScienceDirect's AI-generated Topic Pages"), which is responsible for presynaptic LTP, and [endocannabinoids](https://www.sciencedirect.com/topics/neuroscience/endocannabinoids "Learn more about endocannabinoids from ScienceDirect's AI-generated Topic Pages"), which mediates (in part) presynaptic LTD \[[30](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0150),[29](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0145)\] ([Figure 1](https://www.sciencedirect.com/science/article/pii/S0959438818301028#fig0005)b-ii). Interestingly, recent evidence shows that deficits in the retrograde signalling systems of both nitric oxide and endocannabinoids are implicated in learning and memory impairments, anxiety and depression \[[29](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0145)\]. This may be due to a failure in correctly adjusting probabilistic synapses during plasticity \[[31](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0155),[29](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0145)\].

Synaptic modifications should ultimately lead to more successful behavioural outcomes. Reward-based synaptic plasticity provides a framework in which synapses are modified by specific neuromodulators conveying behaviourally relevant information \[[32](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0160)\]. One such neuromodulator is dopamine, which is known to correlate with reward \[[33](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0165)\]. Moreover, dopamine and other neuromodulators regulate long-term synaptic plasticity \[[34](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0170),[32](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0160)\], suggesting that they may also control learning at probabilistic synapses ([Figure 1](https://www.sciencedirect.com/science/article/pii/S0959438818301028#fig0005)b-iii). This is consistent with recent results on [neuromodulation](https://www.sciencedirect.com/topics/neuroscience/neuromodulation "Learn more about neuromodulation from ScienceDirect's AI-generated Topic Pages") of presynaptic long-term plasticity \[[29](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0145)\], which has also been observed *in vivo* in Drosophila \[[35••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0175)\].

## Computational roles of probabilistic synapses

Despite the growing body of experimental observations suggesting a precise control of probabilistic synapses, it has remained unclear how these relate to computational functions. Below we highlight three key computational roles of probabilistic synapses and how they may be reconciled with experimental findings.

### Biophysical constraint

It is conceivable that due to high energetic costs associated with [neurotransmitter](https://www.sciencedirect.com/topics/neuroscience/neurotransmitters "Learn more about neurotransmitter from ScienceDirect's AI-generated Topic Pages") [transmission synapses](https://www.sciencedirect.com/topics/neuroscience/synaptic-transmission "Learn more about transmission synapses from ScienceDirect's AI-generated Topic Pages") remain unreliable unless necessary \[[36](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0180)\] ([Figure 3](https://www.sciencedirect.com/science/article/pii/S0959438818301028#fig0015)a). This view suggest that only synapses that are important for a given neuronal representation or behaviour should become reliable (see \[[37](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0185)\] for a similar argument at the neuronal level). Consistent with this hypothesis mathematical modelling of slice long-term [synaptic plasticity](https://www.sciencedirect.com/topics/neuroscience/synaptic-plasticity "Learn more about synaptic plasticity from ScienceDirect's AI-generated Topic Pages") experiments showed that after induction of long-term plasticity synapses become more reliable \[[12••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0060)\]. This result was further supported by reanalyses of *in vivo* sensory perception experiments \[[25](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0125),[12••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0060)\] However, it has remained unclear whether synapses not only become more reliable, but aim for the most reliable state (i.e. minimal variance). Recently, Costa *et al.* \[[38••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0190)\] put forward a model in which synapses optimise their response statistics during long-term synaptic plasticity towards reliable responses (i.e. with a given mean and minimal variance) referred to as statistical long-term synaptic plasticity (*stat*LTSP; [Figure 2](https://www.sciencedirect.com/science/article/pii/S0959438818301028#fig0010)a).

![Figure 2](https://ars.els-cdn.com/content/image/1-s2.0-S0959438818301028-gr2.jpg)

1.  [Download : Download high-res image (404KB)](https://ars.els-cdn.com/content/image/1-s2.0-S0959438818301028-gr2_lrg.jpg "Download high-res image (404KB)")
2.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S0959438818301028-gr2.jpg "Download full-size image")

Figure 2. Statistical long-term [synaptic plasticity](https://www.sciencedirect.com/topics/neuroscience/synaptic-plasticity "Learn more about synaptic plasticity from ScienceDirect's AI-generated Topic Pages") (*stat*LTSP). **(a)** The framework proposes that during long-term potentiation (LTP) synapses optimise their response statistics towards reliable responses (i.e. they minimise the divergence between their current statistics and a upper bound). This can be achieved by modifying the postsynapse (through changes in *q*, red) and the presynapse (through changes in *P*rel, blue). **(b)** The *Stat*LTSP proposal predicts a flow field of presynaptic and postsynaptic changes that depends on the current state of the synapse (given a Euclidean-metric and normalised *q*). **(c)** Model (black) captures single experiment variability (purple) of LTP induction in [Hippocampus](https://www.sciencedirect.com/topics/neuroscience/hippocampus "Learn more about Hippocampus from ScienceDirect's AI-generated Topic Pages"). Predicted flow field in the background (grey). **(d)** Frequency-dependent uncertainty encoding of synaptic plasticity. Plasticity experiments suggest that not only synapses aim for reliable responses when stimulated at high frequencies (long-term potentiation, as in (a–c))) or low frequencies (long-term depression) \[[12••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0060),[38••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0190)\], but also that at intermediate frequencies (∼25 Hz) synapses aim for maximum unreliability by setting *P*rel ∼ 0.5 (dashed green line, \[[39](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0195),[12••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0060)\]). Synaptic response variance (top) is calculated using standard binomial release statistics as *Nq*2*P*rel(1 − *P*rel), with *q* = 1 and *N* = 5, for illustration. Bottom panel illustrates the different release probability end points as a function of long-term plasticity pairing frequency. Figure partly adapted from \[[38••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0190)\].

![Figure 3](https://ars.els-cdn.com/content/image/1-s2.0-S0959438818301028-gr3.jpg)

1.  [Download : Download high-res image (360KB)](https://ars.els-cdn.com/content/image/1-s2.0-S0959438818301028-gr3_lrg.jpg "Download high-res image (360KB)")
2.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S0959438818301028-gr3.jpg "Download full-size image")

Figure 3. Computational roles of plastic probabilistic synapses. **(a)** Biophysical constraints, such as limited energy supply \[[36](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0180)\] may only allow reliable synapses to develop if necessary (e.g. during long-term plasticity) due to the high energetic costs (represented by red colour bar) of reliable [synaptic transmission](https://www.sciencedirect.com/topics/neuroscience/synaptic-transmission "Learn more about synaptic transmission from ScienceDirect's AI-generated Topic Pages"). **(b)** It has been postulated that the brain should also encode sensory statistics. Neurons in the brain responding to specific visual objects (e.g. dalmatian dog) should combine contextual information when inferring the presence or absence of an object. For a dalmatian neuron it would be important to integrate visual features such trees, dog head and animal legs (blue boxes). The uncertainty of the connections representing different features should be proportional to how relevant that feature is for that particular object. **(c)** Plastic probabilistic synapses have also been suggested to enable [neural networks](https://www.sciencedirect.com/topics/neuroscience/neural-networks "Learn more about neural networks from ScienceDirect's AI-generated Topic Pages") to find better solutions, escaping local optimum. For example, as animals explore an environment adaptive probabilistic synapses might enable animals to find better global paths.

*Stat*LTSP suggests a gradual optimisation process of synaptic transmission towards a reliable target synaptic weight (or bound) that should be triggered with every plastic event ([Figure 2](https://www.sciencedirect.com/science/article/pii/S0959438818301028#fig0010)b. This theory can explain a wide range of apparently disparate observations of long-term potentiation (LTP) at hippocampal and [visual cortex](https://www.sciencedirect.com/topics/neuroscience/visual-cortex "Learn more about visual cortex from ScienceDirect's AI-generated Topic Pages") excitatory synapses. For long-term depression (LTD), *stat*LTSP predicts presynaptic expression of plasticity — that is, changing *P*rel more rapidly decreases the synaptic response statistics towards a lower reliable target. Importantly, the model captures changes in the synaptic transmission statistics (presynaptic and postsynaptic) of individual recordings ([Figure 2](https://www.sciencedirect.com/science/article/pii/S0959438818301028#fig0010)c).[8](https://www.sciencedirect.com/science/article/pii/S0959438818301028#fn0010) How exactly would *stat*LTSP be implemented at synapses remains unclear. Nevertheless, Costa *et al.* \[[38••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0190)\] identified [nitric oxide](https://www.sciencedirect.com/topics/neuroscience/nitric-oxide "Learn more about nitric oxide from ScienceDirect's AI-generated Topic Pages") and [endocannabinoids](https://www.sciencedirect.com/topics/neuroscience/endocannabinoids "Learn more about endocannabinoids from ScienceDirect's AI-generated Topic Pages") as retrograde signals ([Figure 1](https://www.sciencedirect.com/science/article/pii/S0959438818301028#fig0005)b-ii) encoding errors in *q* and *P*rel consistent with the predictions.

Taken together this body of work suggest that long-term plasticity aims to reduce synaptic unreliability, consistent with the constraint view of stochastic synapses. However, this does not necessarily imply that synapses end up being reliable. First, in the intact brain during learning a mixture of LTP and LTD is likely to occur, which would maintain or increase response variability; second homeostatic mechanisms may control reliability due to its high energetic costs (as discussed above) and third, there are protocols (typically at intermediate frequencies, ∼25 Hz) that appear to maximise synaptic response variability (i.e. aiming for *P*rel = 0.5; \[[39](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0195),[12••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0060)\]; [Figure 2](https://www.sciencedirect.com/science/article/pii/S0959438818301028#fig0010)d). Interestingly, this last observation suggests a frequency-dependent variance encoding — whether synapses aim for minimal or maximal variance depends on the firing rate of presynaptic and postsynaptic neuron. The framework discussed here only aims to optimise the synaptic response variability without a clear behaviourally relevant task. But, it should be possible to extend *stat*LTSP to explicitly relate synaptic response variability to task-relevant uncertainty encoding.

### Encoding perceptual uncertainty

To maximise chances of survival animals should encode perceptual uncertainty associated with the environment in which they live \[[1](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0005)\] ([Figure 3](https://www.sciencedirect.com/science/article/pii/S0959438818301028#fig0015)b). A principled framework often used to describe how the brain may encode perceptual uncertainty is that of Bayesian inference \[[40](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0200)\]. According to the Bayesian inference hypothesis the brain computes the posterior probability over latent variables (e.g. predators) given sensory stimuli (e.g. visual stimuli) *P*(latent ∣ stimuli), which combines prior beliefs over the latent variables *P*(latent) with the incoming sensory evidence (likelihood) *P*(stimuli ∣ latent).

A growing body of work suggests that cortical circuits encode perceptual uncertainty following Bayesian inference ideas \[[1](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0005),[41](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0205),[2•](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0010),[3](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0015)\]. Exactly how such encoding of perceptual uncertainty may be used or learned at the synaptic level has remained unclear. Recent proposals have put forward the notion of synaptic sampling \[[10](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0050),[9•](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0045),[42](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0210)\], in which each synaptic release or structure (i.e. [dendritic spine](https://www.sciencedirect.com/topics/neuroscience/dendritic-spine "Learn more about dendritic spine from ScienceDirect's AI-generated Topic Pages") and axonal bouton) can be interpreted as a sample from a specific posterior distribution. Synaptic sampling can in principle be used by postsynaptic neurons to estimate posterior distributions (and uncertainty) over synaptic weights. For example, Kappel *et al.* \[[9•](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0045)\] demonstrated that spine motility (structural dynamics) similar to that observed experimentally \[[43](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0215)\] can be interpreted as sampling from a posterior distribution over [neural network](https://www.sciencedirect.com/topics/neuroscience/neural-networks "Learn more about neural network from ScienceDirect's AI-generated Topic Pages") configurations. This framework was recently extended to reward-based learning, thus adding a behaviourally relevant component to previous work by the same authors \[[42](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0210)\]. An alternative approach is that of \[[10](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0050)\] in which posterior distributions representing task uncertainty are formally encoded over synaptic weights distribution presumably through long-term synaptic plasticity. It should be noted that none of these frameworks consider synapse release (binomial) statistics as introduced above ([Figure 1](https://www.sciencedirect.com/science/article/pii/S0959438818301028#fig0005)Ai) and that structural sampling \[[9•](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0045),[42](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0210)\] operates on a slower timescale than synaptic release sampling \[[10](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0050)\].

Other approaches have built on the framework of Bayesian inference to introduce gradient descent methods to optimise the full distribution over the weights \[[11••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0055)\]. Similarly, Bellec *et al.* \[[44](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0220)\] introduced a network that optimally rewires as needed in a supervised learning setting closely following the synaptic sampling framework discussed above. Generative models are another class of probabilistic models implicitly related to Bayesian inference. Hierarchical variants of such models can learn progressively higher level features and uncertainty representations \[[45](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0225)\], consistent with experimental observations in sensory [neuroscience](https://www.sciencedirect.com/topics/neuroscience/neurosciences "Learn more about neuroscience from ScienceDirect's AI-generated Topic Pages") \[[1](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0005),[3](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0015),[46](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0230)\]. Recently, Neftci *et al.* \[[47](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0235)\] introduced a generative model with stochastic synapses that together with a local synaptic learning rule can be used for image-recognition tasks.

Despite the appealing properties and growing interest on Bayesian inference for uncertainty representation at the synaptic level \[[10](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0050),[9•](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0045),[42](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0210)\], it has remained unclear whether synapses are modified so as to encode some form of uncertainty. However, recent work by Costa *et al.* \[[38••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0190)\] provided some of the first evidence suggesting that synapses optimise their response statistics (see above). If mapped onto task-relevant quantities (e.g. probability of predator given auditory stimuli) this line of research may provide the first synaptic basis for learning uncertainty encoding in the brain. Additionally, there are open issues with the Bayesian hypothesis: first, sampling-based frameworks imply the need for a large number of samples to accurately estimate encoded uncertainty, second, full Bayesian inference requires computing a normalisation factor, which is computationally costly (although this can be often relaxed). Lastly, and perhaps more importantly, it is unclear whether alternative views, such as more standard predictive views of sensory coding are not sufficient; but, these views can be understood as special cases of each other \[[48](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0240)\].

### Escaping local optima in deep neural networks

One recurring aspect of statistical learning is that noise injection may improve the search over the solution space. Simulated annealing is a well-known variation of this idea in which the level of noise added to the network starts out being relatively high,[9](https://www.sciencedirect.com/science/article/pii/S0959438818301028#fn0015) but is gradually decreased over learning \[[49](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0245)\], allowing the network to escape local optima and converge to a good solution ([Figure 3](https://www.sciencedirect.com/science/article/pii/S0959438818301028#fig0015)c). This concept is remarkably similar to the biology of plastic probabilistic synapses, in that synapses also change their level of noise (variance) over learning (see above) \[[12••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0060),[38••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0190)\].

Similar principles have played an important role in the recent rise of deep learning \[[45](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0225),[46](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0230),[50](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0250)\]. One of the algorithms that has significantly improved performance of deep neural networks is Dropout \[[51](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0255)\]. The idea is to randomly drop (i.e. momentarily remove) neurons with some probability during training (but not during testing), which acts as a regulariser on the network (i.e. reduces overfitting) and enables uncertainty representation akin to Bayesian inference \[[52](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0260)\]. More recently, inspired on stochastic synaptic transmission this idea was applied at the level of synapses (DropConnect) \[[53](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0265)\], which randomly ‘drops’ connections instead of units with a predefined probability.

Dropout (or DropConnect) and its implications in machine learning can thus help us understand the functional utility of probabilistic synapses in the brain. One hypothesis is that learnable stochastic synapses could serve as a mechanism by which neural networks achieve better generalisation as in the simulated annealing algorithm \[[47](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0235),[54](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0270)\]. Additionally, learning probabilistic synapses may also provide a good trade-off between exploration and exploitation during reinforcement learning \[[55](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0275),[11••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0055)\]. Overall, understanding how to best adapt ‘drop’ probabilities is a open problem in both machine learning and neuroscience, but new developments in statistical learning have started shedding light on this issue \[[56](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0280)\].

## Conclusions and future directions

Recent technical developments on the measurement of presynaptic and postsynaptic terminals both *in vitro* and *in vivo* is reaching the point at which it will soon be possible to monitor the synaptic response statistics as an animal learns with high spatial and temporal resolution \[[58](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0290),[28••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0140)\]. In particular, recent advances in ultrafast [glutamate](https://www.sciencedirect.com/topics/neuroscience/glutamic-acid "Learn more about glutamate from ScienceDirect's AI-generated Topic Pages") imaging \[[57•](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0285)\] and statistical inference methods \[[19](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0095),[59•](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0295),[60](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0300)\] will enable accurate and optical measurements of [synaptic transmission](https://www.sciencedirect.com/topics/neuroscience/synaptic-transmission "Learn more about synaptic transmission from ScienceDirect's AI-generated Topic Pages") statistics. However, despite such fast developments in experimental [neuroscience](https://www.sciencedirect.com/topics/neuroscience/neurosciences "Learn more about neuroscience from ScienceDirect's AI-generated Topic Pages"), theoretical neuroscience, with some exceptions (e.g. \[[55](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0275),[12••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0060),[9•](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0045),[10](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0050),[38••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0190)\]), has so far largely overlooked the role of probabilistic synapses in [neural networks](https://www.sciencedirect.com/topics/neuroscience/neural-networks "Learn more about neural networks from ScienceDirect's AI-generated Topic Pages") and [synaptic plasticity](https://www.sciencedirect.com/topics/neuroscience/synaptic-plasticity "Learn more about synaptic plasticity from ScienceDirect's AI-generated Topic Pages").

Combined theoretical and experimental research has suggested that synapses optimise their response statistics through changes in presynaptic and postsynaptic components \[[12••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0060),[38••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0190)\]. In future work it would be important to extend these theories to also capture other puzzling experimental observations such as presynaptic homeostatic plasticity \[[61](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0305),[26](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0130)\], plastic number of release sites \[[27](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0135),[28••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0140)\], spine and bouton turnover \[[9•](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0045),[62•](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0310),[43](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0215)\], connection-type specificity \[[17](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0085),[20](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0100),[17](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0085), [18](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0090), [19](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0095)\], dependence on postsynaptic voltage \[[63](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0315),[61](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0305)\], variability optimisation \[[39](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0195),[12••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0060)\], and the multiple timescales and differential expression of synaptic plasticity \[[7](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0035),[5](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0025)\].

On the functional side several properties may be attributed to probabilistic synapses, such as encoding perceptual uncertainty \[[1](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0005),[10](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0050)\], escaping local optimum \[[55](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0275),[11••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0055),[9•](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0045),[42](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0210)\], but also reflecting biophysical constraints \[[36](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0180),[12••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0060),[38••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0190)\] in the addition to contributing to information processing \[[64](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0320),[65](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0325)\]. It is conceivable that plastic probabilistic synapses enable not just one, but several of these computational functions.

Finally, recent exciting developments have led to deep neural networks that learn to encode uncertainty \[[11••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0055),[56](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0280)\]. These developments together with the recent drive to map deep learning methods onto cortical circuits properties \[[50](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0250),[66](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0330), [67](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0335), [68](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0340)\] will help to guide new research into the function of probabilistic synapses. However, the brain still has a remarkable ability to efficiently encode perceptual and task-specific uncertainty in complex environments that far outperforms current machine learning methods \[[69](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0345)\]. Therefore, novel, unifying insights into the biology of probabilistic synapses also have the potential to inspire new learning algorithms.

## Acknowledgments

We would like to thank Jean-Pascal Pfister, Walter Senn, P Jesper Sjöström, Mark van Rossum, and Tim P Vogels for useful discussions over the years. Finally, we would also like to thank Everton J Agnes, Jakob Jordan and Jean-Pascal Pfister for useful feedback on this review. This work was supported by the Swiss National Science Foundation (310030L\_156863) and the Human Brain Project awarded to Walter Senn.

## References

[1](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0005)

J. Fiser, P. Berkes, G. Orbán, M. Lengyel

**Statistically optimal perception and learning: from behavior to neural representations?**

Trends Cogn Sci, 14 (2010), pp. 119-130

[2•](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0010)

G. Orbán, P. Berkes, J. Fiser, M. Lengyel

**Neural variability and sampling-based probabilistic representations in the visual cortex?**

Neuron, 92 (2016), pp. 530-543

In this work the authors show that many aspects of neuronal variability reflect perceptual uncertainty encoding.

[3](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0015)

R.M. Haefner, P. Berkes, J. Fiser

**Perceptual decision-making as probabilistic inference by neural sampling?**

Neuron, 90 (2016), pp. 649-660

[4](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0020)

S. Nabavi, R. Fox, C.D. Proulx, J.Y. Lin, R.Y. Tsien

**Engineering a memory with LTD and LTP**

Nature (2014)

[5](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0025)

P.R. Roelfsema, A. Holtmaat

**Control of synaptic plasticity in deep cortical networks?**

Nat Rev Neurosci, 19 (2018), pp. 166-180

[6•](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0030)

G. Malagon, T. Miki, I. Llano, E. Neher, A. Marty

**Counting vesicular release events reveals binomial release statistics at single glutamatergic synapses?**

J Neurosci, 36 (2016), pp. 4010-4025

The authors use recent developments to estimate binomial release statistics at single glutamatergic synapses.

[7](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0035)

R.P. Costa, B.E.P. Mizusaki, P.J. Sjostrom, M.C.W. van Rossum

**Functional consequences of pre- and postsynaptic expression of synaptic plasticity**

Philos Trans R Soc Lond Ser B Biol Sci, 372 (2017), p. 20160153

[8](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0040)

Z. Padamsey, N. Emptage

**Two sides to long-term potentiation: a view towards reconciliation**

Philos Trans R Soc Lond Ser B Biol Sci, 369 (2014), p. 20130154

[9•](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0045)

D. Kappel, S. Habenschuss, R. Legenstein, W. Maass

**Network plasticity as bayesian inference**

PLOS Comput Biol, 11 (2015), p. e1004485

The authors use a model to suggest that stochastic spine motility \[[43](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bib0215)\] reflects probabilistic inference through sampling over network configurations.

[10](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0050)

L. Aitchison, P.E. Latham

**Synaptic Sampling: A Connection Between PSP Variability and Uncertainty Explains Neurophysiological Observations**

(2015)

[11••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0055)

C. Blundell, J. Cornebise, K. Kavukcuoglu, D. Wierstra

**Weight uncertainty in neural networks**

Proceedings of the 32nd International Conference on Machine Learning (2015)

The authors introduced*Bayes by Backprop*, in which the distribution over weights is learnt, not just their means. They show that this improves generalisation and yields a good exploration–exploitation trade off in reinforcement learning tasks.

[12••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0060)

R.P. Costa, R.C. Froemke, P.J. Sjostrom, M.C.W. van Rossum

**Unified pre- and postsynaptic long-term plasticity enables reliable and flexible learning**

eLife, 4 (2015), p. e09457

In this paper the authors introduced a synaptic plasticity model that captures both presynaptic and postsynaptic plasticity data. They also show that this model matches*in vivo* perceptual learning data, and proposed a synaptic theory of memory savings.

[13](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0065)

J. Brea, A.T. Gaál, R. Urbanczik, W. Senn

**prospective coding by spiking neurons**

PLOS Comput Biol, 12 (2016), p. e1005003

[14](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0070)

K.C. Bittner, A.D. Milstein, C. Grienberger, S. Romani, J.C. Magee

**Behavioral time scale synaptic plasticity underlies CA1 place fields?**

Science, 357 (2017), pp. 1033-1036

[15](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0075)

U. Pereira, N. Brunel

**Attractor dynamics in networks with learning rules inferred from in vivo data**

Neuron (2018)

[16](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0080)

J. Del Castillo, B. Katz

**Quantal components of the end-plate potential?**

J Physiol, 124 (1954), pp. 560-573

[17](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0085)

A. Brémaud, D.C. West, A.M. Thomson

**Binomial parameters differ across neocortical layers and with different classes of connections in adult rat and cat neocortex?**

Proc Natl Acad Sci U S A, 104 (2007), pp. 14134-14139

[18](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0090)

A.V. Blackman, T. Abrahamsson, R.P. Costa, T. Lalanne, P.J. Sjostrom

**Target-cell-specific short-term plasticity in local circuits**

Front Synapt Neurosci, 5 (2013), p. 11

[19](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0095)

R.P. Costa, P.J. Sjostrom, M.C.W. van Rossum

**Probabilistic inference of short-term synaptic plasticity in neocortical microcircuits**

Front Comput Neurosci, 7 (2013), p. 75

[20](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0100)

A.M. Thomson

**Functional maps of neocortical local circuitry?**

Front Neurosci, 1 (2007), pp. 19-42

[21](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0105)

Y. Wang, H. Markram, P.H. Goodman, T.K. Berger, J. Ma, P.S. Goldman-Rakic

**Heterogeneity in the pyramidal network of the medial prefrontal cortex?**

Nat Publ Group, 9 (2006), pp. 534-542

[22](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0110)

A. Reyes, B. Sakmann

**Developmental switch in the short-term modification of unitary EPSPs evoked in layer 2/3 and layer 5 pyramidal neurons of rat neocortex?**

J Neurosci, 19 (1999), pp. 3827-3835

[23](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0115)

G. Testa-Silva, M.B. Verhoog, D. Linaro, C.P.J. de Kock, J.C. Baayen, R.M. Meredith, C.I. De Zeeuw, M. Giugliano, H.D. Mansvelder

**High bandwidth synaptic communication and frequency tracking in human neocortex**

PLoS Biol, 12 (2014), p. e1002007

[24](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0120)

R.A. Silver

**High-probability uniquantal transmission at excitatory synapses in barrel cortex?**

Science, 302 (2003), pp. 1981-1984

[25](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0125)

R.C. Froemke, I. Carcea, A.J. Barker, K. Yuan, B.A. Seybold, A.R.O. Martins, N. Zaika, H. Bernstein, M. Wachs, P.A. Levis, D.B. Polley, M.M. Merzenich, C.E. Schreiner

**Long-term modification of cortical synapses improves sensory perception?**

Nat Neurosci, 16 (2013), pp. 79-88

[26](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0130)

X. Li, P. Goel, C. Chen, V. Angajala, X. Chen, D.K. Dickman

**Synapse-specific and compartmentalized expression of presynaptic homeostatic potentiation**

eLife, 7 (2018), p. e34338

[27](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0135)

A. Loebel, J.-V. Le Bé, M.J.E. Richardson, H. Markram, A.V.M. Herz

**Matched pre- and post-synaptic changes underlie synaptic plasticity over long time scales?**

J Neurosci, 33 (2013), pp. 6257-6266

[28••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0140)

A.-H. Tang, H. Chen, T.P. Li, S.R. Metzbower, H.D. MacGillavry, T.A. Blanpied

**A trans-synaptic nanocolumn aligns neurotransmitter release to receptors?**

Nature, 536 (2016), pp. 210-214

Using localisation microscopy the authors revealed a new level of synaptic organisation in which release and postsynaptic receptors are aligned at the nano scale. This opens possibility of new level of structure for probabilistic synaptic transmission.

[29](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0145)

H.R. Monday, P.E. Castillo

**Closing the gap: long-term presynaptic plasticity in brain function and disease**

Curr Opin Neurobiol, 45 (2017), pp. 106-112

[30](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0150)

Y. Andrade-Talavera, P. Duque-Feria, O. Paulsen, A. Rodriguez-Moreno

**Presynaptic spike timing-dependent long-term depression in the mouse hippocampus**

Cereb Cortex (New York, N.Y.: 1991), 26 (2016), pp. 3637-3654

[31](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0155)

E. Hebert-Chatelain, T. Desprez, R. Serrat, L. Bellocchio, E. Soria-Gómez, A. Busquets-Garcia, A.C. Pagano Zottola, A. Delamarre, A. Cannich, P. Vincent, M. Varilh, L.M. Robin, G. Terral, M.D. Garc&rsquo;í-Fernández, M. Colavita, W. Mazier, F. Drago, N. Puente, L. Reguero, I. Elezgarai, J.-W. Dupuy, D. Cota, M.-L. Lopez-Rodriguez, G. Barreda-Gómez, F. Massa, P. Grandes, G. Bénard, G. Marsicano

**A cannabinoid link between mitochondria and memory?**

Nature, 539 (2016), pp. 555-559

[32](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0160)

N. Frémaux, W. Gerstner

**Neuromodulated spike-timing-dependent plasticity, and theory of three-factor learning rules**

Front Neural Circuits, 9 (2016), p. 1178

[33](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0165)

W.R. Stauffer, A. Lak, A. Yang, M. Borel, O. Paulsen, E.S. Boyden, W. Schultz

**Dopamine neuron-specific optogenetic stimulation in Rhesus Macaques**

Cell, 166 (2016)

[34](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0170)

V. Pawlak, J.R. Wickens, A. Kirkwood, J.N.D. Kerr

**Timing is not everything: neuromodulation opens the STDP gate**

Front Synapt Neurosci (2010)

[35••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0175)

R. Cohn, I. Morantte, V. Ruta

**Coordinated and compartmentalized neuromodulation shapes sensory processing in Drosophila?**

Cell, 163 (2015), pp. 1742-1755

Imaging of Kenyon cell output synapses in the intact brain of Drosophila shows reward-dependent modifications at presynaptic terminals. This work suggests that probabilistic synapses are also modified during rewarded events.

[36](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0180)

J.J. Harris, R. Jolivet, D. Attwell

**Synaptic energy use and supply?**

Neuron, 75 (2012), pp. 762-777

[37](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0185)

L. Aitchison, G. Hennequin, M. Lengyel

**Sampling-based probabilistic inference emerges from learning in neural circuits with a cost on reliability**

(2018)

[38••](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0190)

R.P. Costa, Z. Padamsey, J.A. D’amour, N.J. Emptage, R.C. Froemke, T.P. Vogels

**Synaptic transmission optimization predicts expression loci of long-term plasticity**

Neuron, 96 (2017)

The authors propose that synapses optimise their own statistics to become strong and reliable. This work demonstrates that synapses may indeed optimise their response statistics.

[39](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0195)

N.R. Hardingham, G.E. Hardingham, K.D. Fox, J.J.B. Jack

**Presynaptic efficacy directs normalization of synaptic strength in layer 2/3 rat neocortex after paired activity?**

J Neurophysiol, 97 (2007), pp. 2965-2975

[40](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0200)

J.O. Berger

**Statistical Decision Theory and Bayesian Analysis**

Springer Science & Business Media (2013)

[41](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0205)

W.J. Ma, M. Jazayeri

**Neural coding of uncertainty and probability**

Annu Rev Neurosci, 37 (2014), pp. 205-220

[42](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0210)

D. Kappel, R. Legenstein, S. Habenschuss, M. Hsieh, W. Maass

**A dynamic connectome supports the emergence of stable computational function of neural circuits through reward-based learning**

ENEURO (2018)

[43](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0215)

G. Mongillo, S. Rumpel, Y. Loewenstein

**Intrinsic volatility of synaptic connections — a challenge to the synaptic trace theory of memory**

Curr Opin Neurobiol, 46 (2017), pp. 7-13

[44](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0220)

G. Bellec, D. Kappel, W. Maass, R. Legenstein

**Deep rewiring: training very sparse deep networks**

International Conference on Learning Representations (2018)

[45](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0225)

I. Goodfellow, Y. Bengio, A. Courville

**Deep Learning**

MIT Press (2016)

[46](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0230)

D.L.K. Yamins, J.J. DiCarlo

**Using goal-driven deep learning models to understand sensory cortex?**

Nat Neurosci, 19 (2016), pp. 356-365

[47](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0235)

E.O. Neftci, B.U. Pedroni, S. Joshi, M. Al-Shedivat, G. Cauwenberghs

**stochastic synapses enable efficient brain-inspired learning machines**

Front Neurosci, 10 (2016), p. 796

[48](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0240)

L. Aitchison, M. Lengyel

**With or without you: predictive coding and Bayesian inference in the brain**

Curr Opin Neurobiol, 46 (2017), pp. 219-227

[49](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0245)

S. Kirkpatrick, C.D. Gelatt, M.P. Vecchi

**Optimization by simmulated annealing?**

Science, 220 (1983), pp. 671-680

[50](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0250)

D. Hassabis, D. Kumaran, C. Summerfield, M. Botvinick

**neuroscience-inspired artificial intelligence?**

Neuron, 95 (2017), pp. 245-258

[51](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0255)

N. Srivastava, G. Hinton, A. Krizhevsky, I. Sutskever, R. Salakhutdinov

**Dropout: a simple way to prevent neural networks from overfitting?**

J Mach Learn Res, 15 (2014), pp. 1929-1958

[52](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0260)

Y. Gal, Z. Ghahramani

**Dropout as a Bayesian approximation: Representing model uncertainty in deep learning**

International Conference on Machine Learning (2016), pp. 1050-1059

[53](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0265)

L. Wan, M. Zeiler, S. Zhang, Y. Le Cun, R. Fergus

**Regularization of neural networks using dropconnect**

International Conference on Machine Learning (2013), pp. 1058-1066

[54](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0270)

J.S. Bowers

**Parallel distributed processing theory in the age of deep networks**

Trends Cogn Sci (2017)

[55](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0275)

H.S. Seung

**Learning in spiking neural networks by reinforcement of stochastic synaptic transmission?**

Neuron, 40 (2003), pp. 1063-1073

[56](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0280)

Y. Gal, J. Hron, A. Kendall

**Concrete dropout**

Advances in Neural Information Processing Systems (2017), pp. 3584-3593

[57•](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0285)

N. Helassa, C.D. Dürst, C. Coates, S. Kerruth, U. Arif, C. Schulze, J.S. Wiegert, M. Geeves, T.G. Oertner, K. Torok

**Ultrafast glutamate sensors resolve high-frequency release at Schaffer collateral synapses**

Proc Natl Acad Sci U S A (2018)

The authors introduce novel sensors for ultrafast imaging of glutamate release. These sensors offer the promise to measure binomial release parameters before and after long-term plasticity induction.

[58](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0290)

S.A. Rey, C.A. Smith, M.W. Fowler, F. Crawford, J.J. Burden, K. Staras

**Ultrastructural and functional fate of recycled vesicles in hippocampal synapses**

Nat Commun, 6 (2015), p. 8043

[59•](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0295)

A.D. Bird, M.J. Wall, M.J.E. Richardson

**Bayesian inference of synaptic quantal parameters from correlated vesicle release**

Front Comput Neurosci, 10 (2016), p. 116

The authors introduce a new, more complete statistical inference method to infer both synaptic transmission and sort-term synaptic plasticity parameters.

[60](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0300)

A. Ghanbari, A. Malyshev, M. Volgushev, I.H. Stevenson

**Estimating short-term synaptic plasticity from pre- and postsynaptic spiking**

PLOS Comput Biol, 13 (2017), p. e1005738

[61](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0305)

T. Branco, K. Staras, K.J. Darcy, Y. Goda

**local dendritic activity sets release probability at hippocampal synapses?**

Neuron, 59 (2008), pp. 475-485

[62•](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0310)

J.S. Jackson, J. Witton, J.D. Johnson, Z. Ahmed, M. Ward, A.D. Randall, M.L. Hutton, J.T. Isaac, M.J. O’Neill, M.C. Ashby

**Altered synapse stability in the early stages of tauopathy?**

Cell Rep, 18 (2017), pp. 3063-3068

Both synaptic boutons and spines exhibit high (and fast) turnover rates, which may be interpreted as a form of probabilistic synapses\[9•,42\]. The authors made the interesting observations that these two components are regulated differentially in early stages of Alzheimer's disease.

[63](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0315)

P.J. Sjöström, G.G. Turrigiano, S.B. Nelson

**Rate, timing, and cooperativity jointly determine cortical synaptic plasticity**

Neuron, 32 (2001), pp. 1149-1164

[64](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0320)

C. Zhang, C.S. Peskin

**Improved signaling as a result of randomness in synaptic vesicle release?**

Proc Natl Acad Sci U S A, 112 (2015), pp. 14954-14959

[65](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0325)

M. Nolte, M.W. Reimann, J.G. King, H. Markram, E.B. Muller

**Cortical reliability amid noise and chaos**

bioRxiv (2018), p. 304121

[66](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0330)

J. Guerguiev, T.P. Lillicrap, B.A. Richards

**Towards deep learning with segregated dendrites**

eLife, 6 (2017), p. 1

[67](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0335)

R.P. Costa, Y.M. Assael, B. Shillingford, N. de Freitas, T.P. Vogels

**Cortical microcircuits as gated-recurrent neural networks**

Advances in Neural Information Processing Systems (2017), pp. 271-282

[68](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0340)

J. Sacramento, R.P. Costa, Y. Bengio, W. Senn

**Dendritic cortical microcircuits approximate the backpropagation algorithm**

Advances in Neural Information Processing Systems (2018)

[69](https://www.sciencedirect.com/science/article/pii/S0959438818301028#bbib0345)

B.M. Lake, T.D. Ullman, J.B. Tenenbaum, S.J. Gershman

**Building machines that learn and think like people**

Behav Brain Sci, 40 (2016), p. 195

## Cited by (13)

[View Abstract](https://www.sciencedirect.com/science/article/abs/pii/S0959438818301028)

© 2018 Elsevier Ltd. All rights reserved.
