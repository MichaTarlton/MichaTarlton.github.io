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
Reinforcement Learning (RL) considers the problem of some *agent*  acting in an environment. Typically, this *environment* is some task in which the *state* of the task or environment must be interpreted and mapped to some *policy* of action by the agent. That is, the agent must optimize its interaction with the environment to achieve some maximal reward signal from the environment. 

The benefit of these schemes is their ability to “self-teach” or optimize to a task without direct supervision or input. This method is further enhanced through introduction of exploration to RL schemes, where the $\epsilon$-greedy option (the action corresponding to the highest amount reward in the current policy) is selected only with some probability. This allows for sub-optimal actions to be chosen in order to fully explore the space of action-rewards, and correction to the policy to be made as needed.  The adaptability and “self-supervising” nature of this framework offers great benefits in a wide range of machine learning applications.

However, this framework comes with key limitations. Namely, the optimization of action-reward policies at different time scales. RL can maximize for reward within a small timescale, but will fail to optimize for multi-objective tasks at larger timescales [[50 Reading/citations/@botvinickDeepReinforcementLearning2020]]. 

In real-life models, where flexible association between multiple objectives, rewards, and timescales may be flexibly and simultaneously be optimized for greater reward over multiple and competing timescales. E.g. A delayed reward gratification in smaller time scales may often be optimal for return of maximum reward: a prey creature may learn to scavenge at particular times, suffering hunger in the short term, in order to avoid predator exposure in the long term. 



As the space of environmental states and available actions increases, conventional RL methods such as Q-Learning become intractable tasks. A different approach, scalable to learning in environments with high-dimensional parameter spaces is required. 

### Deep Learning
In order to mitigate this barrier, RL has been combined with Deep Learning methods. Deep learning (DL), offers a method of simplifying and optimizing high-dimensional spaces in learning. Conventional DL relies on stationary gradient-based optimization, which is not implementable in “live” RL models, nor in spiking networks. Variations on have been successfully integrated with RL [ [[@mnihHumanlevelControlDeep2015]] ] with surrogate- gradient learning[**CITATION**] and further improvements are a field of development [ [[@hesselRainbowCombiningImprovements2017-MDnotes]] ] [Add a more recent citation]. 

It is worth adding, that while RL supposes a more biologically plausible model of adaptation,  and learning in an unpredictable or changing environment; DL is very much a synthetic, non-biologically plausible model. While a deep feed-forward networks are seemingly able to reach brain-like results in problem-solving, it requires well-behaved and differentiable network functions [ [[50 Reading/citations/@zenkeVisualizingJointFuture2021]]] to learn. 

DL also introduces its own issues with time-representations. Representing time in a DL network without relying on additional and external modules, requires aspects of recurrent connections to be introduced, however modern recurrent neural networks can not be generalized to more than a single task due to “catastrophic forgetfulness”[ [[@princeCurrentStateFuture2022]] [[@rolnickExperienceReplayContinual2019a]] ].

This is a barrier in the development of more efficient and computationally complex models.   [Eh probably delete]

### Spiking Neural Networks
Spiking Neural Networks (SNN) offer the opportunity to reinforce both DL and RL. By basis of biologically inspired mechanisms found in physical neural substrates, SNNs are reactive, adaptable, efficient, and computationally complex[ [[@pfeifferDeepLearningSpiking2018]] [[@tavanaeiDeepLearningSpiking2019]]]. 

Because of the sparse analog nature of the event-driven processing, SNNs are reactive and computationally efficient, making them particularly suited for use in energy-efficient neuromorphic hardware, and with applications relying on this hardware such as automated driving, internet of things, and robotics, reactivity to novel environmental conditions are key.

In addition to this, they are naturally online learning, and capable of multiplexing processing all in asynchronous and parallel communications [**CITATION**]. However, these capabilities while found naturally in biological models, have yet to be fully unlocked in synthetic SNNs.

Deep SNN models offers a potential leap in machine learning abilities.

The key feature behind SNN’s is their temporal dynamics. 

By definition of their spiking communication, SNNs directly encode time information directly into their network behavior. 

