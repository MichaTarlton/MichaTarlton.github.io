---
type: writing/draft
status: active
priority: p1
creationtag: 2022-05-18 19:18
infotags: proposal
---

# Introduction
## Combining Reinforcement, Deep Learning, and Spiking Neural Networks 
### Reinforcement Learning
Reinforcement Learning (RL) considers the problem of an *agent*  acting in an environment, learning by trial and error. Typically, this *environment* represents some task in which the *state* of the task or environment must be interpreted and mapped to some *policy* of action by the agent. That is, the agent must optimize its interaction with the environment to achieve some maximal reward signal from the environment. 

The benefit of RL schemes is their ability to “self-learn” or optimize to a task without direct supervision or input. This method is further enhanced through introduction of exploration versus exploitation trade off to RL schemes. Exploration allows for sub-optimal actions to be chosen in order to fully explore the space of action-rewards, and correction to the policy to be made as needed.  The adaptability and “self-supervising” nature of this framework offers great benefits in a wide range of machine learning applications.

However, this framework comes with key limitations. The current optimization of action-reward policies only operates in a single timescale. RL can maximize for reward within a small timescale, but will fail to optimize for multi-objective tasks at larger timescales [[50 Reading/zot2/@botvinickDeepReinforcementLearning2020]]. 

In real-life models, where flexible association between multiple objectives, rewards, and timescales may be flexibly and simultaneously be optimized for greater reward over multiple and competing timescales. A delayed reward gratification in smaller time scales may often be optimal for return of maximum reward, E.g.: a prey creature may learn to scavenge at particular times, suffering hunger in the short term, in order to avoid predator exposure in the long term. 

Additionally, RL is limited to domains of limited application and low-dimensional state spaces [[@mnihHumanlevelControlDeep2015]]. As the space of environmental states and available actions increases, conventional RL methods such as Q-Learning become intractable tasks. A different approach, scalable to learning in environments with high-dimensional spaces, is required. 

### Deep Learning
In order to mitigate this barrier, RL has been combined with Deep Learning methods. Deep learning (DL), offers a method of simplifying and optimizing high-dimensional spaces in learning. Conventional DL relies on stationary gradient-based optimization, which is not implementable in “live” RL models, nor in spiking networks. Variations on have been successfully integrated with RL [[@mnihHumanlevelControlDeep2015]]  with surrogate-gradient learning [[@chenDeepReinforcementLearning2022]] and further improvements are a field of development  [[@hesselRainbowCombiningImprovements2017]]. 

While RL supposes a more biologically plausible model of adaptation, and learning in an unpredictable or changing environment; DL is very much a synthetic, non-biologically plausible model. DL relies on feed-forward networks, which while seemingly able to reach brain-like results in problem-solving, these networks require well-behaved and differentiable network functions to learn  [[50 Reading/citations/@zenkeVisualizingJointFuture2021]]. 

DL also introduces its own issues with time-representations. Representing time in a DL network without relying on additional and external modules, requires aspects of recurrent connections to be introduced, however modern recurrent neural networks can not be generalized to more than a single task due to “catastrophic forgetfulness” [[@princeCurrentStateFuture2022]] [[@rolnickExperienceReplayContinual2019a]] .

This is a barrier in the development of more efficient and computationally complex models. 

### Spiking Neural Networks
Spiking Neural Networks (SNN) offer the opportunity to reinforce both DL and RL. Designed on the basis of biologically inspired mechanisms found in physical neural substrates, SNNs are reactive, adaptable, efficient, and computationally complex[ [[@pfeifferDeepLearningSpiking2018]] [[@tavanaeiDeepLearningSpiking2019]]].  A comparison of spiking and non-spiking units is given in figure 1.

SNNs are reactive and computationally efficient because of their sparse, analog computing, and event-driven processing. Thus making SNNs particularly suited for use in applications of energy-efficient neuromorphic hardware where reactivity to novel environmental conditions are valued. Examples from the field include: automated driving, internet of things, and robotics, and many possible future technologies [[@princeCurrentStateFuture2022]].

In addition to this, SNNs are naturally designed for online learning, and capable of multiplexing processing in asynchronous and parallel communications [[50 Reading/citations/@zenkeVisualizingJointFuture2021]]. However, these capabilities, while naturally occurring in biological models, have yet to be fully unlocked in synthetic SNNs.

