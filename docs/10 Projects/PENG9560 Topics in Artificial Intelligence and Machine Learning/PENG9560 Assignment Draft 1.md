---
type: writing
status: open
priority: p1
project: PENG9560
creationtag: 2023-02-17 18:46
infotags:
people:
date:
---

See [[PENG9560 Assignment Draft 2]]

# Introduction
Reinforcement Learning (RL) has its basis in biological models of learning. 

The RL approach is that of an “agent” in an environment where it must optimize it’s actions based on input about the state of the environment in order to optimize for a reward. 

This imitates animal models where the animal will need to learn conditions of their environment for a reward such as food.

Current RL methods are limited by dimension. RL is a tabular method, requiring a lookup table to save *Q-policies*, mappings between the state of the environment and the subsequent [most valuable / likely] course of action taken by the agent, represented by a *Q-value*.


For a _Q-Function_, there is internally is a Q-table that contains all the state-action pair values, a.k.a. *Q-policies*: mappings between the state of the environment and the subsequent [most valuable / likely] course of action taken by the agent, represented by a *Q-value*. Given a state and action, our Q-Function will search into its Q-table the corresponding value. This approach is unable to scale to larger regimes, where increasing the space of environmental inputs and possible actions scale the policy space exponentially. This problem continues into more naturalistic environments and action spaces with continuous values, causing discrete mappings fail as even small differences between values can result in wildly different outcomes.[^3]

An ideal solution would be to implement a RL paradigm in a Deep Neural Network (DNN). Another biologically inspired paradigm, DNNs are capable of encoding large dimension information spaces in condensed network structures and continuous mappings of the space are possible. A clear boon for the needs of RL. However, this is no small task as the nature of RL disallows for the use of Back-Propagation-Through-Time (bptt), the key training algorithm for DNNs.

As we will see, the cornerstone precursor to the paper[s?] reviewed here, [M15] , obviates these issues with a novel form of Q-Learning titled *experience replay*. Another biologically inspired idea which randomizes over the data, removing correlations through time in the episode sequence. This provides the basis for their highly-successful implementation of RL in an DNN, which they refer to as a ***Deep Q-Network (DQN)***.

To this trifecta of biologically inspired mechanisms we further introduce Spiking Neural Networks SNNs: networks which imitate the spiking functions of biological neurons at the neuronal level. These lie at an oblique juncture with traditional ANNs as the mode of communication at the neuron level is fundamentally different. Eschewing ANN’s static and continuous-valued activation, for the effectively binary and time-dependent information passing of spikes, where spike rates and timing are important. Though some the exact nature of spiking communication is highly-complex and not an extremely open field of study, many plausible mechanisms have been successfully utilized in SNN models over the years.[^4]

[Neurons in an ANN are characterized by a single, static, continuous-valued activation.]

[Yet biological neurons use discrete spikes to compute and transmit information, and the spike times, in addition to the spike rates, matter.]
[[@tavanaeiDeepLearningSpiking2019]]

The motives behind the use of SNNs is not only the push towards more biologically driven models, but the swath of potential benefits offered by SNNs. Particularly in the scope of future hardware (neuromorphics) and contributions to computational neuroscience. For the purposes of RL models, adapting neurological models of reward and Hebbian learning, such as Spike-Timing Dependent-Plasticity (STDP), can offer potential expansion into online and self-supervised learning, 

Liu et al. 2022 - *"Human-Level Control Through Directly Trained Deep Spiking $Q$-Networks"*, provides a complete and effective implementation of all these ideas by expanding on the M15 with a full SNN implementation of the DQN. In this review I will cover the methods and stepping-stones the authors built on to build this model, as well as cover related papers and their methods[! Maybe not !] 


# Methods
## DQN 
The DQN architecture on which these models are based upon, comes from Minh et al. 2015 [^1]. This model overcomes the curse of dimensionality limiting RL models by implementing RL in a deep learning regime. This implementation maps the Q-policies in the high-dimensional space of the deep network, with the values on the output nodes corresponding to the relevant Q-values. 