At the neuron-to-neuron communication level, multiple dimensions of synaptic learning data can be conveyed through spike timing relationships and spike burst patterns [(placeholder, there plenty of neohebbian methods papers to refer to), Montemurro et al .2008] . 

At the whole-network level, dynamic temporal behavior arises from recursive network connections, analogous to neural oscillations, discarding reliance on a centralized clock and allowing for and multiplexed information processing in parallel and multiple timescales [ [[@princeCurrentStateFuture2022]]]. 

At the neuron-to-neuron communication level, multiple dimensions of synaptic learning data can be conveyed through spike timing relationships and spike burst patterns [(placeholder, there plenty of neohebbian methods papers to refer to), Montemurro et al .2008]. The well studied biological mechanism of Spike-Timing Dependent Plasticity (STDP) has been used in reproduction of Deep Learning back-propagation techniques for SNNs [Payuer 2021].

These temporal dynamics are of especial interest to us, as they could be utilized to encode multiple timescales representations and the time-dependent learning of reward and environment conditions [**CITATION**].

[Sorta spoke about echo / liquid state stuff with Anis. He says it’s interesting but may not be worth including right now].

### Challenges in DRL
A key challenge in implementing DL in either RL or SNNs have problems with what is known as the *credit assignment problem* where back propagation of error in both is less than straight forward due to their inability to utilize gradient-based optimization or Back-Propagation Through Time (BPTT) as in standard DL models. Instead, an online and non-forgetful solution to reward based learning is needed, particularly in SNNs [ why? **CITATION**] .  

Plausible solutions are available [**CITATION**] to the credit assignment problem in both types of models and recent research has addressed the issue directly in Deep Reinforcement Learning with Spiking Neural Network (DRL-SNN) paradigms [[[@chenDeepReinforcementLearning2022]], MORE! ]. However, these must be expanded on and developed for the multi-timescale regime.

See: [[50 Reading/citations/@botvinickDeepReinforcementLearning2020]] especially the comments from Anis





# Research Questions
The key question we want to answer, is how can multiple timescales and event associations can be represented in a viable model of reward and learning. Specifically, how can we exploit the innate properties of multifold temporal dynamics found in spiking neural networks, to model a reinforcement learning scheme capable of learning in a complex hyperspace of both time and environmental variables.

An animal agent must associate multiple frames of reference in time with actions to be taken, and potential risk / reward scenarios. Multiple objectives, with their own overlapping and nested time frames, must be considered by the animal, based on the associations and reinforcements made between the animal’s behavior and how it recognizes scales of time. 

Can these timescales be recognized by the agent? Not only is the learning dependent on association between event and time, but as well on recognition of different intervals of time. Additionally, correct association between the appropriate time interval and the relevant event must be learned. 

The association between time and events has been addressable, by machine learning methods up until now, only in short time scales and to single tasks. We ask if it is possible to create a learning method to optimize the behavior of an agent, not only  in regard to the short term, but the actions required in the short term to maximally a long term policy. 

Can we create a model, which learn simultaneous state-action optimizations for multiple reference frames of time, the same way an animal may choose its behaviors, not only on the time of day, but the time of year. Can this model correctly associate reward with actions made, not most recently, but most relevant over the whole time-space.

Assuming, we achieve our goal of encoding multiple, flexible, timescales in SNNs to amplify the abilities of DRL, we can:
→ Create a model which will self-teach
→ Do so for a large state, action, reward, and time relation space
→ Optimize for multiple objectives in both the environment and time

By result of this research, we will have developed:
→ Novel discoveries in SNN temporal dynamics
→ Novel DRL-SNN architecture design and models
→ Novel concept mechanisms to relate to biological systems and implement in neuromorphic hardware

---

How are multiple timescales are represented in SNNs
→ If we can create a viable model of this we can use it to amplify the abilities of DRL-SNNs
→ then we have a model which can:
- self-teach (RL)
- do so for a large input-output space (DL)
- teach itself for multiple objectives in space and time (SNN temporal dynamics)
→ And the novel discoveries we will make in result
- novel methods in SNN temporal dynamics
	- efficient in-computation memory
