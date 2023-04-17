---
type: writing/draft
status: active
priority: p1
creationtag: 2022-05-13 10:45
infotags: proposal
---

# Introduction
## Combining Reinforcement and Deep Learning 
### Reinforcement Learning
Reinforcement Learning (RL) considers the problem of some *agent*  acting in an environment. Typically, this *environment* is some task in which the *state* of the task or environment must be interpreted and mapped to some *policy* of action by the agent. That is, the agent must optimize its interaction with the environment to achieve some maximal reward signal from the environment. 

The benefit of these schemes is their ability to “self-teach” or optimize to a task without direct supervision or input. This method is further enhanced through introduction of exploration to RL schemes, where the $\epsilon$-greedy option (the action corresponding to the highest amount reward in the current policy) is selected only with some probability. This allows for suboptimal actions to be chosen in order to fully explore the space of action-rewards, and correction to the policy to be made as needed.  The adaptability and “self-supervising” nature of this framework offers great benefits in a wide range of machine learning applications.

However, this framework comes with key limitations. Namely, the optimization of action-reward policies at different time scales. 

RL can maximize for reward within a small timescale, but will fail to optimize for multi-objective tasks at larger timescales [[50 Reading/citations/@botvinickDeepReinforcementLearning2020]]. This is in contrast to real-life models, where association between multiple objectives, rewards, and timescales may simultaneously be optimized for greater reward overall. A delayed gratification in reward in smaller time scales may often be optimal for return of maximum reward, e.g. a prey creature optimizing to scavenge at particular times in order to avoid predators. 

Further, as action and state space increases, conventional RL methods such as Q-Learning become intractable tasks. Thus, requiring a different approach to learning in environments with high-dimensional parameter spaces. 

### Deep Learning
In order to mitigate this barrier in RL, it has been combined with methods found in Deep Learning. Deep learning (DL), offers a method of simplifying and optimizing high-dimensional spaces in learning. While conventional DL methods rely on stationary gradient descent which is not implementable in RL models, variations have still been successfully integrated with RL [[@mnihHumanlevelControlDeep2015]] and further improvements are being developed [[@hesselRainbowCombiningImprovements2017-MDnotes]] [Add a more modern citation where you can find one]. 

It is worth adding, that while RL supposes a more biologically plausible model (despite still being very much, you know, *not*), DL is very much not a biologically plausible model. While a deep feed-forward networks are  seemingly able to reach brain-like problem-solving, it requires well-behaved and differentiable network functions [[50 Reading/citations/@zenkeVisualizingJointFuture2021]] to learn. 

DL introduces its own issues with time-representations. Representing time in a DL network without relying on additional and external modules, requires aspects of recurrent-ness to be introduced, however modern recurrent neural networks can not be generalized to more than a single task due to “catastrophic forgetfulness”[[@princeCurrentStateFuture2022]] [[@rolnickExperienceReplayContinual2019a]].

This is a barrier in the development of more efficient and computationally complex models.   [Eh probably delete]

### Spiking Neural Networks
Spiking Neural Networks (SNN) offer the opportunity to reinforce both DL and RL with biologically inspired mechanisms which offer several innate strengths[[@pfeifferDeepLearningSpiking2018]] [[@tavanaeiDeepLearningSpiking2019]].  SNNs promise the advantages of properties found in physical neural substrates including sparse communication, analog computation, event-driven processing, and online learning, all in asynchronous and parallel communications. [writing in circles here]

SNNs are reactive, adaptable, efficient, and computationally complex; all of which are lucrative properties in the potential hardware applications including automated driving, internet of things, robotics, and neuromorphic computing. Deep SNN models offers a potential leap in machine learning abilities.

The key and driving feature behind SNN’s is their temporal dynamics, which encode time information directly into the network behavior. Learning in SNNs rely on the timing between spikes or in reference to some reference signal, such as bursts or network oscillations [Payuer 2021 (not really there are neohebbian methods which are preferable to refer to), Montemurro et al .2008].

These these temporal dynamics are of especial interest to us, we believe the multiple timescales may be encoded in an *in-computation memory*, as exhibited timing dependent behavior at the neuronal and neuronal circuit level, contribute to multiphase oscillations at the macro and full-network levels [**CITATION NEEDED**, probably some echo state paper] . These multiple timescale representations could be utilized to encode time-dependent computations of reward and environment on the network [**CITATION NEEDED**, I don’t like this, needs a more solid footing] 

[Sorta spoke about it with Anis. He says it’s intereesting but may not be worth imcluding right now].

…..

### Challenges in DRL
A key challenge in combining DL with either RL or SNNs have problems with what is known as the *credit assignment problem* where back propagation of error in both is less than straight forward due to their inability to utilize gradient-based optimization or Back-Propagation Through Time (BPTT) as in standard DL models. Instead, an online and non-forgetful solution to reward based learning is needed. 

Plausible solutions are available [**CITATION**] to the credit assignment problem in both types of models and recent research has addressed the issue directly in Deep Reinforcement Learning with Spiking Neural Network (DRL-SNN) paradigms [[[@chenDeepReinforcementLearning2022]], MORE! ]. However, these must be expanded on for reliable use in the multi-timescale regime.

See: [[50 Reading/citations/@botvinickDeepReinforcementLearning2020]] especially the comments from Anis

End this section with the possibilities of DRLSNN
- Back Propagation issues
	- 
- Time association issues [need citations]

How can SNNs fix this ( I kinda already cover all of this above)
 I should probably focus on how SNN can be made to solve them.

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
			- 
		- 



# Research Questions
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

# Methods and Previous work 

# Research Plan
## Breakdown of Research 
Breakdown the stages of your research here.

### Research Review
At all stages, but most importantly at the seminal stage of my project, I will be updating my skills and knowledge of previous and current research being done in similar fields. Because my proposed project relies on combing several “next-generation” fields of machine learning, it is imperative I bring myself to having comfortable command of the underlying concepts and the recent developments which relate to my goals.

### Research and implementation of known methods and establishing benchmarks
I will start with implementing recent methods which offer plausible solution to our questions raised. Here I give detail a specific but incomplete list of particular implementations I will attempt to recreate in my own development environment. [maybe generalize (as you do in the next paragraph) what you will actually implement and then move the particular implementations to the **related work** section]

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
The penultimate goal, will be to combine our learnings from previous stages, into a full model capable of associating tasks in time, for multiple time-scales. These models will be tested against a benchmark derived from our previous stages to analyze for efficiency and effectiveness.

This model should be able to address the tasks/questions required of it….[and those are? Detail the possible examples in the RESEARCH QUESTION section]

- Possibly multiple papers depending on where we see the research going
- At least two or three tasks to address based on our research question
- 
### Implementation of Models in Neuromorphic Systems
A tertiary goal and one we hope to implement with any sufficient developed model in our pipeline, is to test the application thereof in neuromorphic hardware as it is made available to us.


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