The RL aspect of the model is difficult point of implementation into a DL model [fix wording when awake]. RL means that they can not utilize back propagation through time, which is why in the DQN experience replay is used and a gradient descent learning step is done at individual time steps. In order to stay a tractable problem this is done at separated intervals along the full length of the experiment, e.g. every 100, 000 timesteps. 

This was tested with 49 games from the Atari 2600, with a different network being trained for each game. For each games, the image of the current screen, action state, and score (corresponding to the reward) is available to the model. 

The network is trained using experience-replay for greater efficiency where, episodes from the agent’s experience at each time-step is stored in a buffer. During the learning phase of the algorithm, random samples from these experiences for each time-step are batched and trained from. The algorithm then uses gradient descent to maximize the Q-value on the target action output node. 

### Architecture
[[Human-level control through deep reinforcement learning - 20.02.23.md#The exact architecture|the original description]]

The ANN of first, three convolutional layers followed by two fully-connected layers. The input layer intakes an 84 x 84 x 4 frames which have been preprocessed. The first hidden layer convolves 32 filters of 8x8 with stride. The second hidden layer convolves 64 filters of 4 x 4  with stride 2. The third and final convolution layer convolves 64 filters of 3 x 3 with stride 1. Each convolution layer is rectified by ReLUs before passing to the next layer. 

According to L22 the 4 images are the “m” number of most recent frames.

The next two layers are fully-connected layers, the first consists of 512 rectifier units, and the output layer is a fully connected layer with a number of outputs corresponding to the number of valid actions in the Atari games tested. This varied between 4 and 18 actions in the games tested.

## Why addition of an SNN
The goal of our selected papers is to take the well established framework of M15 and implement spiking neurons. Spiking neurons offer many advantages including low-energy and low-computational costs, as well as event-driven processing, making them a potentially powerful tool in designing fully-online and self-supervising models. However, their unique and non-conventional communication technique means implementation in already established models requires some method of encoding and decoding. 

The design of spiking neural networks is still relatively unexplored, and our first steps are to implement these in established methods. Likewise, as a biologically inspired model, there are potential benefits from adaptation of neurological mechanisms in neural networks. Neurological models, which are necessarily deep and reinforcement trained, can possibly have their properties exploited for better DRL models.  

Deep SNNs come with an additional caveat, in that training with gradient descent is not possible due to their spiking nature, where the value on a neuron is predominantly 0, and for and ever brief moment 1. This is sidestepped through surrogate gradient descent, where the Heaviside step-function is replace with a surrogate arctan function. 

There are other methods that can be used, such as measuring the membrane potential of a neuron instead of it’s output value [C22].







# Model Evaluation

They compare their results against the original model in Mnih et al. 2015. Using the same batching of images taken from games in the Atari 2600 problem set. 

The images of in game shots are given a first pass to render them in greyscale, before being fed as inputs to the model. [Are they also downrezed?], yes, input as 512 x 512 images with the pixels corresponding to inputs at the input layer.

The Chen et al. 2022 model was able to outperform the original model, in terms of time-to-learning


## Results

L22 reran the M15 DQN to compare against their DQSN, as well as against a the conversion-based SNN of T20. 

Quickly, the conversion-based SNN presented in T20, laid the ground work, by pretraining a DQN in an ANN, then converting the hyperparameters into an SNN. This proved successful in performance over the regular DQN.

For a training timestep, the last 4 frames are preprocessed and stored to the buffer as the state of the network at the time step. The window length between training steps of simulation were 100 and 64  for the conversion based SNN and DQN respectively.

The qualities measured for were, performance, stability, learning capability, and energy efficiency. 

In performance, of the 17 Atari games tested, it out-performed (in terms of points) the DQN by an average of 106%. The DQSN was able to outperform the DQN on four games, scored equally in nine games, and scored worst (maximum 20% difference) in four of the games.

Further, it proved to be more stable, obtaining lower standard deviations in score than the DQN in six games, equal to it on two games, and inferior in nine games.

In learning capability, a total proof is not given. In figure 7. the learning curve for the DQN and DQSN is compared for two games. From these plots it is apparent that the DQSN reaches a higher score equilibrium faster than the DQN, as well as in average max Q-value. Though the authors claim this is representative in all cases, no metric is provided. I believe in the future some sort of area under curve metric may be a useful measure.

Lastly they score the model in terms of energy-efficiency, a useful metric for prospective uses in neuromorphic hardware. However, there is no direct method of comparing the DQSN to the DQN. A rough estimate can be made by comparing the number of calculations needed per inference. However, in terms of energy transfer, the SNN must be evaluated in average spike count. In this case it was better to compare it to the conversion-based SNN of T20. The result showing around 85% of the energy usage in comparison to the conversion-based SNN. Though, this comparison was only shown for two games.

All in all, their DQSN appears to achieve the same, if not better, level of performance when compared to the DQN. They further tested their DQSN with more recent variations on the DQN: the Double-DQN [44] and the CDQN [45], claiming a further performance boost of 151.4%  and 141.8% respectively.




C22 also tested their model for robustness against “white box attacks”

# Review

I find Liu et al. 2022 to be an excellent and complete work, taking the logical next-step in deep reinforcement learning networks with spiking neurons. Showcasing a fully SNN model, with no mediatory ANN parts or side-networks. This is in comparison to C22, T20, and P19, where an ANN is initially trained and then the hyperparameters converted into an SNN, or in the case of C22 where spiking layers are introduced, essentially alongside a traditional DQN.

This sets the stage for further development of full SNNs RL models, by prototyping the neuron design and communication. This may inform further experiments which may change the neuron design, along with the further development of alternate training techniques for said alternative neurons. 

Additionally the paper is a very complete and exhaustive one with fine detail of network architecture, neuron design, input and output parameters[!]; Along with complete mathematical description of the training process and links to code repositories for duplication.

Particularly as we develop bio-inspired approaches to learning which can be used in self-supervised, online regimes. These approaches include variants of local plasticity models such as three-factor plasticity or spike-timing dependent plasticity which also exploits time-dimension properties of the spikes.[^2] 

The architecture as well may be scaled up or varied in further experiments as the model the use based on M15 is simply a benchmark and baseline. The success of a fully spiking model in this benchmark means that development of larger DQSN models, addressing larger state and action spaces. 

This, however might come at the cost of tractability, as the regression model presented here is presumably computationally expensive. There were no estimates given about time to compute the experiments and with what hardware, but we may assume costs will accumulate on an exponential order [?]

It may be prudent to then test the memory capacity of DQNs.




### Chen et al. review

The way the two papers I review at first seemed quite similar but on closer inspection used slightly

C22 shows success and improvement over the original DQN, but I find the methods unclear and reproducibility may be difficult.

Despite this, the methods of integrating spiking-layers and converting static input and output, as well as passing error back into these neurons, may contribute to my future projects.

preivous methods T20 P19



# Further Direction
> Your new perspectives of AI or CI that does not exist yet. 
> 
> Your new work: Application of CI techniques to a research problem related to your PhD thesis project. 

While this paper marks an important milestone in the development of deep spiking reward based models, its efficacy in a naturalistic environment that the typical biological agent may find itself in, is extremely limited. While experience-replay effectively leverages a Q-learning framework, the resultant product is effectively an offline training algorithm. 

While not the totality of RL motivations, a reward based framework can allow for dynamically adapting model able to train in an online and self-supervised regime. With the goal in mind of designing autonomous and reactive hardware, there is need to design models which are able to learn and adapt to unpredictable and isolated environments. To this purpose it is necessary to utilize the abilities of spiking neurons, to replicate abilities similar to those found in biological agents. 

So while this important step informs us of the capabilities of an in-place DQSN  after training, the next step is experiment with reward mechanisms which will allow for dynamic learning in an online setting. To this we are studying biologically inspired processes of credit assignment. Local plasticity is a well known mechanism of adaptation at the neuron and neuronal assembly level. A well studied mechanism that is being studied for use in SNNs is that of Spike-Timing Dependent Plasticity (STDP) as well as its extension *three-factor dependent plasticity* which explicitly indicates[?] the use a *third-factor* which may come in the form of a reward-signal. Additionally, proposed methods of back-propagation in SNNs have lately been proposed [^5] further adding alternative plausible methods of credit-assignment in Deep-SNNs.

At this point we are approaching a model of reinforcement learning from an entirely new direction, designing entirely new methods of reward-based learning that are effective in the communication regime of SNNs, as opposed to attempting to apply the methods designed for ANNs and then, somewhat awkwardly fitting SNNs to them.

This however is a fairly nascent field, while emerging over two decades ago  in 1996 [[@maassNetworksSpikingNeurons1997|W. Maass (1997)]], it has gained heavy traction in the past few years [^7] [^6] [^8] alongside accelerating computational neuroscience and application specific integrated circuits in the machine learning space; And so there is need to develop and test the efficacy of proposed methods in this space.


This is not to say the gains made from the ANN-to-SNN approach are non-contributive, but instead we can use these proven models such as the DSQN to bridge the gap from one direction, and build towards it from the other. Any future Deep SNN implementations will need to match the benchmark set here by L22. 

Additionally, I believe there are mechanisms here that may inform how other Deep SNN learning methods may be expected to duplicate. Namely, experience-replay, which is again based on biological processes of memory formation and learning. M15 directly based the concept on hippocampal replay wherein the during sleep, the brain replays time-condensed activation of neural circuits associated with an experienced physical activity.[^9] [^10] In SNNs, where spike timing larger oscillatory time cycles of neuron activity known as phases are critical to network communication, perhaps a designed neuronal circuit based around replicating the buffer like memory and replaying the buffer in phases of time could be an aim of future experiments.






# References
[[@chenDeepReinforcementLearning2022|Chen et al. 2022]]

[[@mnihHumanlevelControlDeep2015]]

[[@wangDeepReinforcementLearning2022]]

[[@liuHumanLevelControlDirectly2022]]
- uh this looks similar if not basically the same

[[@tanStrategyBenchmarkConverting2020]]
- an earlier paper which does similar
- referenced in both papers
- In Liu they refer to this as “conversion-based SNN”
	- the compare their results in Liu to both Mnih and this one
	- I don’t think I want to linger on this as, from the sound of it, it is pretrained on ANNs which are then converted to SNNs
	- ~~They also have a DQSN CV~~ 
		- They do not, I confused the subititle on table VI in Liu
		- It is the comparison
> - To further improve the performance, Tan et al. [28] proposed a more effective conversion method based on the more accurate approximation of the spiking firing rates. It reduced the conversion error based on a pretrained DQN, and achieved state-of-the-art performance on multiple Atari games.

[24] D. Patel, H. Hazan, D. J. Saunders, H. T. Siegelmann, and R. Kozma, “Improved robustness of reinforcement learning policies upon conversion to spiking neuronal network platforms applied to atari breakout game,” Neural Networks, vol. 120, pp. 108–115, 2019.

> is the first work to introduce spiking conversion methods to the domain of deep Q-learning. They demonstrated that both shallow and deep ReLU networks can be converted to SNNs without performance degradation on Atari game Breakout. Then, they showed that the converted SNN is more robust to input perturbations than the original neural network. However, it only focuses on improving the robustness rather than the performance of SNNs on Atari games.

[44] J. Weng et al., “Tianshou: A highly modularized deep reinforcement learning library,” 2021, arXiv:2107.14171. 

[45] Z. T. Wang and M. Ueda, “Convergent and efficient deep Q learning algorithm,” in Proc. Int. Conf. Learn. Represent., Mar. 2022, pp. 1–27.

[^1]: Minh
[^2]: Redo this and refactor it later down the line
[^3]: See [[Human-level control through deep reinforcement learning - 20.02.23.md#^3glkd1]]
[^4]: Add references
[^5]: add references [[@payeurBurstdependentSynapticPlasticity2021]] [[@williamsNeuralBurstCodes2021]]
[^6]: [[@zenkeVisualizingJointFuture2021]] 
[^7]: [[@princeCurrentStateFuture2022]]
[^8]: [[@mehonicBraininspiredComputingNeeds2022]]
[^9]: Bendor, D. & Wilson, M. A. Biasing the content of hippocampal replay during sleep. Nature Neurosci. 15, 1439–1444 (2012).
[^10]: O’Neill, J., Pleydell-Bouverie, B., Dupret, D. & Csicsvari, J. Play it again: reactivation of waking experience and memory. Trends Neurosci. 33, 220–229 (2010).