Deep SNN models offer a potential leap in machine learning abilities. 

---
[[Screenshot_20220521_110624.png]]
Fig. 1: Adapted from [[@chenDeepReinforcementLearning2022]]. General spiking neural model (Top) versus a general non-spiking neural model (Bottom).  The spiking model, where at timestep $t$, $X_t$ is the external input, $H_t$ represents the membrane voltage after neural dynamics, $V_t$ represents the trigger of a spike, and $S_t$ is the spike output which is 1 if there is a spike and 0 if there is no event. Contrast with a non-spiking model. The one shown attempts to simplify the neural model by simply passing along the membrane potential (for a leaky integrate-and-fire neuron). The key difference between the spiking and non-spiking network is the sparse communication in the spiking model (where communication between nodes is off until it is “on”) and in the non-spiking model, where information between units is continuously given.

---



The key feature behind SNN’s is their temporal dynamics. By definition of their spiking communication, SNNs directly encode time information directly into their network behavior. 

At the neuron-to-neuron communication level, multiple dimensions of synaptic learning data can be conveyed through spike timing relationships and spike burst patterns [[@gerstnerEligibilityTracesPlasticity2018]] , [[@montemurroPhaseofFiringCodingNatural2008]]. The well established biological mechanism of Spike-Timing Dependent Plasticity (STDP) broadly defines these mechanisms, and has been used to produce models in DL back-propagation techniques for SNNs [[@payeurBurstdependentSynapticPlasticity2021]].

At the whole-network level, the gestalt of these neuron-on-neuron timing interactions and recursive network connections, gives rise to neural oscillations. These macro-scale temporal dynamics may remove reliance on a centralized clock and allow for asynchronous information processing in parallel and multiple timescales [[@princeCurrentStateFuture2022]]. 

These parallel macro and micro temporal dynamics are of especial interest to us. The full scope of nested temporal dynamics could be utilized to encode the multiple timescales representations necessary to facilitate time-dependent learning of reward and environment conditions, in a biologically plausible model of *in-computation memory*.

### Challenges in DRL and DRL-SNNs
A key challenge in implementing DL in either RL or SNNs have problems with what is known as the *credit assignment problem* where back propagation of error in both is less than straightforward due to their inability to utilize gradient-based optimization or Back-Propagation Through Time (BPTT) as in standard DL models. Instead, an online and non-forgetful solution to reward based learning is needed, particularly in SNNs  [[@pfeifferDeepLearningSpiking2018]], [[@tavanaeiDeepLearningSpiking2019]] .  

Plausible solutions are available to the credit assignment problem in both DRL and RL-SNN models [[@pfeifferDeepLearningSpiking2018]], [[@princeCurrentStateFuture2022]], and recent research has addressed the issue directly in Deep Reinforcement Learning with Spiking Neural Network (DRL-SNN) paradigms [[@chenDeepReinforcementLearning2022]]. However, these must be expanded on and developed for the multi-timescale regime [[50 Reading/zot2/@botvinickDeepReinforcementLearning2020]].

# Research Questions
The key question we want to answer is how multiple timescales and event associations can be represented in a viable model of reward and learning. Specifically, how can we exploit the innate properties of multifold temporal dynamics found in spiking neural networks, to model a reinforcement learning scheme capable of learning in a complex hyperspace of both time and environmental variables.

An animal agent must associate multiple frames of reference in time with actions to be taken, and the potential risk / reward scenarios. Multiple objectives, each with their own overlapping and nested time frames, must be considered by the animal. The associations and reinforcements, made between the animal’s behavior and conditions, depends on how it recognizes scales of time. 

How can these timescales be recognized by a synthetic agent? Not only is the learning dependent on association between event and time, but also on recognition of different intervals of time. Additionally, correct association between the appropriate time interval and the relevant event must be learned. 

The association between time and events has been addressed by machine learning methods up until now, in only short time scales and to single tasks. We ask if it is possible to create a learning method to optimize the behavior of an agent, not only  in regard to the short term, but the actions required in the short term to maximally a long term policy. 

Can we create a model, which learns simultaneous state-action optimizations for multiple reference frames of time, the same way an animal may choose its behaviors. For example, make decisions not only on the time of day, but the time of year. Can this model correctly associate reward with actions made, not most recently, but most relevant over the whole time-space.

