---
type:  writing/draft
status: active 
priority: p1
creationtag: 2022-05-23 13:29
infotags: latex
comments: converted from latex on overleaf
---

::: {#Introduction}
# Introduction
:::

Recent advances in machine learning methods, availability of data and
computation hardware have brought Artificial Intelligence to the center of a new industrial revolution and posits to permeate all future technologies. Advances of the last decade in robotics, self-driving cars, and the Internet of Things, all rely on supervised learning methods, in special deep learning (DL).

Supervised learning leverages labeled data to train models through examples. The goal of supervised learning is to approximate a function that maps the input variable to the targeted output so predictions, trends and classifications can be derived. 

Deep learning methods make use of networks of artificial neurons to create models able to approximate a wide range of functions. Supervised learning with deep learning enables the detection and recognition of complex patterns, which are beyond the reach of other methods in supervised learning.

Although very powerful, Supervised DL has several limitations. Because DL models depend on large human-curated datasets, these models are often costly and time-consuming to train. They demand both, great human effort to label data, as well as computational power (and therefore energy) to be deployed. Because of that, supervised DL models are often trained in times apart from inference. This severely reduces its utility to some applications that demand real-time learning. Additionally, handling temporal information is especially difficult for supervised DL models. Although several techniques have been developed to increase their ability to handle inputs with variable lengths [@hochreiterLongShortTermMemory1997] [@vaswaniAttentionAllYou2017] , these solutions rely on increasing the size of network, magnifying their
disadvantages.

In contrast, instead of learning through examples of known solutions,
reinforcement learning (RL) explores the space of possible solutions
through trial and error. RL optimizes its policies (i.e, what decision
to take as function of the input) not by reducing an error from a
targeted output, but by maximizing a feedback or teaching signal called reward. For this reason, RL models are better suited for complex
problems where solutions are hard to define. Because RL models learn sequentially, step-by-step optimizing decisions towards the
maximal accumulation of rewards, they are also better than supervised
learning at adapting quickly to unpredictable environments. 

This form of learning is akin to how animals and humans learn in natural environments to generate adaptive behaviors to overcome the challenges of the real-world. For this reason, RL is considered by some the key underlying mechanism of general intelligence [@silverRewardEnough2021].

One important challenge for RL is learning policies from rewards that
may not be presented until a substantial time after the decision that
were responsible for generating them. Although several solutions to
this problem of correctly associating actions through time have been
proposed [@hungOptimizingAgentBehavior2019], the issue remains
unresolved. And since animals and humans are the only intelligent
systems that provide evidence for a solution, several researchers
[@princeCurrentStateFuture2022] [@zenkeVisualizingJointFuture2021]
[@pfeifferDeepLearningSpiking2018] propose that the solution might
derive from biologically plausible models.

Spiking Neural Networks (SNN) might be the key to solve the time
conundrum. SNN are more biologically plausible models of the network of neurons in the brain. SNNs have two critical characteristics that makes them appealing to the problem at hand. First, they encode not only information about the input, but also when the input has happened, giving SNNs an inherent increased capability of performing temporal computations. 
Second, information is encoded and learned asynchronously,
through their dynamics. These dynamics can be further exploited not only to learn what decision to make, but also when to take these decisions.
The asynchronous characteristics is especially interesting because it
might enable parallel representations at multiple scales of time
[@nakajimaReservoirComputingTheory2021][@bellecSolutionLearningDilemma2020].

To take significant steps towards deploying features of general
intelligence in the machine, it seems clear that one must be able to
include representations about time within the model. Arbitrary temporal
representations have been tested before with limited degree of success
in supervised and reinforcement learning models. In contrast, biological
systems seem to repurpose brain areas that encode space and behavior to
derive temporal information [@patonNeuralBasisTiming2018]. In other
words, the temporal representation is learned as part of the temporal
statistics of the environment. Not only that, but they are also able to
optimize behaviors for multiple objectives in time.

In this project we aim at developing combining Deep RL models which use SNNs to learn representations of the environment and its temporal
statistics without explicit arbitrary temporal representations. The goal
is achieve through these combination of methods a model able to
represent simultaneously multiple-time-scale representations. We are
going to draw insights from neuroscience to derive SNN architectures
suitable to solve RL timing tasks. We expect that the resulting model
can not only be useful in the applied field of real-time agents, but
that the insights derived from the model can shed light on how the human brain learns in real-time.

::: {#reinforcement-learning}
## Reinforcement Learning
:::

Reinforcement Learning (RL) is one of the three pillars of Machine
Learning. RL considers the problem of an *agent* acting in an
environment aspiring to learn via trial and error an optimal behavior or
policy. Typically, the *agent* is faced with a particular task
represented by the *environment*. The *state* of the environment must be
interpreted and mapped to some action by the agent among a set of
possible actions according to a certain learned policy. That is, the
agent must optimize sequentially and over time its interaction with the
environment to achieve maximal reward signal from the environment.

The benefit of RL schemes is their ability to optimize to a task without
direct supervision or input from an outside observer. Any RL scheme
tries to maximize accumulation of rewards through a balance of
exploration and exploitation. Exploration allows for sub-optimal actions
to be chosen in order to fully explore the action space, which may lead
to discovery of actions with increased reward rate. In contrast,
exploitation permits pursuit of the best actions so far. This implies
some trade-off between exploitation and exploration, where the
opportunity to find the global maxima, diminishes exploitation of local
maxima. This adaptability of RL offers great benefits in a wide range of
machine learning applications
[@suttonReinforcementLearningIntroduction2018].

However, this framework comes with key limitations. The current
optimization of action-reward policies only operates in a single
timescale. In this sense, RL can maximize for reward within a small
timescale, but will fail to optimize for multi-objective tasks at larger
timescales [@botvinickDeepReinforcementLearning2020]. Indeed, most of
the RL schemes give more importance to immediate rewards as a
consequence to the action rather than reward what might happen further
in time. This prioritization of association between events that are
contiguous in time is also present in natural behaviors. For instance,
cycles of food availability are vital to animals which must make
time-place associations of resources which will renew over time
[@tello-ramosTimePlaceLearning2015]. But unlike animals, RL models are
unable to capture regular association between events that are widely
apart in time [@patonNeuralBasisTiming2018]. An especially interesting
challenge for RL is to learn policies that optimize for multiple
competing objectives. In most real life scenarios, reward will follow
actions by variable gaps of time, which might mean an action may be
immediately followed by a reward which in truth was given by an
unrelated action. This kind of temporal interference between competing
objectives, may occlude the relevant information used for the
associative learning. Under such conditions, to be able to navigate in
such a complex environment, the agent needs to hold multiple and
somewhat independent temporal representations of the competing
objectives. To the best of our knowledge, this form of learning is yet
under-explored.

Additionally, RL is limited to domains of limited application and
low-dimensional state spaces [@mnihHumanlevelControlDeep2015]. As the
space of environmental states and available actions increases,
conventional RL methods such as Q-Learning become intractable tasks. A
different approach, scalable to learning in environments with
high-dimensional spaces, is required. This led to the advent of Deep RL
which uses the power of Deep Learning to estimate the Q-values of
state-action pairs. The intuitive idea of Deep RL is to understand the
hidden structure of the state representation to infer the Q values even
for unexplored state action pairs.

::: {#deep-learning RL}
## Deep Learning RL {#deep-learning}
:::

Deep learning, offers a method of simplifying and optimizing
high-dimensional spaces in learning. Supervised learning methods which
use DL, rely on stationary gradient-based optimization, which is not
implementable in online RL models, nor in SNNs. Variations of DL have
been successfully integrated with RL [@mnihHumanlevelControlDeep2015]
using surrogate-gradient learning and further improvements are a field
of development [@hesselRainbowCombiningImprovements2017].

While RL supposes a more biologically plausible model of adaptation, and
learning in an unpredictable or changing environment; DL is very much a
synthetic, biologically non-plausible model. DL relies on feed-forward
networks, which while seemingly able to reach brain-like results in
problem-solving, these networks require well-behaved and differentiable
network functions to learn [@zenkeVisualizingJointFuture2021].

DL also introduces its own issues with time-representations.
Representing time in a DL network without relying on increasing network
size requires recurrent connections to be introduced. This drastically
increases the complexity of the network and imposes challenges to model
training. For instance, several recurrent connections might give rise to
vanishing or exploding gradients, which have to be handled by an extra
layer of complex solutions.

Finally, because DL relies on synchronized back propagation of error
signals, artificial neural networks can not be generalized to more than
a single task due to "catastrophic forgetfulness"
[@rolnickExperienceReplayContinual2019a]. That is, the change in weights
derived from learning a previous task, will be affected directly by
learning a posterior task. Hypothetically this interference can be
circumvented by compartmentalizing the neural network, where each
compartment handles a different task, or by introducing asynchronous
learning within the network.

::: {#spiking-neural-networks}
## Spiking Neural Networks
:::

Spiking Neural Networks (SNN) offer the opportunity to boost the
capabilities of both DL and RL. Designed on the basis of biologically
inspired mechanisms found in physical neural substrates, SNNs are
reactive, adaptable, efficient, asynchronous, and computationally
complex\[ [@pfeifferDeepLearningSpiking2018]
[@tavanaeiDeepLearningSpiking2019]\]. A comparison of spiking and
non-spiking units is given in figure 1.

SNNs are reactive and computationally efficient because of their sparse
and event-driven processing. Unlike DL where at any given time, all
neurons are outputing some scalar value. In SNNs information is
propagated by time-stamped events. Only activated neurons are outputting
trains of events while the the rest of network may rest quiet. Thus,
making SNNs particularly suited for use in applications of
energy-efficient neuromorphic hardware where reactivity to novel
environmental conditions are valued. Examples from the field include:
automated driving, internet of things, and robotics, and many possible
future technologies [@princeCurrentStateFuture2022].

In addition, and as consequence of its inner-workings, information is
encoded in the dynamics of populations of active neurons. Because of
that, SNNs are naturally suitable for online learning, and capable of
multiplexing variable sources of information in asynchronous and
parallel communications [@zenkeVisualizingJointFuture2021]. However,
these capabilities, while naturally occurring in biological models, have
yet to be fully unlocked in synthetic SNNs. Deep SNN models offer a
potential leap in machine learning abilities, and are recently regarded
as the next generation of DL [@zenkeVisualizingJointFuture2021]
[@princeCurrentStateFuture2022].

![***Fig.1:** Adapted from [@chenDeepReinforcementLearning2022]. General
spiking neural model (Top) versus a general non-spiking neural model
(Bottom). The spiking model, where at timestep $t$, $X_{t}$ is the
external input, $H_{t}$ represents the membrane voltage after neural
dynamics, $V_{t}$ represents the trigger of a spike, and $S_{t}$ is the
spike output which is 1 if there is a spike and 0 if there is no event.
Contrast with a non-spiking model. The one shown attempts to simplify
the neural model by simply passing along the membrane potential (for a
leaky integrate-and-fire neuron). The key difference between the spiking
and non-spiking network is the sparse communication in the spiking model
(where communication between nodes is off until it is "on") and in the
non-spiking model, where information between units is continuously
given.* ](f1.png){width="70%"}

The key feature behind SNN's is their temporal dynamics. By definition
of their spiking communication, SNNs encode time information directly
into their network behavior. This temporal coding is leveraged by
learning mechanism which act on different levels. On the
neuron-to-neuron level they take into account spike timing relationships
and spike burst patterns [@gerstnerEligibilityTracesPlasticity2018] ,
[@montemurroPhaseofFiringCodingNatural2008]. The well established
biological mechanism of Spike-Timing Dependent Plasticity (STDP) broadly
defines these mechanisms, and has been used to produce DL models with
back-propagation techniques for SNNs
[@payeurBurstdependentSynapticPlasticity2021].

At the whole-network level, the population behavior emergent from the
collective neuron-on-neuron timing interactions and recursive network
connections, gives rise to neural oscillations. These macro-scale
temporal dynamics may mediate information propagation within the neural
network. It is yet unclear if such oscillations are encoding any
particular information, but some researchers argue that combinations of
oscillations may be used to derive an internal temporal representation
[@guOscillatoryMultiplexingNeural2015] [@buhusiWhatMakesUs2005]. This
introspective form of information process may remove reliance on a
centralized timing mechanism by using properties of the dynamics
emergent from asynchronous information processing in parallel and
multiple timescales [@princeCurrentStateFuture2022].

These parallel macro and micro temporal dynamics are of especial
interest to us. The full scope of nested temporal dynamics could be
utilized to encode the multiple timescales representations necessary to
facilitate time-dependent learning of reward and environment conditions,
in a biologically plausible model of *in-computation memory*
\[CITATION\].

::: {#challenges-in-drl-and-drl-snns}
## Challenges in DRL and DRL-SNNs
:::

A key challenge in implementing DL in either RL or SNNs is the problem
known as the *credit assignment problem*, where back propagation of
error in both is less than straightforward due to their inability to
utilize gradient-based optimization or Back-Propagation Through Time
(BPTT) as in standard DL models. Instead, an online and non-forgetful
solution to reward based learning is needed, particularly in SNNs
[@pfeifferDeepLearningSpiking2018], [@tavanaeiDeepLearningSpiking2019] .

Plausible solutions are available to the credit assignment problem in
both DRL and RL-SNN models [@pfeifferDeepLearningSpiking2018],
[@princeCurrentStateFuture2022], and recent research has addressed the
issue directly in Deep Reinforcement Learning with Spiking Neural
Network (DRL-SNN) paradigms [@chenDeepReinforcementLearning2022].
However, these must be expanded on and developed for the multi-timescale
regime [@botvinickDeepReinforcementLearning2020].

# Research Questions

In this project, we ask how can we exploit the innate properties of
temporal dynamics found in spiking neural networks, to create a model
which can learn in a complex, time-dependent environment. In detail, the
answers we seek are the following:

→ Can we combine models of current machine learning to create a new
model which performs multi-objective learning in multiple frames of
time? → What temporal dynamics of a SNN can be used to create a model
which learn multiple timescales? → How do these representations of time
emerge in the dynamics of such a model, and how can they be modulated? →
Can we implement this model in novel neuromorphic hardware, and how
effective will its performance be? → Can we relate any novel findings in
SNN dynamics to biological models?

# Methods and Related Work

::: {#multiple-timescale-dynamics-in-snn}
## Multiple Timescale Dynamics in SNN
:::

In order to understand, associate, and respond to events and rewards in
the environment at different timescales, the system must maintain some
concept of "time" in its calculations. A number of methods have been
implemented to represent time in SNNs such as Synfire chain
[@abelesCorticonicsNeuralCircuits1991]
[@kumarSpikingActivityPropagation2010] and reservoir systems (such as
liquid state machines) [@ponulakSupervisedLearningSpiking2010], but
representing in multiple frames of time has proved a more difficult task
[@zenkeVisualizingJointFuture2021].

The FORCE training network of Nicola and Clopath 2017
[@nicolaSupervisedLearningSpiking2017], creates a network of episodic
memory, able to learn and replay the sequence of notes in a birdsong
through synchronized oscillations of the mean spiking population
activity.

Bellec et al. 2020 [@bellecSolutionLearningDilemma2020] uses a method
called *reward based E-prop* to solve the problem of time-event
association in a spiking neural network.

Yin et al. 2020 [@yinEffectiveEfficientComputation2020] uses a similar
framework for multi-timescale representation, while also optimizing for
efficiency. Both of these papers rely on a Recurrent SNN architecture,
primarily to offer a solution to the issue of credit-assignment.

A third design of interest to us, is Legendre Memory Units (LMUs)
[@voelkerLegendreMemoryUnits2019] which is also a hybrid design of
recurrent and linear layers within each unit to encode multiple temporal
dependencies. They also have been shown to exhibit "time-cell" like
behavior and have already been implemented in SNN and neuromorphic
hardware where they were able to exhibit on-chip learning.

Studies of these designs will inform the direction of implementation of
multi-timescale dynamics in our design, and present opportunities for
collaboration with these labs studying similar topics.

::: {#drl-snns}
## DRL-SNNs
:::

DRL implementation in SNNs has only recently been tested in the
literature [@tangDeepReinforcementLearning2020] , Chen et al. 2022
[@chenDeepReinforcementLearning2022] is the latest and most prominent
example in which a Deep Q-Learning Network (DQN)
[@mnihHumanlevelControlDeep2015] is implemented into a SNN to great
success when testing against a DQN in a conventional artificial neural
network, particularly in regard to energy efficiency.

::: {#credit-assignment-problem}
## Credit Assignment Problem
:::

Up until now we have already discussed several papers which have
addressed the challenges with the credit assignment problem \[
[@bellecSolutionLearningDilemma2020],[@yinEffectiveEfficientComputation2020],
[@nicolaSupervisedLearningSpiking2017]\], even in DRL-SNNs
[@chenDeepReinforcementLearning2022]. Though in SNN literature there is
still a great deal of development to be made in biologically-plausible,
*three-factor* or *NeoHebbian*, learning mechanisms
[@gerstnerEligibilityTracesPlasticity2018].

Payeur et al. 2021 [@payeurBurstdependentSynapticPlasticity2021] offer a
biologically plausible model based on spike timing dependent plasticity,
which uses a *three-factor* model to differentiate between spikes and
"events" which imply some learning signal. Isolated spikes and bursts
maintain different meanings, allowing for two information channels of
simultaneous feed-forward and feedback error flows. This dual-channel
mechanism may be useful in RL as signals propagate in real time.
Additionally, it allows for the construction of inhibitory
micro-circuits.

::: {#neuromorphic-hardware-and-snns}
## Neuromorphic Hardware and SNNs
:::

Neuromorphic hardware designed to exploit the advantages of analog
computing with many natively implementing spike-based or event-based
processing [@mehonicBraininspiredComputingNeeds2022]. The aforementioned
LMUs based networks were implemented in Intel's Loihi
[@voelkerSpikePerformanceTraining2021]. Other systems such as Spinnaker
[@furberSpiNNakerProject2014] and BrainScaleS
[@schmittNeuromorphicHardwareLoop2017] offer advantages of native STDP
based computing. Other neuromorphic systems and their strengths are
illustrated in Figure 2.

![***Fig.2:** Adapted from Mehonic et al.
2021[@mehonicBraininspiredComputingNeeds2022]. The figure describes
several neuromorphic systems and plots them in four quadrants relative
to interpretation by the author as to their reliance on digital or
analog (or mixed-analog) hardware substrate (**y-axis**) and the
research motivations driving the architecture design: biological or
synthetic models (**x-axis**) . Additionally, several properties of
these systems are listed on the right-hand side.* ](f2.png){width="70%"}

# Research Plan

**Please see Figure 3 for a brief visual summary of my PhD timetable**.\

![***Fig.3:** Visual summary and timetable of PhD project.*
](f3.png){width="100%"}

::: {#research-review}
## Research Review
:::

Most importantly at the seminal stage of my project, but still at all
stages, I will be updating my skills and knowledge of previous and
current research being done in similar fields.

Because my proposed project relies on combining several
fields at the forefront of machine learning, it is imperative I bring
myself to having comfortable command of the underlying concepts and the recent developments which relate to my goals.

::: {#research-and-implementation-of-known-methods-and-establishing-benchmarks}
## Research and implementation of known methods and establishing benchmarks
:::

I will start with implementing recent methods which offer plausible
solutions to our questions raised. Here I give a detailed but incomplete
list of particular implementations I will attempt to recreate in my own
development environment.

The project will consist of the development of a Deep Reinforcement
Learning model in a Spiking Neural Network framework. We will build this
model up from established methods in SNNs and DRL to create a basic
combined model. Using this basic model we can develop an analytic
heuristic against which to benchmark descendant models.

::: {#heuristics-in-the-field-of-drl-snn}
### Heuristics in the field of DRL-SNN
:::

There is a need for new benchmarks by which to test the efficacy of both
DRL-SNNs and multi-timescale dynamics
[@pfeifferDeepLearningSpiking2018], [@zenkeVisualizingJointFuture2021].
In much of the literature some visual or game based task is used for
testing, such as the psMNIST [@chilkuriParallelizingLegendreMemory2021]
or Atari 2600 games [@chenDeepReinforcementLearning2022]. However it is
likely we will need to develop and build off previous examples in order
to appropriately test our models as we develop them.

Tan et al. 2020 [@tanStrategyBenchmarkConverting2020] offers a new
standard by which to test DRL-SNNs which was then again picked up and
used in Chen et al. 2022. We will probably begin by using a similar
benchmark when comparing our DRL and SNN based models.

Our goal at this stage will be to replicate plausible methods and begin
envisioning benchmarks and measurements of future combination models.

::: {#development-of-drl-snn-models}
### Development of DRL-SNN Models
:::

**DRL implementations**, such as the DQN
[@mnihHumanlevelControlDeep2015] and subsequent Deep Reinforcement
Schemes [@hesselRainbowCombiningImprovements2017] will be the first
methods to replicate. This should include at least one spiking model
such as the one featured in Chen et al. 2022
[@chenDeepReinforcementLearning2022]

Recent models of the same type [@chenDeepReinforcementLearning2022] ,
[@tangDeepReinforcementLearning2020] directly address the issues of
credit assignment, but leave plenty of questions in regard to time
representation. As we develop our own DRL-SNN, we will steer its
development with the representation of time and multi-timescale
objectives at the forefront of consideration.

Credit assignment methods which are implementable in SNNs, particularly
using biologically inspired mechanisms such as timing-dependent and
neo-hebbian mechanisms will need to be tested for effectiveness and
compatibility with network architectures we choose. So I will replicate
the models found in Payeur 2021
[@payeurBurstdependentSynapticPlasticity2021] and Bellec 2020.
[@bellecSolutionLearningDilemma2020]

Once I have established methods and benchmarks from previous research, I
will begin to combine and iterate where possible. The first combination
model I would like to expand upon is one of a Deep Reinforcement
Learning - Spiking Neural Network.

::: {#development-of-multi-timescale-representation-in-snns}
### Development of Multi-Timescale Representation in SNNs
:::

Multi-timescale networks which are implementable in a spiking model such
as the Legendre Memory Unit [@voelkerLegendreMemoryUnits2019] or FORCE
training [@nicolaSupervisedLearningSpiking2017] will be used to develop
a benchmark for testing model effectiveness for multi-timescale
environments.

As SNNs are driven by temporally dependent events, understanding how
these events can be used to represent multiple timescales is key. This
core of the project will be focused on time representation in the
dynamics of SNNs as driven by both biologically inspired and synthetic
models. Particular emphasis will be placed on developing a model which
is computationally dense by means of multiplexing computations of
multiple timescales simultaneously.

::: {#development-of-models-based-in-multi-timescale-task-representations-in-deep-reinforcement-learning-in-spiking-neural-networks}
### Development of Models Based in Multi-Timescale Task Representations in Deep Reinforcement Learning in Spiking Neural Networks
:::

The goal of the final stage will be to combine our learnings from
previous stages, into a full model capable of performing associative
learning over multiple timescales. These models will be tested against a
benchmark derived from our previous stages to analyze for efficiency and
effectiveness.

::: {#implementation-of-models-in-neuromorphic-systems}
### Implementation of Models in Neuromorphic Systems
:::

A tertiary goal is to implement any sufficiently developed model within
our pipeline into neuromorphic hardware. I will iterate on models in
conventional software environments, while maintaining the goal of
eventual implementation in neuromorphic hardware. Thus I will take steps
to ensure models can easily be ported to new software environments once
a suitable neuromorphic platform option has been decided on, or made
available.

I will consider and apply for use of available neuromorphic hardware
platforms. This decision will need to be informed by the properties of
the "production" model we decide to use, and the availability of the
hardware. For instance should our model include an STDP driven
mechanism, we may prefer use of hardware which natively supports such a
feature.

::: {#phd-education}
## PhD Education
:::

Below I have broken down my initial plans on how to fulfill the 30 ECTS
credit requirement including the 10 credits of obligatory courses
offered by Oslomet (PENG9100 & PENG9200).

I will fulfill 5 credits in the local course *PENG9560 Topics in
Artificial Intelligence and Machine Learning* at Oslomet. I plan to
fulfill another 7.5 credits in an external course taught at the
University of Agder - "IKT441 - ICT Seminar 2", taught by Per-Arne
Andersen, and covering the topic of Reinforcement Learning. I have
already reached out to professor Andersen and he has made clear the
course will be offered in the Spring of 2023 and that we can tailor the
course to the requirements of a PhD level course, possibly capping it
with a submissible paper.

The final 7.5-10 credits I plan to acquire through attendance of summer
schools. I have already enrolled in two, DeepLearn 2022 and Machine
Learning Summer School 2022, and I leave the possibility of attending
further summer schools in the following years

-   5 ECTS credits - PENG9100 "Engineering Science and Ethics"

-   5 ECTS credits - PENG9200 "Scientific Research Methods and Data
    Analysis"

-   5 ECTS credits - "PENG9560 Topics in Artificial Intelligence and
    Machine Learning"

-   7.5 ECTS credits - ICT Seminar 2 at UiA with Per-Arne Andersen

-   3-6 expected ECTS credits - Deep Learn 2022

-   3-6 expected ECTS credits - MLSS\^N Kraków 2022

::: {#potential-collaborations}
## Potential Collaborations
:::

In the related works section I have mentioned several recent
implementations of models closely related to the research in DRL and
SNNs, and in my project development plan I discuss how I will be designs
and techniques off their previously established work. To accelerate the
development of these methods which I will use and build in my PhD, I
will reach out to these labs and communicate, if not collaborate, on
potential designs and for support.

To name a few potentials, the Waterloo University Computational
Neuroscience Research Group investigates similar studies in
multi-timescale units with spiking neuromorphic hardware
implementations[@voelkerSpikePerformanceTraining2021][@chilkuriParallelizingLegendreMemory2021].
Novel design of biologically plausible SNN-learning as developed by
Alexander Payeur [@payeurBurstdependentSynapticPlasticity2021] or Rui
Ponte Costa [@costaCorticalMicrocircuitsGatedrecurrent2017] are relevant
to my research and collaboration with them would be sought. The DRL-SNN
models by Ding Chen or Weihao Tan will directly inform my models, and so
I will directly be reaching out to them about their further
development[@chenDeepReinforcementLearning2022][@tanStrategyBenchmarkConverting2020].

::: {#publications}
## Publications
:::

In my first year I will write and publish a position or review paper
which establishes my scope of research and the supporting body of
relevant knowledge. This paper will serve the express purpose of
accelerating my academic development and expertise in my research topic.
A secondary goal of this publication will be the integration of myself
and my work with the community of related researchers in my field, with
whom I will network and engage for additional support and development of
my project. Initial experimental results gathered in this first year
will be published in conferences such as the Reinforcement Learning and
Decision Making conference, the Neural Information Processing Systems
conference, the Spiking Networks as Universal Function Approximators
conference, along with several potential others mentioned below.

After the first paper, I aim to develop and submit two more papers to
journals including Nature Neuroscience, IEEE Transactions on Neural
Networks and Learning Systems, and Advances in Neural Information
Processing Systems within the following two years. Additionally, I will
increase the visibility of my work in the Neuroscientific and Machine
Learning community through micro-content publication and engagement in
social networks such as Twitter; and advertisement of my research
results in science blogs and national conferences. My last year will see
the development of a fourth and possibly further papers depending on how
much research material I have accumulated by then. I will complete and
submit my thesis during this final year.

::: {#conference-participation}
## Conference Participation
:::

In addition to the conferences listed above, I am considering several
others due to their relevance, impact and networking potential,
including:

-   International Conference on Machine Learning

-   AAAI Conference on Artificial Intelligence

-   International Joint Conferences on Artificial Intelligence

-   International Conference on Learning Representations

-   International Conference on Neuromorphic Systems

-   Federation of European Neuroscience Conference

-   Society For Neuroscience: Neuroscience Conference

I will seek participation in these and others within possibility and
relevance.

::: {#research-visit}
## Research Visit
:::

Within the third year of my program I will arrange a four to six month
research visit at an external university. I will apply for a mobility
fund [from the Norwegian Research Council mobility
grant]{style="color: mypink1"} approximately one year in advance.
