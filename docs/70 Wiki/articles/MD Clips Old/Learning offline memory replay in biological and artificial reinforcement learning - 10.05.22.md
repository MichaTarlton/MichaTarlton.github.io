---
created: 2022-05-10T18:43:18 (UTC +02:00)
tags: []
source: https://www.sciencedirect.com/science/article/pii/S0166223621001442
author: 
---

# Learning offline: memory replay in biological and artificial reinforcement learning - ScienceDirect



> ## Excerpt
> Learning to act in an environment to maximise rewards is among the brain’s key functions. This process has often been conceptualised within the framew…

---
[![Elsevier logo](https://sdfestaticassets-us-east-1.sciencedirectassets.com/shared-assets/24/images/elsevier-non-solus-new-grey.svg)](https://www.sciencedirect.com/)

-   [View **PDF**](https://www.sciencedirect.com/science/article/pii/S0166223621001442/pdfft?md5=657553b537dc1d674765b24387b2ad6f&pid=1-s2.0-S0166223621001442-main.pdf)

## Outline

1.  [Highlights](https://www.sciencedirect.com/science/article/pii/S0166223621001442#ab0010 "Highlights")
2.  [Keywords](https://www.sciencedirect.com/science/article/pii/S0166223621001442#ks0005 "Keywords")
3.  [Replay in biological and artificial reinforcement learning](https://www.sciencedirect.com/science/article/pii/S0166223621001442#s0005 "Replay in biological and artificial reinforcement learning")
4.  [Uniform experience replay and its origins in neuroscience](https://www.sciencedirect.com/science/article/pii/S0166223621001442#s0010 "Uniform experience replay and its origins in neuroscience")
5.  [Prioritised experience replay](https://www.sciencedirect.com/science/article/pii/S0166223621001442#s0015 "Prioritised experience replay")
6.  [Memory buffer as a limitation of replay](https://www.sciencedirect.com/science/article/pii/S0166223621001442#s0020 "Memory buffer as a limitation of replay")
7.  [Generative replay](https://www.sciencedirect.com/science/article/pii/S0166223621001442#s0025 "Generative replay")
8.  [Future directions](https://www.sciencedirect.com/science/article/pii/S0166223621001442#s0030 "Future directions")
9.  [Concluding remarks](https://www.sciencedirect.com/science/article/pii/S0166223621001442#s0035 "Concluding remarks")
10.  [Acknowledgements](https://www.sciencedirect.com/science/article/pii/S0166223621001442#s0040 "Acknowledgements")
11.  [Declaration of interests](https://www.sciencedirect.com/science/article/pii/S0166223621001442#s0045 "Declaration of interests")
12.  [References](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bi0005 "References")
13.  [Glossary](https://www.sciencedirect.com/science/article/pii/S0166223621001442#gl0005 "Glossary")

## Figures (3)

1.  [
    
    ![Figure 1. Replay of hippocampal place cells](https://ars.els-cdn.com/content/image/1-s2.0-S0166223621001442-gr1.sml)
    
    ](https://www.sciencedirect.com/science/article/pii/S0166223621001442#f0005)
2.  [
    
    ![Figure 2. Deep Q network (DQN) with memory buffer](https://ars.els-cdn.com/content/image/1-s2.0-S0166223621001442-gr2.sml)
    
    ](https://www.sciencedirect.com/science/article/pii/S0166223621001442#f0010)
3.  [
    
    ![Figure 3. Biological and artificial generative replay](https://ars.els-cdn.com/content/image/1-s2.0-S0166223621001442-gr3.sml)
    
    ](https://www.sciencedirect.com/science/article/pii/S0166223621001442#f0015)

[![Journal home page for Trends in Neurosciences](https://ars.els-cdn.com/content/image/Dcellpress.gif)](https://www.sciencedirect.com/journal/trends-in-neurosciences/vol/44/issue/10)

## Highlights

Reinforcement learning in deep neural networks often relies on the interleaving of new and old episodes, a technique which mimics the replay of neuronal activity in the brain.

Biological replay is important for memory consolidation and has wider roles in other cognitive processes such as planning and generalisation. Deep neural networks offer a framework for understanding the role of replay in learning and memory.

We suggest how recent developments could be leveraged to support more robust, efficient, and flexible reinforcement learning agents by avoiding explicit storage of past trials.

Theoretical advances and more sophisticated experimental task designs will help uncover how biological replay supports complex cognition over time and throughout the brain.

Learning to act in an environment to maximise rewards is among the brain’s key functions. This process has often been conceptualised within the framework of reinforcement learning, which has also gained prominence in machine learning and artificial intelligence (AI) as a way to optimise decision making. A common aspect of both biological and machine reinforcement learning is the reactivation of previously experienced episodes, referred to as replay. Replay is important for memory consolidation in biological neural networks and is key to stabilising learning in deep neural networks. Here, we review recent developments concerning the functional roles of replay in the fields of neuroscience and AI. Complementary progress suggests how replay might support learning processes, including generalisation and continual learning, affording opportunities to transfer knowledge across the two fields to advance the understanding of biological and artificial learning and memory.

-   [**Previous**](https://www.sciencedirect.com/science/article/pii/S0166223621001648)
-   [**Next**](https://www.sciencedirect.com/science/article/pii/S0166223621001594)

## Keywords

computation

deep neural networks

hippocampus

Q-learning

reward

## Replay in biological and artificial reinforcement learning

Research into **reinforcement learning** (see [Glossary](https://www.sciencedirect.com/science/article/pii/S0166223621001442#gs0005)) in biology, psychology, and AI has a long and symbiotic history \[[1](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0005)\]. In recent years, **deep reinforcement learning** has shown remarkable success in problems previously thought intractable. Key to the success of these algorithms is the practice of interleaving new trials with old ones, a technique known as **experience replay** \[[2](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0010)\], and an example of convergence between biological and artificial neural networks. Replay has proved important for cognitive theories of memory \[[3](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0015)\] and the importance of replay in deep reinforcement learning supports the theory that ‘offline’ activity can aid learning and memory, raising general computational principles through which this can be achieved by any intelligent system. The relative ease of manipulating replay in artificial systems compared with biological brains means that advances in deep reinforcement learning can offer useful test cases for neuroscientists. Meanwhile, the continuing search for ever-better learning algorithms in AI could be informed by recent neurobiological insights into how self-organised activity can lead to selective strengthening or weakening of specific memories \[[4.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0020), [5.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0025), [6.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0030), [7.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0035), [8.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0040)\], generalisation from individual experiences to abstract knowledge \[[9](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0045)\], and, more generally, flexible adaptation to a changing world \[[10.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0050), [11.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0055), [12.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0060), [13.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0065)\].

Here, we review recent developments in both fields. We discuss the successes of uniform experience replay and prioritised experience replay in AI, reviewing analogous neurobiological phenomena evident in rodent and human experiments. Our review converges on the proposal that methods which avoid explicit storage of past trials and generate their own replay samples may better reflect biological processes and hold the key to flexible reinforcement learning.

## Uniform experience replay and its origins in neuroscience

Reinforcement learning in AI was developed in the mid-20th century, taking inspiration from earlier animal behaviour research \[[1](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0005)\]. In training reinforcement learning algorithms, an artificial agent collects data samples through continuous interaction with a real or simulated world, learning policies for selecting actions given the state of the environment in a way that maximises a reward function. Given limited online experience, learning can be accelerated by storing past experiences and subsequently sampling from them repeatedly, in effect to increase the training set.

Experience replay first appeared in the AI literature in the early 1990s as a means to achieve such an increase \[[2](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0010)\] ([Box 1](https://www.sciencedirect.com/science/article/pii/S0166223621001442#b0005)) and grew in popularity with the advent of deep reinforcement learning and its applications to Atari games and Go in the early 2010s \[[14](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0070),[15](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0075)\]. Independently, a series of neurophysiology studies beginning in the 1980s and 1990s found a similar phenomenon of reusing past experience in the mammalian brain (see [Figure 1](https://www.sciencedirect.com/science/article/pii/S0166223621001442#f0005) and [Box 2](https://www.sciencedirect.com/science/article/pii/S0166223621001442#b0010), and recent reviews for more detail \[[3](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0015),[16.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0080), [17.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0085), [18.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0090), [19.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0095)\]). These neuroscientific replay studies unveiled, among other insights, potential mechanisms of sleep-dependent **memory consolidation**, with replay providing a cellular basis for the long-standing observation that sleep supports memory \[[20](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0100)\].

Box 1

Experience replay in artificial intelligence

In discrete time sequences, incoming data samples are usually represented in the form of an **experience tuple**, consisting of a state *s* at time step *t*, action *a* performed at time step *t*, reward *r* obtained at time step *t*, and the next state *s**t*+1 at next time step *t* + 1. This experience tuple is first stored in a buffer and, during the learning phase, samples are randomly drawn in mini-batch from this buffer uniformly.

In deep Q networks, these mini-batch samples are then used to learn the agent’s Q-value function, the expected future reward associated with each pair of states and actions, using off-policy Q-learning. The Q-value function is policy-dependent as it relies on data collected resulting from the agent’s actions derived from its policy (behaviour). In the tabular setting, this Q-value function can be represented by a table of size ∣*S* ∣  ×  ∣ *A*∣, where ∣*S*∣ is the number of states and ∣*A*∣ is the number of actions in the environment. It is defined as:\[I\]$<math><msup is="true"><mi is="true">Q</mi><mi is="true">π</mi></msup><mfenced open="(" close=")" separators="," is="true"><mi is="true">s</mi><mi is="true">a</mi></mfenced><mo linebreak="goodbreak" is="true">=</mo><msub is="true"><mi is="true">E</mi><mi is="true">π</mi></msub><mfenced open="[" close="]" separators="|," is="true"><mrow is="true"><msub is="true"><mi is="true">r</mi><mn is="true">1</mn></msub><mo linebreak="badbreak" is="true">+</mo><msub is="true"><mrow is="true"><mi mathvariant="italic" is="true">γ</mi><mi is="true">r</mi></mrow><mn is="true">2</mn></msub><mo linebreak="badbreak" is="true">+</mo><msup is="true"><mi is="true">γ</mi><mn is="true">2</mn></msup><msub is="true"><mi is="true">r</mi><mn is="true">3</mn></msub><mo linebreak="badbreak" is="true">+</mo><mo is="true">…</mo></mrow><mrow is="true"><msub is="true"><mi is="true">s</mi><mn is="true">0</mn></msub><mo linebreak="goodbreak" is="true">=</mo><mi is="true">s</mi></mrow><mrow is="true"><msub is="true"><mi is="true">a</mi><mn is="true">0</mn></msub><mo linebreak="goodbreak" is="true">=</mo><mi is="true">a</mi></mrow></mfenced></math>$

where *γ* is the discount factor that controls how much the agent prioritises immediate rewards against long-term rewards. The off-policy update rule for the Q-value function is:\[II\]$<math><mi is="true">Q</mi><mfenced open="(" close=")" separators="," is="true"><mi is="true">s</mi><mi is="true">a</mi></mfenced><mo is="true">←</mo><mi is="true">Q</mi><mfenced open="(" close=")" separators="," is="true"><mi is="true">s</mi><mi is="true">a</mi></mfenced><mo linebreak="badbreak" is="true">+</mo><mi is="true">α</mi><mfenced open="[" close="]" is="true"><mrow is="true"><msub is="true"><mi is="true">r</mi><mrow is="true"><mi is="true">t</mi><mo is="true">+</mo><mn is="true">1</mn></mrow></msub><mo linebreak="badbreak" is="true">+</mo><mi is="true">γ</mi><msub is="true"><mo mathvariant="italic" is="true">max</mo><msup is="true"><mi is="true">a</mi><mo is="true">′</mo></msup></msub><mi is="true">Q</mi><mfenced open="(" close=")" separators="," is="true"><msup is="true"><mi is="true">s</mi><mo is="true">′</mo></msup><msup is="true"><mi is="true">a</mi><mo is="true">′</mo></msup></mfenced><mo linebreak="badbreak" is="true">−</mo><mi is="true">Q</mi><mfenced open="(" close=")" separators="," is="true"><mi is="true">s</mi><mi is="true">a</mi></mfenced></mrow></mfenced></math>$

where *α* is the learning rate. The Q-value function is said to have been completely learnt when its values have converged.

As the agent continuously explores the environment and collects data samples, sooner or later the buffer will become full and the oldest samples will be replaced by newer samples. This strikes a balance between learning the most recent samples and allowing older samples to ‘live’ longer than they usually would, such as in the classical online learning setting. Experience replay has shown to improve the learning efficiency of artificial agents \[[105](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0525)\].

![Figure 1](https://ars.els-cdn.com/content/image/1-s2.0-S0166223621001442-gr1.jpg)

1.  [Download : Download high-res image (275KB)](https://ars.els-cdn.com/content/image/1-s2.0-S0166223621001442-gr1_lrg.jpg "Download high-res image (275KB)")
2.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S0166223621001442-gr1.jpg "Download full-size image")

Figure 1. Replay of hippocampal place cells.

Replay of hippocampal place cells during a single lap of a linear track. (A) Spiking of place cells during a sharp-wave ripple, representing a forward replay. (B) Sequential spiking of place cells that encode successive locations on the track; colours represent the location on the track to which the cell is tuned. Black trace at the top shows concurrent local field potential. Red and blue boxes outline bursts of spiking, which are magnified in A and C, respectively. (C) Spiking of place cells during a sharp-wave ripple, representing a reverse replay. (D) Animal’s running velocity, including periods of immobility before and after the run. Figure adapted from \[[119](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0595)\].

Box 2

Hippocampal replay

Pyramidal neurons in the hippocampus exhibit spatial receptive fields: their firing rate increases by as much as tenfold when the animal is in a particular location \[[106](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0530)\]. Taken together, such ‘**place cells**’ have been proposed to form a cognitive map of an environment from which an animal may be able to plan routes, find shortcuts, and make other inference. As the animal traverses a room or a habitat, the sequence of increased firing rates of one place cell after another can provide a read-out of the animal’s trajectory through the environment \[[29](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0145)\]. Following earlier predictions \[[107](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0535),[108](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0540)\], a series of studies in the 1990s showed that pairs of place cells that were coactive during behaviour (i.e., encoding overlapping or adjacent locations on a maze) became coactive again when the animal was taken away from the maze and left to rest or sleep in one place \[[31.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0155), [32.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0160), [33.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0165), [34.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0170)\]. This reactivation of place cell pairs was above both the level of chance and the level of their coactivation during rest before exploring the environment; that is to say that the hippocampal trace of previous behaviour was being replayed during rest, when the animal was not running or exploring and the hippocampus was otherwise unengaged with the task of navigation ([Figure 1](https://www.sciencedirect.com/science/article/pii/S0166223621001442#f0005)).

Further research has shown that such replay extends outside the hippocampus to cortical \[[35.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0175), [36.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0180), [37.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0185)\] and limbic \[[38.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0190), [39.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0195), [40.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0200)\] brain areas, which are involved in processing nonspatial information, suggesting a brain-wide phenomenon in which many facets of an experience, including sensory and reward-related properties, can be reactivated together.

In humans, the noninvasive, nonsurgical experimental methods usually required for recording neural activity offer lower spatial and temporal resolution, making replay detection more difficult. Nevertheless, classifiers trained on human neural activity during a task show hippocampal reactivation of task representations during subsequent rest, with a bias towards replaying items that are highly rewarded and subsequently better remembered \[[109](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0545),[110](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0550)\]. Replay has also been shown to selectively strengthen weaker memories \[[111](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0555)\] and re-evaluate state-action values for reinforcement learning \[[13](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0065)\] and with tentative evidence of hippocampal-to-cortical transfer of task-relevant information \[[112](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0560)\].

Evidence for the causal role of replay in memory consolidation has come from studies in which sharp-wave ripples in the hippocampus are either disrupted or prolonged. Hippocampal replay relies on synchronous excitation of large neuronal populations, which occurs during sharp-wave ripples \[[31](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0155)\]: distinctive, transient bursts of high-frequency oscillatory activity \[[113](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0565)\] that promotes the firing of a subset of pyramidal cells, resulting in replay sequences \[[26](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0130),[27](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0135)\]. Disrupting the ripples, which also disrupts coincident replay events, results in slower spatial learning on timescales of minutes \[[4](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0020),[5](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0025),[10](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0050)\], and days \[[41](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0205),[42](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0210)\]. Disrupting the replay event but not the ripple itself (technically a much harder feat) has also been shown to slow down learning \[[43](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0215)\]. Extending the duration of ripples, conversely, appears to increase replay and improve spatial memory \[[5](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0025)\]. Finally, studies that invoke or bias replay of some experiences over others can selectively improve the memory of those items \[[6.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0030), [7.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0035), [8.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0040),[44](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0220)\]. The definitive evidence for a link between replay and memory consolidation would be performance improvement following the induction of a replay event from scratch. Such a test, however, is technically challenging and to our knowledge has not been achieved experimentally so far.

How does replay improve memory? One of the leading hypotheses is that replay induces Hebbian **plasticity** between the cells being replayed \[[21.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0105), [22.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0110), [23.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0115), [24.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0120), [25.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0125)\], thereby strengthening their synaptic connections. Replay events, particularly during non-rapid eye movement (**non-REM**) **sleep**, typically reiterate neural patterns on a faster timescale than during the original experience \[[26.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0130), [27.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0135), [28.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0140)\], which might further encourage spike-timing-dependent plasticity \[[21](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0105)\]; one could call this the ‘offloading plasticity until later’ theory of how replay supports memory consolidation. However, while the importance of replay for spatial (hippocampus-dependent) memory has been established, questions remain about which aspects of the experience are represented in replayed activity, how replay patterns propagate through the brain, and the roles of replay in wider cognitive processes.

Computational studies have suggested functions for replay that extend beyond memory consolidation ([Box 3](https://www.sciencedirect.com/science/article/pii/S0166223621001442#b0015)). The complementary learning systems theory has used the so-called ‘penguin problem’ to illustrate the necessity of maintaining a network that is stable enough for acquired knowledge to persist, but plastic enough to incorporate new knowledge \[[29](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0145)\]. In this illustration, a network was trained to classify living things from their characteristics, before being presented with an anomalous semi-aquatic bird (the penguin) that has feathers and wings like a bird, but does not fly and swims like a fish. Updating the connection weights to incorporate this new information disrupted and worsened performance for other birds \[[29](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0145)\]. The proposed solution was replay, interleaving training of the new item (penguin) with older, similar items (other birds); this proved sufficient to maintain both representations without interference. One could call this the ‘preventing **catastrophic interference**’ theory of how replay improves memory consolidation, an idea that dates back to connectionist models early in the history of artificial neural networks \[[30](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0150)\].

Box 3

Proposed computational functions of replay

Replay has been proposed to serve a variety of cognitive and network functions for learning, some of which depend biologically on brain area and sleep–wake state (during behaviour, extended rest, rapid eye movement (REM) sleep, or non-REM sleep). The theories and perspectives outlined briefly in the following bullet points are not mutually exclusive and some of them are not unique to reinforcement learning, but they suggest how replay can support learning from individual rewarded episodes.

•

Consolidation of new memories rapidly encoded by a fast learner (the hippocampus) into long-term storage in a slow learner (the cortex) \[[57](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0285)\]. Memory encoding can form rapidly in the hippocampus but takes longer to be integrated into cortical representations (but see \[[114](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0570),[115](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0575)\]). Replay serves as additional training to supplement online learning, in order to strengthen cortical representations \[[116](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0580)\].

•

Generalising across episodes. Representations formed quickly and sparsely, for example, in the hippocampus enable pattern separation, which is beneficial for one-shot learning or retention of individual episodes of experience, but poorly suited to generalising across episodes. By contrast, a slower-learning cortex can integrate multiple episodes and encode statistical regularities between them, but takes many examples to achieve this (but see \[[117](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0585)\]). Replay serves as additional training for the cortex from individual episodes initiated by the hippocampus.

•

Preventing catastrophic interference. Gradual interleaving of online and offline information regularises synaptic changes or weight changes to ensure that network representations of older information are not supplanted by those of newer information \[[30](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0150),[57](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0285)\].

•

Stabilising learning. Experiences close in time tend to be correlated, which can result in large, fluctuating weight changes. Interleaving uncorrelated samples constrains weight changes for more stable learning \[[57](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0285),[118](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0590)\].

Models of replay are often concerned with its role in reinforcement learning. Although biological replay is discussed commonly in terms of episodic memory consolidation and the integration of new memory traces into long-term storage \[[3](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0015),[16.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0080), [17.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0085), [18.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0090), [19.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0095),[29](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0145),[31.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0155), [32.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0160), [33.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0165), [34.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0170), [35.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0175), [36.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0180), [37.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0185)\], evidence from animal studies usually comes from spatial navigation tasks in which food rewards or electrical brain stimulation are used to reinforce exploration and navigation of an environment \[[4](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0020),[5](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0025),[8](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0040),[10.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0050), [11.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0055), [12.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0060),[26](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0130),[27](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0135),[29](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0145),[31.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0155), [32.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0160), [33.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0165), [34.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0170), [35.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0175), [36.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0180), [37.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0185), [38.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0190), [39.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0195), [40.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0200), [41.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0205), [42.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0210), [43.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0215), [44.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0220), [45.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0225), [46.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0230), [47.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0235), [48.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0240)\]. The additional plasticity that replay incurs may itself reinforce habitual behaviours that are driven by the replayed activity patterns \[[39](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0195)\]. Replay of activity in the hippocampus alone is necessary for stabilising newly formed representations of the environment, ensuring that learned **state transitions** are maintained for subsequent visits \[[49](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0245),[50](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0250)\]. In addition, the recruitment of other brain areas that are involved in evaluating likely outcomes and rewards during replay may promote further updating of stored action values or state values in neural reinforcement learning circuits \[[13](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0065),[40](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0200),[48](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0240),[51](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0255)\].

These two functional roles of replay (preventing catastrophic interference and facilitating reinforcement learning) are particularly relevant for deep reinforcement learning. The fact that the use of experience replay was crucial to the first notable success of reinforcement learning with deep neural networks showed that these proposed functions of replay have application beyond the mammalian brain and extend to artificially intelligent systems \[[14](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0070)\]. In this work, an artificial neural network composed of several convolutional and fully connected layers received visual input (images from Atari 2600 computer games) while producing joystick movements to play the game. Its learning algorithm builds on classical **Q-learning**, which maps states (visual input) to actions (joystick output). The error generated by the Q-learning loss function is then used to train the deep neural network using the **backpropagation** algorithm. This process gradually optimises the neuron parameters (e.g., synaptic weights) towards an optimal mapping between the state space (Atari images) and the possible actions ([Figure 2](https://www.sciencedirect.com/science/article/pii/S0166223621001442#f0010)).

![Figure 2](https://ars.els-cdn.com/content/image/1-s2.0-S0166223621001442-gr2.jpg)

1.  [Download : Download high-res image (219KB)](https://ars.els-cdn.com/content/image/1-s2.0-S0166223621001442-gr2_lrg.jpg "Download high-res image (219KB)")
2.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S0166223621001442-gr2.jpg "Download full-size image")

Figure 2. Deep Q network (DQN) with memory buffer.

DQN with memory buffer. Top: a DQN trained to play the Atari game Boxing. At every time-step *t*, the DQN outputs an action corresponding to a joystick movement (1), which causes the game to produce a new reward (game score) and a new observation (pixel values; 2). The observation is transformed into a series of four visual frames that make up the state, and the tuple of state, reward, action, and subsequent state are stored in the replay buffer (3). These tuples are then sampled from the buffer and replayed to the DQN so that it optimises a function mapping state inputs to action outputs in order to maximise reward (4). Bottom: at each update, Q-values for a given pair of state *s* and action *a* from the sample are updated according to the difference between the observed value and expected value, where the observed value is the reward *r* from the sample added to expected future reward maxQ(s′, a′) discounted by a factor *ɣ* and expected value is the previous Q-value of the state-action pair. Over repeated updates, the Q-values converge on an approximation of how a state-action pair (top node) maps onto possible subsequent states (white nodes) and actions (bottom nodes).

A necessary element of the **deep Q network (DQN)** is that past trials are stored in a **memory buffer** and regularly played back to the network. Because the incoming training data depends on the agent’s previous actions, the distribution of the training data is prone to shift as the agent’s **action policy** for how it behaves also shifts, leading to nonstationary data distributions. Such temporal correlations between successive online learning trials can cause a phenomenon known as catastrophic forgetting, where weight parameters undergo changes that optimise for the most recent gameplay at the cost of older gameplay; this results in behaviour learned from the previous task being rapidly overwritten by the agent’s new behaviour. Experience replay proved a crucial intervention to break temporal correlations between successive online learning trials, which stabilises learning and ultimately leads to much improved performance.

Experience replay itself was proposed in machine learning long before the deep reinforcement breakthrough, but it was only when experience replay and deep reinforcement learning were combined that closer parallels with replay in the brain emerged \[[14](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0070)\]. It can be argued that DQNs exemplify how artificial neural networks can be used as models of biological learning to test theories of how replay can support learning. Manipulating biological replay has largely been limited to broad disruption of replay patterns \[[4](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0020),[5](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0025),[10](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0050),[41](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0205),[42](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0210)\], typically during a relatively brief period immediately following learning, which is found to diminish learning. Whereas in DQNs the consequences of manipulations such as including, excluding, or tweaking replay have been examined more comprehensively \[[14](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0070),[52](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0260)\], the effects of such manipulations in biological settings have been relatively less studied.

However, the differences between how experience replay is implemented algorithmically and how biological replay occurs physiologically merit further consideration. In the early experience replay method \[[14](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0070)\], the memory buffer consisted of past samples taken at random from the replay buffer. The memory buffer was set with an arbitrary capacity of the most recent one million trials; when full, the older samples in memory were replaced with new ones to maintain relatively recent training data. Several of these features of artificial experience replay (specifically the storage of exact copies of previous trials \[[53](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0265),[54](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0270)\], the prioritisation of recent experience \[[55](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0275)\], uniform sampling from the memory buffer \[[56](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0280)\], and its fixed capacity \[[53](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0265)\]) have been developed further in recent years and all of them can be said to be unrepresentative of biological replay to varying degrees. In the following sections, we highlight how advances in experience replay algorithms have come closer to replicating biological replay and the implications for replay as a cognitive mechanism.

## Prioritised experience replay

In principle, replaying activity corresponding to past trials effectively increases the training set, by supplementing ‘live’, online experiences with additional samples. Further, manipulating the set of replayed experiences (the replay buffer) can alter the statistics of this training set to promote more efficient learning. For example, given limited time or resources, prioritising more ‘important’ samples for replay can produce faster and more efficient learning of the encoded information. Depending on what is considered important for the animal or agent, this can be achieved by biasing replay towards rarer events to overcome the under-representation of such information online, towards information that is likely to be needed in the near future \[[4](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0020),[11](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0055),[37](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0185),[38](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0190),[57](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0285),[58](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0290)\], or towards the most surprising or unexpected information \[[46](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0230),[48](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0240)\].

One approach is to select samples stored in the replay buffer by prioritising them according to the magnitude of the **temporal-difference error** \[[56](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0280)\]: a measure of how unexpected a transition between temporally successive states has been. This prioritised replay has also been applied to computational models in neuroscience research, showing that considering rewards while accessing memory can lead to better planning and decision making \[[58](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0290)\]. Replaying surprising information is particularly beneficial, because examples where observed outcomes diverge from predictions indicate that the predictions need improving, so there is more to be gained from updating the weights that produced the erroneous prediction. Predictive coding, based on a mental model of the environment, is a feature of neural activity in the hippocampus and elsewhere \[[59](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0295)\] and offers an efficient way of learning by correcting for errors in predictions. Dopaminergic signals, which influence plasticity in the hippocampus and other brain areas that exhibit replay, have been argued to encode reward-prediction errors during reinforcement learning \[[60](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0300)\]. This means that there is a normative case to be made for the brain to prioritise neural activity associated with errors and there are plausible **neuromodulatory** mechanisms by which this might be instantiated. Relatedly, it has been shown that using DQNs with replay biased by prediction errors can speed up learning \[[56](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0280)\].

In the biological context, prioritised experience is exemplified by the finding in rats that there is greater replay immediately following reward in a reinforcement learning task than following the absence of reward \[[46](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0230)\] or following reward that does not depend on reinforcement learning \[[61](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0305)\], suggesting a bias towards (positive) reward-prediction error. Biological prioritised experience replay is believed to rely on neuromodulatory influences in networks of neurons \[[62](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0310)\]. The association between reward and replay had been observed not only immediately after a trial during wakefulness but also during subsequent sleep; however, these findings are consistent with several possible computational roles for reward in replay \[[63](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0315)\]. More generally, replay has been found to be biased by aversive as well as rewarding outcomes \[[40](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0200),[64](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0320)\], suggesting that the brain does engage in methods of prioritising some replay events over others. In addition to carefully designed experiments to tease out how replay contributes to reinforcement learning in animals \[[63](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0315)\], directly examining the effects of prioritised replay on a deep neural network can be an important proof of principle for how different replay regimes affect learning.

Overall, this is a research area where AI, we would argue, could be a good model for biological learning, because the prediction-error theory of the midbrain dopaminergic circuit has been successful historically in explaining a wide range of experimental findings and several parts of that circuit have been implicated in replay \[[13](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0065),[36.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0180), [37.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0185), [38.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0190), [39.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0195)\]: hippocampus and prefrontal cortex for encoding states \[[65](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0325),[66](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0330)\], striatum for action values \[[67](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0335),[68](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0340)\], and ventral tegmental area for reward-prediction errors \[[69](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0345),[70](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0350)\]. Therefore, it provides a suitable framework for integrating hypotheses about replay, reinforcement learning, dopaminergic signalling, and temporal-difference errors.

Other reviews have covered in greater depth the suitability of deep neural networks as models of neuronal function \[[71.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0355), [72.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0360), [73.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0365), [74.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0370)\]. There are fundamental differences between biological and artificial networks, but, in various domains, deep neural networks can be useful as abstract neural models especially for manipulations that are not easy to test biologically; for example, to model how different neural architectures and cost functions can support learning and performance. This is exemplified by convolutional neural networks and long short-term memory architectures, which have been successfully used as models for visual processing and short-term memory, respectively \[[75](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0375)\]. For replay, manipulating the rules for prioritising replay in deep neural networks can offer insight into how it supports cognitive functions. Where deep neural networks diverge from biological networks, there is an opportunity to identify the necessary elements for recreating desired features. In-depth investigation of how such differences affect information processing in both biological and artificial neural networks has the potential to reveal the key computational principles underlying learning in these systems.

For example, it may be important to establish some quantification of phenomena such as interleaving of online and offline episodes. Quantifying replay over the course of learning in animal studies is difficult for several reasons, among which is a lack of consistency in how replay is defined, measured, and reported. However, the majority of decodable replay events immediately following an episode or trial are repetitions of the same hippocampal activity rather than replays of a different episode \[[45](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0225)\], a proportion that decreases with learning \[[76](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0380)\]. Specifically, 0.4–2 **hippocampal replays** of a familiar, low-reward and low-prediction-error episode per online trial have been reported \[[77.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0385), [78.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0390), [79.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0395)\], rising to 1–4 replays per online trial for higher-reward episodes \[[45](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0225),[76](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0380),[77](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0385),[79](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0395)\] and as many as 9 replays per online trial for episodes with high reward-prediction error \[[77](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0385)\]. This compares to, for example, a mini-batch of 32 samples from the replay buffer for each online trial in a DQN \[[14](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0070)\]. Similarly, before initiating an action, the majority of decodable replay events reflect the upcoming trajectory \[[12](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0060),[45](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0225)\] (but see \[[79](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0395)\]), a proportion that increases with learning \[[76](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0380)\].

Does this mean replays during learning are mostly massed repetitions and not interleaved? This remains to be seen. Some place cells are selective not just for spatial location but also temporal or behavioural context \[[45](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0225),[77](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0385),[78](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0390),[80](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0400)\]; whether they differentially participate in replay events to interleave different contexts for the same spatial trajectory is not clear. In addition, what is replayed in prefrontal cortex appears to be mostly independent of what is replayed in hippocampus \[[81](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0405)\], which suggests that interleaving may happen at a higher cortical, rather than hippocampal, level. Finally, decodable replay events typically coincide with half or less of sharp-wave ripple events, which means the remaining ripples may contain undetected replays of hippocampal activity encoding other environments or tasks \[[47](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0235)\] (but see \[[79](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0395)\]).

Biological replay continues for hours after training at a slowly decaying rate \[[82](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0410)\], so sleep or extended rest may offer an opportunity for increasingly interleaved replay of these new episodes with older ones \[[47](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0235)\]. However, what is replayed, apart from the novel experience, is largely unknown, because studies typically record a single task in one environment to which replayed activity can be decoded. Ambitious experiments with several environments or reinforcement learning tasks, varying in their similarity to each other and recorded over long timescales, would be beneficial for testing predictions about how replay is interleaved.

## Memory buffer as a limitation of replay

Uniform and prioritised experience replay have proved useful for learning individual, relatively deterministic tasks such as video games. But as the AI field becomes more ambitious in its application domains, the tasks to which models are applied become more complex and less constrained, necessitating more sophisticated solutions. One example is hindsight experience replay \[[83](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0415)\], in which the learning agent breaks down complicated goals into simpler ones by redefining its goal (target state) retrospectively when replaying past experience. This flexibility makes it easier to learn from sparse rewards and allows learning of many policies in parallel, supporting efficient learning for robotics where there are many more degrees of freedom in how an agent can interact with the physical world than a joystick-controlled video game with limited screen resolution. Even this has limitations when the tasks to be learned are too distinct from each other.

A further limitation is that memory buffers in deep reinforcement learning are often designed to contain one million transitions, an arbitrary hyperparameter that is commonly untuned. With more complex tasks, a limited memory buffer cannot contain a representative set of samples from a very large state-space: some will fail to be stored in the memory buffer, so the network is at risk of converging on solutions that are not appropriate for these forgotten experiences. This storage issue is particularly problematic for continual learning when many tasks must be learned in sequence, which is becoming an important problem as AI progresses towards ever more complex challenges.

One response to this challenge is to innovate ways to prioritise the samples that are stored in the memory buffer, contrasting with the simpler approach of just making the buffer bigger. Techniques have been developed to penalise, limit, or freeze weight changes in the network that were important for one task when learning a new additional task. For example, with elastic weight consolidation, the learnt connections that are important for one task but not another can be restricted to limit weight changes, ensuring that new learning is encoded by a different set of connections in the same network \[[84](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0420)\]. To some degree this resembles the largely nonoverlapping cortical neuronal representations that are enforced when successive tasks are learnt in quick succession, which has been shown to prevent interference \[[85](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0425)\], although this is not characteristic of hippocampus \[[86](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0430)\], and over longer timescales and larger spatial scales ‘representational drift’ achieves a similar effect by different mechanisms \[[80](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0400)\]. Variations of this approach mean that the replay buffer can either be abolished altogether, or used only to store a limited selection of recent samples (such as from the current task) \[[87.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0435), [88.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0440), [89.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0445), [90.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0450), [91.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0455)\].

Although these approaches prevent catastrophic forgetting, often without needing a replay buffer, they often assume a series of discrete, well-defined tasks with parameters that do not need to be updated once learned \[[92](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0460)\]. This may not be suitable for autonomous agents that face continuous, unsupervised learning in the real world. In addition, reducing the overlap between representations of different tasks in the network disregards the potential benefits of transfer learning, in which shared representations can speed up learning on new, similar tasks.

How can replay be used to support continual learning? To some extent, maintaining the memory buffer as a representative sample of tasks past and present can mitigate catastrophic forgetting \[[55](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0275)\], but eventually the trade-off remains between a large computationally costly memory buffer and remembering insufficient samples. Another ethical consideration is that explicitly storing training data may also violate privacy for some applications. Given that the mammalian brain achieves both continual learning and transfer learning with ease despite limits on resources, again neuroscience has major potential to offer inspiration for solving this problem: converging new evidence suggests that the hippocampus is capable of generating its own samples to train from.

## Generative replay

Brains are not structured in a way that separates the processing network away from the learning network that stores exact copies of past trials. Moreover, neuronal firing in brains is inherently stochastic. The result is that no two patterns of activity, either the original online activity encoding the novel experience, or any subsequent replay, are exactly the same. In the context of spatial navigation, sequences of activity during replay events can reflect random walks through the cognitive map \[[93](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0465)\], encoding paths through the environment that have never been observed directly by an animal, including reverse trajectories in a one-way system, shortcuts, and blocked-off paths that were seen but not taken \[[94](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0470),[95](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0475)\] ([Figure 3](https://www.sciencedirect.com/science/article/pii/S0166223621001442#f0015)). One can interpret this as if the hippocampus generates its own samples (its own training data) from a minimal stored model.

![Figure 3](https://ars.els-cdn.com/content/image/1-s2.0-S0166223621001442-gr3.jpg)

1.  [Download : Download high-res image (489KB)](https://ars.els-cdn.com/content/image/1-s2.0-S0166223621001442-gr3_lrg.jpg "Download high-res image (489KB)")
2.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S0166223621001442-gr3.jpg "Download full-size image")

Figure 3. Biological and artificial generative replay.

(A) Hippocampal replay sequences have been found to reflect paths through the environment never taken by the animal, as demonstrated by decoding of locations during a replay event along the top of the maze when the animal had only explored it in a figure-of-eight pattern. Bottom: spiking of hippocampal cells that have place fields on the left and right loops of the maze, respectively, during a replay event. Top: decoded position during replay event. Colour indicates temporal order in the replay sequence. (B) Images generated by a generative adversarial network trained to reproduce handwritten MNIST digits and Street View House Numbers, instead of explicitly storing copies of such images in a memory buffer as in standard experience replay. Sample examples from early (top) and later in training (bottom) are shown; as training progresses, the samples produced by the generator increasingly resemble real images and are increasingly recognisable as numbers. Panels (A) and (B) adapted from \[[53](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0265),[94](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0470)\], respectively.

Deep neural networks can generate their own samples too, although so far this has been achieved primarily in supervised classification tasks with relatively simple datasets and with minimal applications for reinforcement learning. Typically, a generative adversarial network, autoencoder, or restricted Boltzmann machine is trained to generate data with the same parameter distributions as incoming data. The generated data is then replayed to the (main) solver model, so that even as new tasks are learned, the cumulative input distribution of all previous tasks continue to be replayed with minimal storage burden.

This approach has been shown to work well for classifying the MNIST database of handwritten digits learnt in sequence without succumbing to catastrophic forgetting \[[53](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0265)\] ([Figure 3](https://www.sciencedirect.com/science/article/pii/S0166223621001442#f0015)). So far, implementations of generative replay usually train a separate network for each task, assuming well-isolated tasks. The challenge for efficient deep generative replay is training a generator that is flexible enough to be scalable to many tasks and complex inputs.

Future research on this topic could, in principle, apply generative replay to a broader range of reinforcement learning tasks and extend it as a model of biological replay. Hippocampal replay is influenced by neuromodulation both at the time of encoding and during replay \[[96](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0480)\], which could serve to bias the generative mechanism towards goal states or high-error transitions, or otherwise alter the parameters of the generated samples in a way that enhances reinforcement learning. There is also evidence of a bidirectional process whereby cortical activity can prompt or select replay patterns in hippocampus \[[8](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0040),[44](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0220),[97](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0485)\], in addition to the hippocampus replaying information to the cortex and other brain areas. These are underexplored in modelling hippocampal replay and may also serve to improve the performance of deep generative replay for more complex tasks. There are many ways in which replayed information need not reflect online updates: low-dimensional representations, top-down influences, biasing towards salient information, and different update or plasticity rules could all be used to improve replay algorithms. For example, work on deep generative replay suggests that freezing weights in initial layers of the network and replaying low-dimensional information may reduce the computational burden \[[54](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0270)\]. An improved understanding of how replay patterns propagate through cortical and subcortical networks may inspire further refinements to this approach.

Finally, the additional flexibility that comes with generative replay may offer other benefits: one example of nonstereotyped replay is that hidden structures can be inferred from information presented in a disjointed way. This pertains not only to finding shortcuts in spatial environments \[[94](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0470)\], but, more abstractly, to replaying sequences of images in the appropriate order \[[9](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0045)\]. Inferring hidden structures from segmented experience may not be possible with an explicit memory buffer, but such forms of biologically inspired replay might allow deep neural networks to gain more insight from their training than current methods can support. A possible role for replay in transfer learning, in which knowledge of past tasks is leveraged to improve learning on new tasks, is yet to be investigated in either neuroscience or machine learning, but may offer both improved algorithms and better insight into cognitive processes.

## Future directions

Recent experimental innovations allow recording of broader areas of the brain over longer timescales to capture more neural data \[[9](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0045),[80](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0400),[97](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0485)\]. This richer data offers possibilities for exploring how replay spreads throughout the brain \[[8](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0040),[81](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0405)\] and over time \[[47](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0235),[53](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0265),[82](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0410)\], but will need strong theory to guide the boundless possibilities for analysis. Meanwhile, reinforcement learning in AI is increasingly taking advantage of more complex and brain-inspired representations of the world to meet the challenges of complex, noisy, and nonstationary applications, including hierarchies of learners \[[98](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0490)\] and distributions of values \[[99](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0495)\]. Increasingly sophisticated task designs in experimental neuroscience may advance current understanding of replay of inferred structure \[[9](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0045)\], generalisations \[[81](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0405)\], interleaved episodes \[[47](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0235)\], and other ways of organising information to support complex cognition. In turn, these biological insights could help improve the use of past samples in machine learning to support transfer, continual and hierarchical reinforcement learning. While this recent focus on increasing the quantity of data is valuable, understanding the role of replay in complex cognitive processes will require more sophisticated and carefully designed behavioural tasks than are now available.

Other developments include encoding states of the world as successor representations \[[100](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0500)\], a computational structure that represents states in terms of where they might lead to (i.e., expected occupancies of future states). Successor representations make learning more efficient, generalise better in multitask settings \[[101](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0505)\], and can be used as a model of hippocampal place cells \[[59](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0295)\]. Replaying the successor representations themselves, rather than pixel observations as is typical in experience replay \[[14](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0070)\], could further support learning in complex settings, not only improving machine learning algorithms but also shedding light on the function of hippocampal replay.

Beyond gaining insights into optimisation of cognitive processes, closer integration of research on replay for reinforcement learning in AI and neuroscience could lead to new avenues for understanding disease aetiology and symptoms. Reinforcement learning is altered, for instance, in patients with Parkinson’s disease and schizophrenia (conditions that are characterised by altered **dopamine** levels), both during learning itself and in the consolidation period of hours or days afterwards \[[102](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0510),[103](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0515)\]. Future models of replay for reinforcement learning that explicitly relate to the various neural circuits affected by such conditions may help to explain how they give rise to the associated cognitive changes.

## Concluding remarks

Deep neural networks and brains are examples of artificial and natural intelligent systems that solve computationally related problems involving reinforcement learning in complex environments. Despite significant fundamental differences between biological and artificial networks, replay appears to reflect convergence on comparable mechanisms: both biologically and artificially intelligent systems harness replay of past experience to stabilise, consolidate, generalise from, and accelerate learning. In neuroscience, questions remain about how replay is initiated and propagated through cortical and subcortical networks and what influence this has on learning. By addressing these problems in simulated and real-world settings, computational models can play important roles in making testable predictions of how the brain solves these problems (see [Outstanding questions](https://www.sciencedirect.com/science/article/pii/S0166223621001442#b0020)). Deep neural networks are an example of such a computational model that underlie complex applications of AI in computer vision and other domains while also being biologically plausible in some aspects, making them invaluable for manipulating aspects of replay that are difficult to control experimentally to reveal how it supports learning and memory processes. In particular, experimental studies are restricted to learning and memory processes that take place over timescales of seconds to weeks; therefore, hypotheses about lifelong learning may be more easily developed and tested in deep neural networks. Conversely, as research on replay throughout the brain develops, it may hold keys to solving some of the biggest challenges in AI today, including continual learning where algorithms fall short of what brains can do with ease \[[104](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bb0520)\]. A more ambitious long-term goal for AI, with prospects of its feasibility being debated, is the design of an artificial general intelligence that can tackle virtually any task in the grasp of humans.

Outstanding questions

To what extent does replay reflect individual episodes versus aggregated statistics in the brain and how does the replay of individual versus generalised information support learning and consolidation in both biology and AI?

Replay in deep reinforcement learning often starts at the input layer and propagates to higher layers; in the mammalian brain it is unclear how different brain areas interact during replay events. Can replay originate in lower layers (corresponding to sensory cortices, in brains), higher layers (hippocampus, prefrontal cortex), and output layers (striatum)? How does it propagate through the network and what influence does this have on learning?

How does replay of newer versus older information, and overlapping versus distinct representations, support learning and consolidation?

How can replay of similar information benefit transfer learning?

Are the update rules different for online experience versus replay? Are the update rules different for replay during wake versus sleep and replay during rapid eye movement (REM) versus non-REM sleep?

How can generative replay be used to support continual learning of complex tasks?

## Acknowledgements

This research was funded in part by a Wellcome Senior Research Fellowship in Basic Biomedical Science (grant number [202810/Z/16/Z](https://www.sciencedirect.com/science/article/pii/S0166223621001442#gts0005) to M.W.J.), a Wellcome PhD studentship (grant number [109070/Z/15/A](https://www.sciencedirect.com/science/article/pii/S0166223621001442#gts0010) to E.R.), a Leverhulme Trust Research Leadership Award (grant number [RL-2016-39](https://www.sciencedirect.com/science/article/pii/S0166223621001442#gts0015) to N.L.). R.C. was supported by Unifying Neuroscience and Artificial Intelligence - Québec (UNIQUE), Fonds de recherche du Québec (FRQNT), and Natural Sciences and Engineering Research Council of Canada (NSERC). For the purpose of Open Access, the authors have applied a CC BY public copyright licence to any Author Accepted Manuscript version arising from this submission.

## Declaration of interests

The authors declare no competing interests in relation to this work.

## References

[1.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0005)

R.S. Sutton, A.G. Barto

**Introduction to Reinforcement Learning**

The MIT Press (1998)

[2.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0010)

L.-J. Lin

**Self-improving reactive agents based on reinforcement learning, planning and teaching**

Mach. Learn., 8 (1992), pp. 293-4, pp. 293–321

[3.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0015)

H.F. Ólafsdóttir, *et al.*

**The role of hippocampal replay in memory and planning**

Curr. Biol., 28 (2018), pp. R37-R50

[4.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0020)

F. Michon, *et al.*

**Post-learning hippocampal replay selectively reinforces spatial memory for highly rewarded locations**

Curr. Biol., 29 (2019), pp. 1436-1444

[5.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0025)

A. Fernández-Ruiz, *et al.*

**Long-duration hippocampal sharp wave ripples improve memory**

Science, 364 (2019), pp. 1082-1086

[6.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0030)

B. Rasch, *et al.*

**Odor cues during slow-wave sleep prompt declarative memory consolidation**

Science, 315 (2007), pp. 1426-1429

[7.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0035)

D.C. Barnes, D.A. Wilson

**Slow-wave sleep-imposed replay modulates both strength and precision of memory**

J. Neurosci., 34 (2014), pp. 5134-5142

[8.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0040)

G. Rothschild, *et al.*

**A cortical-hippocampal-cortical loop of information processing during memory consolidation**

Nat. Neurosci., 20 (2017), pp. 251-259

[9.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0045)

Y. Liu, *et al.*

**Human replay spontaneously reorganizes experience**

Cell, 178 (2019), pp. 640-652

[10.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0050)

S.P. Jadhav, *et al.*

**Awake hippocampal sharp-wave ripples support spatial memory**

Science, 336 (2012), pp. 1454-1458

[11.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0055)

A.A. Carey, *et al.*

**Reward revaluation biases hippocampal replay content away from the preferred outcome**

Nat. Neurosci., 22 (2019), pp. 1450-1459

[12.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0060)

H.F. Ólafsdóttir, *et al.*

**Task demands predict a dynamic switch in the content of awake hippocampal replay**

Neuron, 96 (2017), pp. 925-935

[13.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0065)

I. Momennejad, *et al.*

**Offline replay supports planning in human reinforcement learning**

Elife, 7 (2018), Article e32548

[14.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0070)

V. Mnih, *et al.*

**Human-level control through deep reinforcement learning**

Nature, 518 (2015), pp. 529-533

[15.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0075)

D. Silver, *et al.*

**Mastering the game of Go with deep neural networks and tree search**

Nature, 529 (2016), pp. 484-489

[16.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0080)

H.R. Joo, L.M. Frank

**The hippocampal sharp wave–ripple in memory retrieval for immediate use and consolidation**

Nat. Rev. Neurosci., 19 (2018), pp. 744-757

[17.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0085)

D.J. Foster

**Replay comes of age**

Annu. Rev. Neurosci., 40 (2017), pp. 581-602

[18.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0090)

G. Rothschild

**The transformation of multi-sensory experiences into memories during sleep**

Neurobiol. Learn. Mem., 160 (2019), pp. 58-66

[19.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0095)

B.E. Pfeiffer

**The content of hippocampal ‘replay**

Hippocampus, 30 (2020), pp. 6-18

[20.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0100)

R. Stickgold

**Sleep-dependent memory consolidation**

Nature, 437 (2005), pp. 1272-1278

[21.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0105)

J.H.L.P. Sadowski, *et al.*

**Sharp-wave ripples orchestrate the induction of synaptic plasticity during reactivation of place cell firing patterns in the hippocampus**

Cell Rep., 14 (2016), pp. 1916-1929

[22.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0110)

C.J. Behrens, *et al.*

**Induction of sharp wave–ripple complexes in vitro and reorganization of hippocampal networks**

Nat. Neurosci., 8 (2005), pp. 1560-1567

[23.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0115)

H. Norimoto, *et al.*

**Hippocampal ripples down-regulate synapses**

Science, 359 (2018), pp. 1524-1527

[24.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0120)

E.V. Lubenov, A.G. Siapas

**Decoupling through synchrony in neuronal circuits with propagation delays**

Neuron, 58 (2008), pp. 118-131

[25.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0125)

L.L. Colgin, *et al.*

**Long-term potentiation is impaired in rat hippocampal slices that produce spontaneous sharp waves**

J. Physiol., 558 (2004), pp. 953-961

[26.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0130)

Z. Nádasdy, *et al.*

**Replay and time compression of recurring spike sequences in the hippocampus**

J. Neurosci., 19 (1999), pp. 9497-9507

[27.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0135)

A.K. Lee, M.A. Wilson

**Memory of sequential experience in the hippocampus during slow wave sleep**

Neuron, 36 (2002), pp. 1183-1194

[28.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0140)

M. Yoshida, *et al.*

**Cholinergic modulation of the CAN current may adjust neural dynamics for active memory maintenance, spatial navigation and time-compressed replay**

Front. Neural Circuits, 6 (2012), p. 10

[29.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0145)

M.A. Wilson, B.L. McNaughton

**Dynamics of the hippocampal ensemble code for space**

Science, 261 (1993), pp. 1055-1058

[30.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0150)

M. McCloskey, N.J. Cohen

**Catastrophic interference in connectionist networks: the sequential learning problem**

Psychol. Learn. Motiv. Adv. Res. Theory, 24 (1989), pp. 109-165

[31.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0155)

M.A. Wilson, B.L. McNaughton

**Reactivation of hippocampal ensemble memories during sleep**

Science, 265 (1994), pp. 676-679

[32.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0160)

W.E. Skaggs, B.L. McNaughton

**Replay of neuronal firing sequences in rat hippocampus during sleep following spatial experience**

Science, 271 (1996), pp. 1870-1873

[33.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0165)

H.S. Kudrimoti, *et al.*

**Reactivation of hippocampal cell assemblies: effects of behavioral state, experience, and EEG dynamics**

J. Neurosci., 19 (1999), pp. 4090-4101

[34.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0170)

Y.-L. Qin, *et al.*

**Memory reprocessing in corticocortical and hippocampocortical neuronal ensembles**

Philos. Trans. R. Soc. B Biol. Sci., 352 (1997), pp. 1525-1533

[35.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0175)

D. Ji, M.A. Wilson

**Coordinated memory replay in the visual cortex and hippocampus during sleep**

Nat. Neurosci., 10 (2007), pp. 100-107

[36.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0180)

D.R. Euston, *et al.*

**Fast-forward playback of recent memory sequences in prefrontal cortex during sleep**

Science, 318 (2007), pp. 1147-1150

[37.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0185)

A. Peyrache, *et al.*

**Replay of rule-learning related neural patterns in the prefrontal cortex during sleep**

Nat. Neurosci., 12 (2009), pp. 919-926

[38.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0190)

C.M.A. Pennartz, *et al.*

**The ventral striatum in off-line processing: ensemble reactivation during sleep and modulation by hippocampal ripples**

J. Neurosci., 24 (2004), pp. 6446-6456

[39.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0195)

S.N. Gomperts, *et al.*

**VTA neurons coordinate with the hippocampal reactivation of spatial experience**

Elife, 4 (2015), pp. 321-352

[40.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0200)

G. Girardeau, *et al.*

**Reactivations of emotional memory in the hippocampus–amygdala system during sleep**

Nat. Neurosci., 20 (2017), pp. 1634-1642

[41.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0205)

G. Girardeau, *et al.*

**Selective suppression of hippocampal ripples impairs spatial memory**

Nat. Neurosci., 12 (2009), pp. 1222-1223

[42.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0210)

V. Ego-Stengel, M.A. Wilson

**Disruption of ripple-associated hippocampal activity during rest impairs spatial learning in the rat**

Hippocampus, 20 (2010), pp. 1-10

[43.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0215)

I. Gridchyn, *et al.*

**Assembly-specific disruption of hippocampal replay leads to selective memory deficit**

Neuron, 106 (2020), pp. 291-300

[44.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0220)

D. Bendor, M.A. Wilson

**Biasing the content of hippocampal replay during sleep**

Nat. Neurosci., 15 (2012), pp. 1439-1444

[45.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0225)

H. Xu, *et al.*

**Assembly responses of hippocampal CA1 place cells predict learned behavior in goal-directed spatial tasks on the radial eight-arm maze**

Neuron, 101 (2019), pp. 119-132

[46.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0230)

A.C. Singer, L.M. Frank

**Rewarded outcomes enhance reactivation of experience in the hippocampus**

Neuron, 64 (2009), pp. 910-921

[47.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0235)

M.P. Karlsson, L.M. Frank

**Awake replay of remote experiences in the hippocampus**

Nat. Neurosci., 12 (2009), pp. 913-918

[48.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0240)

C.S. Lansink, *et al.*

**Preferential reactivation of motivationally relevant information in the ventral striatum**

J. Neurosci., 28 (2008), pp. 6372-6382

[49.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0245)

G.M. van de Ven, *et al.*

**Hippocampal offline reactivation consolidates recently formed cell assembly patterns during sharp wave-ripples**

Neuron, 92 (2016), pp. 968-974

[50.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0250)

L. Roux, *et al.*

**Sharp wave ripples during learning stabilize the hippocampal spatial map**

Nat. Neurosci., 20 (2017), pp. 845-853

[51.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0255)

S.J. Gershman, *et al.*

**Retrospective revaluation in sequential decision making: a tale of two systems**

J. Exp. Psychol. Gen., 143 (2014), pp. 182-194

[52.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0260)

W. Fedus, *et al.*

**Revisiting fundamentals of experience replay**

Proc. 37th Int. Conf. Mach. Learn. Proc. Mach. Learn. Res, 119 (2020), pp. 3061-3071

[53.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0265)

J.K. Lee, *et al.*

**Continual learning with deep generative replay**

31st Conference on Neural Information Processing Systems (NIPS 2017) (2017), pp. 2990-2999

[54.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0270)

G.M. van de Ven, *et al.*

**Brain-inspired replay for continual learning with artificial neural networks**

Nat. Commun., 11 (2020), p. 4069

[55.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0275)

D. Isele, A. Cosgun

**Selective experience replay for lifelong learning**

32nd AAAI Conference on Artificial Intelligence AAAI 2018 (2018), pp. 3302-3309

[56.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0280)

T. Schaul, *et al.*

**Prioritized experience replay**

4th International Conference on Learning Representations ICLR 2016 (2016)

[57.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0285)

J.L. McClelland, *et al.*

**Why there are complementary learning systems in the hippocampus and neocortex: insights from the successes and failures of connectionist models of learning and memory**

Psychol. Rev., 102 (1995), pp. 419-457

[58.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0290)

M.G. Mattar, N.D. Daw

**Prioritized memory access explains planning and hippocampal replay**

Nat. Neurosci., 21 (2018), pp. 1609-1617

[59.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0295)

K.L. Stachenfeld, *et al.*

**The hippocampus as a predictive map**

Nat. Neurosci., 20 (2017), pp. 1643-1653

[60.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0300)

M. Watabe-Uchida, *et al.*

**Neural circuitry of reward prediction error**

Annu. Rev. Neurosci., 40 (2017), pp. 373-394

[61.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0305)

D. Dupret, *et al.*

**The reorganization and reactivation of hippocampal maps predict spatial memory performance**

Nat. Neurosci., 13 (2010), pp. 995-1002

[62.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0310)

G. de Lavilléon, *et al.*

**Explicit memory creation during sleep demonstrates a causal role of place cells in navigation**

Nat. Neurosci., 18 (2015), pp. 493-495

[63.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0315)

E. Roscow, *et al.*

**Behavioural and computational evidence for memory consolidation biased by reward-prediction errors**

bioRxiv (2019)

[64.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0320)

C.-T. Wu, *et al.*

**Hippocampal awake replay in fear memory retrieval**

Nat. Neurosci., 20 (2017), pp. 571-580

[65.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0325)

R.C. Wilson, *et al.*

**Orbitofrontal cortex as a cognitive map of task space**

Neuron, 81 (2014), pp. 267-279

[66.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0330)

A.M. Wikenheiser, G. Schoenbaum

**Over the river, through the woods: cognitive maps in the hippocampus and orbitofrontal cortex**

Nat. Rev. Neurosci., 17 (2016), pp. 513-523

[67.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0335)

K. Samejima, *et al.*

**Representation of action-specific reward values in the striatum**

Science, 310 (2005), pp. 1337-1340

[68.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0340)

B. Lau, P.W. Glimcher

**Value representations in the primate striatum during matching behavior**

Neuron, 58 (2008), pp. 451-463

[69.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0345)

W. Schultz

**Predictive reward signal of dopamine neurons**

J. Neurophysiol., 80 (1998), pp. 1-27

[70.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0350)

J.P. O’Doherty, *et al.*

**Temporal difference models and reward-related learning in the human brain**

Neuron, 38 (2003), pp. 329-337

[71.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0355)

A.H. Marblestone, *et al.*

**Toward an integration of deep learning and neuroscience**

Front. Comput. Neurosci., 10 (2016), p. 94

[72.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0360)

B.A. Richards, *et al.*

**A deep learning framework for neuroscience**

Nat. Neurosci., 22 (2019), pp. 1761-1770

[73.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0365)

A. Saxe, *et al.*

**If deep learning is the answer, what is the question?**

Nat. Rev. Neurosci., 22 (2021), pp. 55-67

[74.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0370)

R.M. Cichy, D. Kaiser

**Deep neural networks as scientific models**

Trends Cogn. Sci., 23 (2019), pp. 305-317

[75.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0375)

D. Hassabis, *et al.*

**Neuroscience-inspired artificial intelligence**

Neuron, 95 (2017), pp. 245-258

[76.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0380)

J.D. Shin, *et al.*

**Dynamics of awake hippocampal-prefrontal replay for spatial learning and memory-guided decision making**

Neuron, 104 (2019), pp. 1110-1125

[77.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0385)

H. Igata, *et al.*

**Prioritized experience replays on a hippocampal predictive map for learning**

Proc. Natl. Acad. Sci. U. S. A., 118 (2021), p. 1

[78.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0390)

B. Bhattarai, *et al.*

**Distinct effects of reward and navigation history on hippocampal forward and reverse replays**

Proc. Natl. Acad. Sci. U. S. A., 117 (2020), pp. 689-697

[79.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0395)

A.K. Gillespie, *et al.*

**Hippocampal replay reflects specific past experiences rather than a plan for subsequent choice**

bioRxiv (2021)

[80.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0400)

Y. Ziv, *et al.*

**Long-term dynamics of CA1 hippocampal place codes**

Nat. Neurosci., 16 (2013), pp. 264-266

[81.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0405)

K. Kaefer, *et al.*

**Replay of behavioral sequences in the medial prefrontal cortex during rule switching**

Neuron, 106 (2020), pp. 154-165

[82.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0410)

B. Giri, *et al.*

**Hippocampal reactivation extends for several hours following novel experience**

J. Neurosci., 39 (2019), pp. 866-875

[83.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0415)

M. Andrychowicz, *et al.*

**Hindsight experience replay**

31st Conference on Neural Information Processing Systems (2017)

[84.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0420)

J. Kirkpatrick, *et al.*

**Overcoming catastrophic forgetting in neural networks**

Proc. Natl. Acad. Sci. U. S. A., 114 (2017), pp. 3521-3526

[85.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0425)

J. Cichon, W.B. Gan

**Branch-specific dendritic Ca2+ spikes cause persistent synaptic plasticity**

Nature, 520 (2015), pp. 180-185

[86.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0430)

G.P. Gava, *et al.*

**Integrating new memories into the hippocampal network activity space**

Nat. Neurosci., 24 (2021), pp. 326-330

[87.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0435)

Z. Li, D. Hoiem

**Learning without forgetting**

IEEE Trans. Pattern Anal. Mach. Intell., 40 (2018), pp. 2935-2947

[88.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0440)

F. Zenke, *et al.*

**Continual learning through synaptic intelligence**

34th International Conference on Machine Learning, ICML 2017, Vol. 8 (2017), pp. 6072-6082

[89.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0445)

N.Y. Masse, *et al.*

**Alleviating catastrophic forgetting using context dependent gating and synaptic stabilization**

Proc. Natl. Acad. Sci. U. S. A., 115 (2018), pp. E104657-E104675

[90.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0450)

A.A. Rusu, *et al.*

**Progressive neural networks**

arXiv (2016)

[91.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0455)

J. Schwarz, *et al.*

**Progress & compress: a scalable framework for continual learning**

35th International Conference on Machine Learning ICML 2018, Vol. 10 (2018), pp. 7199-7208

[92.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0460)

G.I. Parisi, *et al.*

**Continual lifelong learning with neural networks: a review**

Neural Netw., 113 (2019), pp. 54-71

[93.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0465)

F. Stella, *et al.*

**Hippocampal reactivation of random trajectories resembling Brownian diffusion**

Neuron, 102 (2019), pp. 450-461

[94.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0470)

A.S. Gupta, *et al.*

**Hippocampal replay is not a simple function of experience**

Neuron, 65 (2010), pp. 695-705

[95.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0475)

H.F. Ólafsdóttir, *et al.*

**Hippocampal place cells construct reward related sequences through unexplored space**

Elife, 4 (2015), Article e06063

[96.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0480)

L.A. Atherton, *et al.*

**Memory trace replay: the shaping of memory consolidation by neuromodulation**

Trends Neurosci., 38 (2015), pp. 560-570

[97.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0485)

J.K. Abadchi, *et al.*

**Spatiotemporal patterns of neocortical activity around hippocampal sharp-wave ripples**

Elife, 9 (2020), Article e51972

[98.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0490)

J.X. Wang, *et al.*

**Prefrontal cortex as a meta-reinforcement learning system**

Nat. Neurosci., 21 (2018), pp. 860-868

[99.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0495)

W. Dabney, *et al.*

**A distributional code for value in dopamine-based reinforcement learning**

Nature, 577 (2020), pp. 671-675

[100.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0500)

P. Dayan

**Improving generalization for temporal difference learning: the successor representation**

Neural Comput., 5 (1993), pp. 613-624

[101.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0505)

A. Barreto, *et al.*

**Fast reinforcement learning with generalized policy updates**

Proc. Natl. Acad. Sci. U. S. A., 117 (2020), pp. 30079-30087

[102.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0510)

J.P. Grogan, *et al.*

**Effects of dopamine on reinforcement learning and consolidation in Parkinson’s disease**

Elife, 6 (2017), Article e26801

[103.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0515)

A.J. Culbreth, *et al.*

**Retention of value representations across time in people with schizophrenia and healthy control subjects**

Biol. Psychiatry Cogn. Neurosci. Neuroimaging, 6 (2021), pp. 420-428

[104.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0520)

R. Hadsell, *et al.*

**Embracing change: continual learning in deep neural networks**

Trends Cogn. Sci., 24 (2020), pp. 1028-1040

[105.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0525)

L.-J. Lin

**Programming robots using reinforcement learning and teaching**

Proceedings of the Ninth National Conference on Artificial Intelligence (1991), pp. 781-786

[106.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0530)

J. O’Keefe, J. Dostrovsky

**The hippocampus as a spatial map. Preliminary evidence from unit activity in the freely-moving rat**

Brain Res., 34 (1971), pp. 171-175

[107.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0535)

D. Marr

**Simple memory: a theory for archicortex**

Philos. Trans. R. Soc. Lond. B, 262 (1971), pp. 23-81

[108.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0540)

C. Pavlides, J. Winson

**Influences of hippocampal place cell firing in the awake state on the activity of these cells during subsequent sleep episodes**

J. Neurosci., 9 (1989), pp. 2907-2918

[109.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0545)

M.J. Gruber, *et al.*

**Post-learning hippocampal dynamics promote preferential retention of rewarding events**

Neuron, 89 (2016), pp. 1110-1120

[110.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0550)

V.P. Murty, *et al.*

**Selectivity in postencoding connectivity with high-level visual cortex is associated with reward-motivated memory**

J. Neurosci., 37 (2017), pp. 537-545

[111.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0555)

A.C. Schapiro, *et al.*

**Human hippocampal replay during rest prioritizes weakly learned information and predicts memory performance**

Nat. Commun., 9 (2018), p. 3920

[112.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0560)

N.W. Schuck, Y. Niv

**Sequential replay of nonspatial task states in the human hippocampus**

Science, 364 (2019), p. 6447

[113.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0565)

G. Buzsáki, *et al.*

**High-frequency network oscillation in the hippocampus**

Science, 256 (1992), pp. 1025-1027

[114.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0570)

D. Tse, *et al.*

**Schemas and memory consolidation**

Science, 316 (2007), pp. 76-82

[115.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0575)

Z. Cook, *et al.*

**Exploration versus exploitation in polydomous ant colonies**

J. Theor. Biol., 323 (2013), pp. 49-56

[116.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0580)

J.W. Antony, K.A. Paller

**Hippocampal contributions to declarative memory consolidation during sleep**

D.E. Hannula, M.C. Duff (Eds.), The Hippocampus from Cells to Systems: Structure, Connectivity, and Functional Contributions to Memory and Flexible Cognition, Springer International Publishing (2017), pp. 245-280

[117.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0585)

A.C. Schapiro, *et al.*

**Complementary learning systems within the hippocampus: a neural network modelling approach to reconciling episodic memory with statistical learning**

Philos. Trans. R. Soc. B Biol. Sci., 372 (2017), p. 20160049

[118.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0590)

J.L. McClelland, *et al.*

**Integration of new information in memory: new insights from a complementary learning systems perspective**

Philos. Trans. R. Soc. B Biol. Sci., 375 (2020), p. 1799

[119.](https://www.sciencedirect.com/science/article/pii/S0166223621001442#bbb0595)

M.F. Carr, *et al.*

**Hippocampal replay in the awake state: a potential substrate for memory consolidation and retrieval**

Nat. Neurosci., 14 (2011), pp. 147-153

## Cited by (2)

## Glossary

**Action policy**

behaviour learned by a reinforcement learning agent that determines the actions to be taken given observations about the current state.

**Backpropagation**

learning algorithm for updating the weights in a deep neural network, in which the gradients of the error function are calculated for each layer sequentially, starting with the last layer.

**Catastrophic interference**(

or forgetting); when new learning in a network causes dramatic changes that result in the loss of previously acquired, stable associations.

**Deep Q network (DQN)**

deep neural network that performs Q-learning.

**Deep reinforcement learning**

reinforcement learning algorithms implemented in deep neural networks, characterised by an input later, an output layer, and at least one intermediate hidden layer.

**Dopamine**

neuromodulator released by (among other brain regions) the basal forebrain. Dopamine has been proposed to function as a reward-prediction error signal throughout the brain.

**Experience replay**

technique of sampling from past experiences stored in a memory buffer and replaying them to the network.

**Experience tuple**

the data from a single episode that is stored in a memory buffer to be replayed later; typically, the state of the environment, the action taken by the agent, the resulting reward, and the subsequent state of the environment.

**Hippocampal replay**

reinstatement of neural activity that encodes a previous experience in the hippocampus during rest and sleep.

**Memory buffer**

storage of experience tuples during the learning of a task, which can later be sampled from and replayed.

**Memory consolidation**

stabilisation of a recent memory into the neural circuit so that it is retained long-term, through chemical and structural plasticity processes.

**Neuromodulation**

chemical transmission between neurons that diffuses over a broad area, to regulate the activity of a large number of neurons.

**Non-REM sleep**

light and deep sleep stages, excluding rapid eye movement (REM) sleep, characterised by synchronous patterns of neural activity. Most replay has been observed in non-REM sleep and it is unclear to what extent the quantity, attributes, and computational roles of replay differ between REM and non-REM sleep.

**Place cell**

neuron found in the hippocampus that fires preferentially when the animal is in a particular place.

**Plasticity**

changes in neural circuits, particularly the strengthening and weakening of synaptic connections.

**Q-learning**

a model-free reinforcement learning algorithm and extension of temporal-difference learning, for optimising the policy of selecting actions in any given state.

**Reinforcement learning**

learning to act to maximise expected rewards, an area of study in both psychology and machine learning.

**State transitions**

the possibility or probability of one state leading to another state in a single step; in spatial navigation tasks this depends on the topology of the environment, including physical distance between states and barriers between them.

**Temporal-difference error**

reinforcement learning algorithm that learns the values of states by minimising the difference in predicted value between temporally successive states.

[View Abstract](https://www.sciencedirect.com/science/article/abs/pii/S0166223621001442)

© 2021 Elsevier Ltd. All rights reserved.