- novel methods for DRL-SNNs
	- credit assignment
- novel model of biological mechanisms

## Task - Time Representation in Spiking Neural Networks over Multiple Time Scales
Because of SNNs are driven by temporally dependent mechanisms, unlocking the full potential of such networks will require deeper understanding and development of said mechanisms. The project we propose here is to develop and expand on how these temporal mechanisms work in relation to the following: 
- time - event relationships in multiple time scales
-  Is there more? That sorta covers it
- But if we want to break that down into subparts
	- Event association at multiple timescales
		- “short term association is easy. Long term is harder.”
		- Multi-time-objectives.
		- Optimizing multiple tasks in time
		- Simultaneous State-Action associations at multiple timescales
			- day/night foraging in different seasons
			- Further nested / overlapped timescales with associate state and action mappings
				- we must assume non-static environment, but instead timespace as another overlapped manifold to the environment state - action mapping 


Can we train DRL models which can learn for different time scales and adapt to changes in the environment using the multiscale temporal dynamics of SNNs
- Can we encode associations with multiple time scales into the “state” of the network
	- That is, can we rely on “in-computation” memory to encode optimal network configurations
- Can we effectively utilize “recurrent-ness” in a network to effect an echo state memory
- Can we effectively utilize properties of spiking networks (and particularly spike timing properties) to…
	-  train the network without running into previous issues with back propagation
		- STDP 
		- see proposed solutions
	- encode memory into the spiking phases
- Can we build a model which scales

Our model needs to:
	Utilize spike-timing properties in an SNN to train offline to a task defined by a dynamical reward environment. The task environment in which the model network learns, may change over time, and in the response the network must retain a “memory” of previous optimizations to inform future optimizations. 
- need to reword this especially in regards to memory, but I maintain this is still what we want, where the association with “seasons” would be optimization for a memory of a certain “timescale”

# What is my “position”

1. Spiking neural dynamics are temporally driven
2. These temporally driven dynamics exhibit micro-properties, which can give rise to macro-properties and multi-timescale resolutions in a greater gestalt
3. These properties should be studied and developed for implementation in SNNs with Deep RL models


# Methods and Related Work 
## Multiple Time-Scale Dynamics in SNN
In order to understand, associate, and respond to events and rewards in the environment at different timescales, the system must maintain some concept of “time” in it’s calculations. A number of methods of including this in RL systems have been used. 
- References  needed: 
	- synfire chains, 
	- rolling windows (need more like this of time/memories in conventional systems), 
	- dynamical temporal behavior in RNNs (echos and liquid states)
- System must retain some sense of time in order to “observe” these changes 
- The SNUFA paper Zenke 2021, talks about this extensively
 ### [[Voelker & Eliasmith 2018]]
 ### [[Voelkner 2019]]

### LMUs
- Implemented in SNNs
- and on Neuromorphic hardware
- further, mention **on-chip learning** so how does that relate to RL?
### Echo State Networks / Liquid State Networks
- Elicit memory through recurrent network phases 

## Credit Assignment Problem
- NeoHebbian Deep Learning
- Talk about the challenge with the Credit Assignment Problem in SNNs
- STDP
	- Relation to temporal conditions of the network
-  go through SNUFA paper again and reiterate methods
- In the *Linking normative and biologically plausible plasticity models* section 
- **A number of non bio plausible alternatives in this, maybe just say we are picking out some highlights*

### FORCE Training algo - Nicola and Clopath 2017
- One of the first to address this problem

### [Frémaux and Gerstner, 2016](https://www.frontiersin.org/articles/10.3389/fncir.2018.00053/full#B38)
### [[Gerstner et al. 2018]]
### Bellec 2020
- Reiterate importance of temporal dynamics
-  Mentioned in the SNUFA paper as offering a bio plausible solution to the spatial credit problem
###  [[Payeur et al. 2021]]
- Eligibility traces
	- Gerstner 2018
	- Biologicallyplausible but not as favorable in