Assuming, we achieve our goal of encoding multiple, flexible, timescales in SNNs to amplify the abilities of DRL, we can:
→ Create a model which will self-teach
→ Do so for a large state, action, reward, and time relation space
→ Optimize for multiple objectives in both the environment and time

By result of this research, we will have developed:
→ Novel discoveries in SNN temporal dynamics
→ Novel DRL-SNN architecture design and models
→ Novel concept mechanisms to relate to biological systems and implement in neuromorphic hardware

## What is my “position”
1. Spiking neural dynamics are temporally driven
2. These temporally driven dynamics exhibit micro-properties, which can give rise to macro-properties and multi-timescale resolutions in a greater gestalt
3. These properties should be studied and developed for implementation in SNNs with Deep RL models

---

# Methods and Related Work 
## Multiple Timescale Dynamics in SNN
In order to understand, associate, and respond to events and rewards in the environment at different timescales, the system must maintain some concept of “time” in its calculations. A number of methods have been implemented to represent time in SNNs such as Synfire chain [[@abelesCorticonicsNeuralCircuits1991]], [[@kumarSpikingActivityPropagation2010]], sliding windows [**Citation needed**, lmus use them], and reservoir systems (such as liquid state machines) [[@ponulakSupervisedLearningSpiking2010]], but representing in multiple frames of time has proved a more difficult task [[50 Reading/citations/@zenkeVisualizingJointFuture2021]].

The FORCE training network of Nicola and Clopath 2017 [[@nicolaSupervisedLearningSpiking2017]], creates a network of episodic memory, able to learn and replay a birdsong through synchronized oscillations of the mean spiking population activity. ^u9fm4e

Bellec et al. 2020 [[@bellecSolutionLearningDilemma2020]] uses a method called *reward based E-prop* to solve the problem of time-event association in a spiking neural network.

A second paper, Yin et al. 2020 [[@yinEffectiveEfficientComputation2020]] uses a similar framework for multi-timescale representation, while also optimizing for efficiency. Both of these papers rely on a Recurrent SNN architecture, primarily to offer a solution to the issue of credit-assignment. 

A third design of interest to us, is Legendre Memory Units (LMUs) [[@voelkerLegendreMemoryUnits2019]] which is also a hybrid design of recurrent and linear layers within each unit to encode multiple temporal dependencies. They also have been shown to exhibit “time-cell” like behavior and have already been implemented in SNN and neuromorphic hardware where they were able to exhibit on-chip learning. 

Studies of these designs will inform the direction of implementation of multi-timescale dynamics in our design, and present opportunities for collaboration with these labs studying similar topics.


## DRL-SNNs
DRL implementation in SNNs has only recently been tested in the literature [[@tangDeepReinforcementLearning2020]] , [[Chen 2022|Chen et al. 2022]] [[@chenDeepReinforcementLearning2022]] is the latest and most prominent example in which a Deep Q-Learning Network (DQN) [[@mnihHumanlevelControlDeep2015]] is implemented into a SNN to great success when testing against a DQN in a conventional artificial neural network. Particularly in regard to energy efficiency.

## Credit Assignment Problem
Up until now we have already discussed several papers which have addressed the challenges with the credit assignment problem [ [[@bellecSolutionLearningDilemma2020]],[[@yinEffectiveEfficientComputation2020]], [[@nicolaSupervisedLearningSpiking2017]]], even in DRL-SNNs [[@chenDeepReinforcementLearning2022]]. Though in SNN literature there is still a great deal of development to be made  in biologically-plausible, *three-factor* or *NeoHebbian*, learning mechanisms [[@gerstnerEligibilityTracesPlasticity2018]].

[[Payeur et al. 2021]] offer a biologically plausible model based on spike timing dependent plasticity, which uses a *three-factor* model to differentiate between spikes and “events” which imply some learning signal. Isolated spikes and bursts maintain different meanings, allowing for two information channels of simultaneous feed-forward and feedback error flows. This dual-channel mechanism may be useful in RL as signals propagate in real time. Additionally, it allows for the construction of inhibitory micro-circuits.

## Neuromorphic Hardware and SNNs
Neuromorphic hardware designed to exploit the advantages of analog computing with many natively implementing spike-based or event-based processing [[@mehonicBraininspiredComputingNeeds2022]]. The aforementioned LMUs based networks were implemented in Intel’s Loihi [[@voelkerSpikePerformanceTraining2021]]. Other systems such as Spinnaker [[@furberSpiNNakerProject2014]] and BrainScaleS [[@schmittNeuromorphicHardwareLoop2017]] offer advantages of native STDP based computing. Other neuromorphic systems and their strengths are illustrated in Figure 2.

