---
type:  writing/draft
status: active 
priority: p1
creationtag: 2022-05-24 15:57
infotags:
comments: "Gustavo has specifically requested a rework of the Research Plan"
---

> [11:14 AM] Gustavo Borges Moreno e Mello
> I was thinking that now that you have a clearer vision of what do you want to do and why, you could work better on refining the plan of how you plan to execute your thesis.
> 
> Try to think from the beginning to the end, but also backwards towards the beginning
> 
> Think about the landmarks you need to reach and try, at your best capacity to see what do you need to have in place to get there.
> 
> also, try to make a list of relevant authors and labs (with countries and institutions) that are relevant to your research. Use the papers you read so far as a starting point. Pay special attention to the "correspondent authors" and try to track not only where they were when they did the paper, but were they are now and if they are still working on the topic.
> 
> Finally, make also a list of keywords that you can use for searching.

# Research and Progress Plan 
## Research Review
Because my proposed project relies on combining several
fields at the forefront of machine learning, it is imperative I bring
myself to having a comfortable command of underlying concepts and recent developments in the larger community which relate to my goals.

To facilitate this, I will perpetually update my knowledge and skills through research of previous and emerging materials, enrollment 
in PhD Courses, via involvement with conferences, schools, and active collaboration with other researchers. 

## Establishing Benchmarks
It will be essential to establish new benchmarks against which to compare our developments against current and previous models.
The problem of assessing the performance of Deep SNN models has come into focus as conventional AI benchmarks have a contextually different focus, than the problems addressed by SNNs [[@pfeifferDeepLearningSpiking2018]].

The benchmark in Tan et al. 2020 
[[@tanStrategyBenchmarkConverting2020]] is a good place to start from as it has already been used as a benchmark in recent DRL-SNN models [[@chenDeepReinforcementLearning2022]]. Using this as a basis, we can benchmark our preliminary models, and develop it to address our future models involving separation of timescales and objectives. 

## Development of DRL-SNN and Multi-Timescale Models
Our initial models, will be developed on the basis of previously established models of: DRL-SNNs such as Chen et al 2022 [[@chenDeepReinforcementLearning2022]], and timing models such as LMUs [[@voelkerLegendreMemoryUnits2019]] which are implementable in SNNs. As we develop these previously established models into our own, we will steer them into models capable of multiple objectives and timescale representations.

Our research of credit assignment will use biologically plausible spiking communication models such as Payeur 2021
[[@payeurBurstdependentSynapticPlasticity2021]] and Bellec 2020
[[@bellecSolutionLearningDilemma2020]]. As these spiking models of credit assignment are driven by distinctions in temporal events, we will study how these models might express different timescales in their dynamics and how they may be modified to better represent multiple timescales.  

The next step will be integration of our biologically plausible models of credit assignment, with the established models and our own iterations of these models. These models will be tested against our benchmarks and optimized for problems in multiple timescales.

## Implementation in Neuromorphic Hardware
A tertiary goal is to implement any of our sufficiently developed models in neuromorphic hardware. While we will iterate on these models in conventional computing ecosystems. We will maintain the possibility of eventual implementation in neuromorphic hardware; and thus take steps to ensure portability of the models into neuromorphic development software and hardware.

We will consider and apply for use of available neuromorphic hardware platforms. This decision will  be informed by the availability of possible hardware and the properties of the models we use. For instance should our model include an STDP based mechanism, we may prefer use of hardware which natively supports such a feature. The diversity of neuromorphic hardware features is explored in figure 2.