- The dual channel method may be useful for RL as the learning signals propagate in real time
- Point out its implementation of inhibitory microcircuits
	- Isolated Spike and Bursts maintain different meaning, allowing for two information channels
	- Allowing each neuron to have simultaneous feed-forward and feedback error flows

## Neuromorphic Hardware and SNNs
- More Voelkner and Eliasmith to look at
 - [[Mehonic 2021]]
	- Perhaps could borrow figure 2 from there. However I would not like for that to be the only figure I use if any.
- using Intel neuromorphic hardware
- Loihi, Spinnaker, or Brainscales
	- Loihi has been used for LMUs
	- STDP in sppinaker and Brainscales
- Exploiting new Memresistor hardwares? 


# Research Plan
## Breakdown of Research 
### Research Review
Most importantly at the seminal stage of my project, but still at all stages, I will be updating my skills and knowledge of previous and current research being done in similar fields. 

Because my proposed project relies on combing several “next-generation” fields of machine learning, it is imperative I bring myself to having comfortable command of the underlying concepts and the recent developments which relate to my goals.

### Research and implementation of known methods and establishing benchmarks
I will start with implementing recent methods which offer plausible solution to our questions raised. Here I give a detailed but incomplete list of particular implementations I will attempt to recreate in my own development environment. 

The project will consist of the development of a Deep Reinforcement Learning model in a Spiking Neural Network framework. We will build this model up from established methods in SNNs and DRL to create a basic combined model. Using this basic model we can develop a analytic heuristic against which to benchmark descendant models.

#### Heuristics in the field of Spiking DRL NN
- Write a bit about the need for a heuristic by which to test the effectiveness of our model
- there is need for new benchmarks - Pfeiffer 2018
- See papers which describe the need for new heuritics specific to DL SNNs [Pfeiffer 2018, Prince, SNUFA paper all mention it]
- Using the MNIST on current DL
- What is typically used in RL for testing?

Three main points of replicating previous work will be:
#### **Deep-Reinforcement Learning Networks**
**DRL implementations**, such as the DQN [***CITATION***] and subsequent Deep Reinforcement Schemes such as [ADD EXAMPLES and CITATION] will be the first methods to replicate. This should include at least one spiking model such as the one featured in Chen et al. 2022 [[@chenDeepReinforcementLearning2022]]

#### **Multi-Timescale Representation**
Multi-Timescale networks, such as the Legendre Memory Unit [[@voelkerLegendreMemoryUnits2019]] which also benefits us from being implementable in a spiking model. This allows us to develop a benchmark for testing model effectiveness for multi-timescale environment.

#### Biologically inspired SNN credit assignment
Credit assignment methods which are implementable in SNNs, particularly using biologically inspired mechanisms such as timing-dependent and neo-hebbian mechanisms will need to be tested for effectiveness and compatibility with network architectures we choose. So I will replicate the models found in Payuer 2021 [[@williamsNeuralBurstCodes2021]] and Bellec 2020. [[@bellecSolutionLearningDilemma2020]]

Our goal at this stage will be to replicate plausible methods and begin envisioning benchmarks and measurements of future combination models.

### Development of DRL-SNN Models
Once I have established methods and benchmarks from previous research, I will begin to combine and iterate where possible. The first combination model I would like to expand upon is one of a Deep Reinforcement Learning - Spiking Neural Network.

Recent models of the same type [ [[@chenDeepReinforcementLearning2022]]  , **seek others** ] directly address the issues of credit assignment, but leave plenty of questions particularly in regards to time representation [do they though?]. As we develop our own DRL-SNN, we will steer its development with the representation of time and multi-timescale objectives at the forefront of consideration.

### Development of Multi-Timescale Representation in SNNs
As SNNs are driven by temporally dependent events, understanding how these events can be used to represent multiple timescales is key. This core of the project will be focused on time representation in the dynamics of SNNs as driven by both a biologically inspired and synthetic models. Particular emphasis will be placed on developing a model which is computationally dense by means of multiplexing computations of multiple timescales simultaneously.