---
[Fig. 2](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2Fs41586-021-04362-w/MediaObjects/41586_2021_4362_Fig2_HTML.png)
Fig 2. Adapted from Mehonic et al. 2021[[@mehonicBraininspiredComputingNeeds2022]]. The figure describes several neuromorphic systems and plots them in four quadrants relative to interpretation by the author as to their reliance on digital or analog (or mixed-analog) hardware substrate (**y-axis**) and the research motivations driving the architecture design: biological or synthetic models (**x-axis**) . Additionally, several properties of these systems are listed on the right-hand side.

---

# Research Plan
**Please see Figure 3 for a brief visual summary of my PhD timetable**.
[Fig 3.](https://lh6.googleusercontent.com/KA19xNpBZeDSp87hPhAkV-5ZfTtR-m0Yj4HbvEOeew-1Jnca4dLHmIZBr7BKqlKqmTr5bCubhLA9v4ThMM37cuqNzFy3imINxjWX_wGLrUwWm7oNi8D5_Am_z3Rx94IMshpiQqg)
Fig.3: Visual summary and timetable of PhD project.

## Research Review
Most importantly at the seminal stage of my project, but still at all stages, I will be updating my skills and knowledge of previous and current research being done in similar fields. 

Because my proposed project relies on combining several “next-generation” fields of machine learning, it is imperative I bring myself to having comfortable command of the underlying concepts and the recent developments which relate to my goals.

## Research and implementation of known methods and establishing benchmarks
I will start with implementing recent methods which offer plausible solutions to our questions raised. Here I give a detailed but incomplete list of particular implementations I will attempt to recreate in my own development environment. 

The project will consist of the development of a Deep Reinforcement Learning model in a Spiking Neural Network framework. We will build this model up from established methods in SNNs and DRL to create a basic combined model. Using this basic model we can develop an analytic heuristic against which to benchmark descendant models.

### Heuristics in the field of DRL-SNN
There is a need for new benchmarks by which to test the efficacy of both DRL-SNNs and multi-timescale dynamics [[@pfeifferDeepLearningSpiking2018]], [[50 Reading/citations/@zenkeVisualizingJointFuture2021]]. In much of the literature some visual or game based task is used for testing, such as the psMNIST [[@chilkuriParallelizingLegendreMemory2021]] or Atari 2600 games [[@chenDeepReinforcementLearning2022]] . However it is likely we will need to develop and build off previous examples in order to appropriately test our models as we develop them.

Tan et al. 2020 [[@tanStrategyBenchmarkConverting2020]] offers a new standard by which to test DRL-SNNs which was then again picked up and used in Chen et al. 2022. We will probably begin by using a similar benchmark when comparing our DRL and SNN based models.

Our goal at this stage will be to replicate plausible methods and begin envisioning benchmarks and measurements of future combination models.

### Development of DRL-SNN Models
**DRL implementations**, such as the DQN [[@mnihHumanlevelControlDeep2015]] and subsequent Deep Reinforcement Schemes [[@hesselRainbowCombiningImprovements2017]] will be the first methods to replicate. This should include at least one spiking model such as the one featured in Chen et al. 2022 [[@chenDeepReinforcementLearning2022]]

Recent models of the same type [[@chenDeepReinforcementLearning2022]]  , [[@tangDeepReinforcementLearning2020]] directly address the issues of credit assignment, but leave plenty of questions in regard to time representation. As we develop our own DRL-SNN, we will steer its development with the representation of time and multi-timescale objectives at the forefront of consideration.

Credit assignment methods which are implementable in SNNs, particularly using biologically inspired mechanisms such as timing-dependent and neo-hebbian mechanisms will need to be tested for effectiveness and compatibility with network architectures we choose. So I will replicate the models found in Payeur 2021 [[@payeurBurstdependentSynapticPlasticity2021]] and Bellec 2020. [[@bellecSolutionLearningDilemma2020]]

Once I have established methods and benchmarks from previous research, I will begin to combine and iterate where possible. The first combination model I would like to expand upon is one of a Deep Reinforcement Learning - Spiking Neural Network.

### Development of Multi-Timescale Representation in SNNs
Multi-timescale networks which are implementable in a spiking model such as the Legendre Memory Unit [[@voelkerLegendreMemoryUnits2019]] or FORCE training [[@nicolaSupervisedLearningSpiking2017]] will be used to develop a benchmark for testing model effectiveness for multi-timescale environments.

As SNNs are driven by temporally dependent events, understanding how these events can be used to represent multiple timescales is key. This core of the project will be focused on time representation in the dynamics of SNNs as driven by both biologically inspired and synthetic models. Particular emphasis will be placed on developing a model which is computationally dense by means of multiplexing computations of multiple timescales simultaneously.

### Development of Models Based in Multi-Timescale Task Representations in Deep Reinforcement Learning in Spiking Neural Networks 
The goal of the final stage will be to combine our learnings from previous stages, into a full model capable of associating tasks in time, for multiple time-scales. These models will be tested against a benchmark derived from our previous stages to analyze for efficiency and effectiveness.

### Implementation of Models in Neuromorphic Systems
A tertiary goal and one we hope to implement with any sufficiently developed model in our pipeline, is to test the application thereof in neuromorphic hardware as it is made available to us.

We will test our iterative models in current conventional software environments, while maintaining the goal of eventual implementation in neuromorphic hardware. Thus we will take steps to ensure our methods can easily be ported to new software environments once a suitable neuromorphic platform option has been decided on, or made available.

 We will consider and apply for use of available neuromorphic hardware platforms. This decision will need to be informed by the properties of the “production” model we decide to use, and the availability of the hardware. For instance should our model include an STDP driven mechanism, we may prefer use of hardware which natively supports such a feature.

## PhD Education
Below I have broken down my initial plans on how to fulfill the 30 ECTS credit requirement including the 10 credits of obligatory courses offered by Oslomet (PENG9100 & PENG9200).

I will fulfill 5 credits in the local course “Topics in AI” at Oslomet. I plan to fulfill another 

7.5 credits in an external course taught at the University of Agder - “IKT441 - ICT Seminar 2”, taught by Per-Arne Andersen, and covering the topic of Reinforcement Learning. I have already reached out to professor Andersen and he has made eclear the course will be offered in the Spring of 2023 and that we can tailor the course to the requirements of a PhD level course, possibly capping it with a submissible paper.

The final 7.5-10 credits I plan to acquire through attendance of summer schools. I have already enrolled in two, DeepLearn 2022 and  Machine Learning Summer School 2022, and I leave the possibility of attending further summer schools in the following years

-  5 ECTS credits - PENG9100 “Engineering Science and Ethics” 
-  5 ECTS credits - PENG9200 “Scientific Research Methods and Data Analysis”
- 7.5 ECTS credits - ICT Seminar 2 at UiA with Per-Arne Andersen
- 5 ECTS credits -  Topics in AI
- 3-6 expected ECTS credits - Deep Learn 2022
- 3-6 expected ECTS credits - MLSS^N Kraków 2022
- [Should I include Norskkurs?]


## Potential Collaborations
I will seek potential collaborations with outside labs. A potential collaboration we will initially seek is with Waterloo University and the Computational Neuroscience Research Group.  As previously mentioned, their work in multi-timescale unit implementations with SNNs appears to be closely related to my proposed work.

## Papers 
Within my first year, I aim to compile and submit a manuscript to a conference in related fields such as the Reinforcement Learning and Decision Making conference, the Neural Information Processing Systems conference, the Spiking Networks as Universal Function Approximators conference, along with several others mentioned below.

After the first paper, I aim to develop and submit two more papers to journals within the following two years. My last year will see the development of a fourth and possibly further papers depending on how much research material I have accumulated by then. Additionally, I will complete and submit my thesis during this final year.

## Conference Participation
As briefly mentioned I will seek to participate in conferences. In addition to the ones listed above, I am considering several others including:
- International Conference on Machine Learning
- AAAI Conference on Artificial Intelligence
- International Joint Conferences on Artificial Intelligence
- International Conference on Learning Representations
- International Conference on Neuromorphic Systems
- Federation of European Neuroscience Conference
- Society For Neuroscience: Neuroscience Conference

I will seek participation in these and others within possibility and relevance.

## Research Visit
Within the third or fourth year of my program I will arrange a four to six month research visit at an external university.  I will apply for a mobility fund approximately one year in advance.