### Development of Models Based in Muli-Timescale Task Representations in Deep Reinforcement Learning in Spiking Neural Networks 
The goal of the final stage, will be to combine our learnings from previous stages, into a full model capable of associating tasks in time, for multiple time-scales. These models will be tested against a benchmark derived from our previous stages to analyze for efficiency and effectiveness.

This model should be able to address the tasks/questions required of it….[and those are? Detail the possible examples in the RESEARCH QUESTION section]

- Possibly multiple papers depending on where we see the research going
- At least two or three tasks to address based on our research question
---

In establishing a combined model, we can then iterate on the minute mechanics of the model which will be more open to experimentation. This will include the shape of the network architectures, node unit structure and mechanisms, and methods of credit assignment throughout the network.
- Network Architecture
	- Perhaps best to begin with simple feed-forward with back propagation 
	- Recurrent network architectures next
		- Though this may also be implemented on the “nodal” basis. See LMUs.
	- Possible hierarchical structures
		- Global signals such as “dopamine” simulation
		- Because of sparse, low saturation of the network, small world or pseudo-fully connected models may be viable
- Nodal Units
	- This may overlap considerably with methods of credit assignment as STDP type learning is self-contained
	- LMUs
	- Payeur three factor STDP neurons
	- Other timing based units 
	- Honestly designing our own would be dope
		- Though I’m initially inclined towards some STDP + LMU type situation

### Implementation of Models in Neuromorphic Systems
A tertiary goal and one we hope to implement with any sufficient developed model in our pipeline, is to test the application thereof in neuromorphic hardware as it is made available to us.

We will test our iterative models in current conventional software environments, while maintaining the goal of eventual implementation in neuromorphic hardware. Thus we will take steps to ensure our methods can easily be ported to new software environments once a suitable neuromorphic platform option has been decided on, or made available.

 We will consider and apply for use of available neuromorphic hardware platforms. This decision will need to be informed by the properties of the “production” model we decide to use, and the availability of the hardware. For instance should our model include an STDP driven mechanism, we may prefer use of hardware which natively supports such a feature.

## PhD Education
Below I have broken down my initial plans on how to fulfill the 30 ECTS credit requirement including the 10 credits of obligatory courses offered by Oslomet (PENG9100 & PENG9200).

I will fulfill 5 credits in the local course “Topics in AI” at Oslomet. I plan to fulfill another 

7.5 credits in an external course taught at the University of Agder - “IKT441 - ICT Seminar 2”, taught by Per-Arne Andersen, and covering the topic of Reinforcement Learning. I have already reached out to professor Andersen and he has mad eclear the course will be offered in the Spring of 2023 and that we can tailor the course to the requirements of a PhD level course, possibly capping it with a submissible paper.

The final 7.5-10 credits I plan to acquire through attendance of summer schools. I have already enrolled in two, DeepLearn 2022 and  Machine Learning Summer School 2022, and I leave the possibility of attending further summer schools in the following years

-  5 ECTS credits - PENG9100 “Engineering Science and Ethics” 
-  5 ECTS credits - PENG9200 “Scientific Research Methods and Data Analysis”
- 7.5 ECTS credits - ICT Seminar 2 at UiA with Per-Arne Andersen
- 5 ECTS credits -  Topics in AI
- 3-6 expected ECTS credits - Deep Learn 2022
- 3-6 expected ECTS credits - MLSS^N Kraków 2022
- [Should I include Norskkurs?]


## Potential Collaborations
I will seek potential collaborations with outside labs. A potential collaboration we will initially seek is with Waterloo University and the Computational Neuroscience Research Group.  As previously mentioned, their work in multi-timescale unit implementations with SNNs appears to be closely related to my proposed work [CITATION?].

## Papers 
I aim to within my first year compile and submit a manuscript to a conference in related fields such as the Reinforcement Learning and Decision Making conference, the Neural Information Processing Systems conference, the Spiking Networks as Universal Function Approximators conference, along with several others mentioned below.

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
Within the third or fourth year of my program I will arrange a four to six month research visit at an external university.  I will apply for a mobility fund approximately one year in advance.[]






