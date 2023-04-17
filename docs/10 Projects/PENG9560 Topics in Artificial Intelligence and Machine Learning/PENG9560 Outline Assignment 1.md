---
type: [outline, writing]
status: active
priority: p1
project: PENG9560/as1
creationtag: 2023-02-13 22:24
infotags:
people:
date:
---
# Drafts
[[PENG9560 Assignment Draft 1]]
[[PENG9560 Assignment Draft 2]]


# About
Writing over [[@liuHumanLevelControlDirectly2022|Liu et al. 2022]]
- Previously writing over [[@chenDeepReinforcementLearning2022|Chen et al. 2022]]
	-  [[Chen 2022]]
3000-5000 words excluding References

# Summary Outline
See from the [[Presentation Outline - PENG9560]]
1. Intro
	- Future of Deep Learning
	- SNNs
	- The potential of a SQDN
		- Why I chose this paper
	- 
2. What the Paper Presents
	- DQN architecture
		- [Mnih et al. 2015]
		- Novel DQN
		- 
	- Addition of spiking layers
	- Difficulty of implementation in conventional DQN
		- Conventional DQN [Mnih et al. 2015]
			- Trad neurons
				- i.e., Input-32C8S4ReLU-64C4S2-ReLU-64C3S1-ReLU-Flatten-512-ReLU-NA
			- SNN neurons
				- LIF
				- IF
				- i.e., Input-32C8S4ReLU-64C4S2-ReLU-64C3S1-ReLU-Flatten-512-ReLU-NA
			- Integration of trad and spiking neurons
			- Output layer : Measurable Statistics
	- Training
		- DQN
		- SNN Layers
		- Fuck I don’t even know exactly
3.  Evaluation of Model
	1. Atari
	2. tested against [Mnih et al 2015]
4. Weaknesses
	1. offline nature
5. Future directions
	1. Pushing into an online nature
	2. Self-organized nature

> Your new perspectives of AI or CI that does not exist yet. 
> 
> Your new work: Application of CI techniques to a research problem related to your PhD thesis project. 


# Notes
- both of them use surrogate gradient descent
- I would prefer to not use that and instead something usable in a self-supervised role

# Todo
- fix references M15, L22, C22, T20, P19
- Need to fill out the neurons, 
- add figures

# References
[[@chenDeepReinforcementLearning2022]]

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
	- ~~They also have a DSQN CV~~ 
		- They do not, I confused the subititle on table VI in Liu
		- It is the comparison
> - To further improve the performance, Tan et al. [28] proposed a more effective conversion method based on the more accurate approximation of the spiking firing rates. It reduced the conversion error based on a pretrained DQN, and achieved state-of-the-art performance on multiple Atari games.

[24] D. Patel, H. Hazan, D. J. Saunders, H. T. Siegelmann, and R. Kozma, “Improved robustness of reinforcement learning policies upon conversion to spiking neuronal network platforms applied to atari breakout game,” Neural Networks, vol. 120, pp. 108–115, 2019.
[[@patelImprovedRobustnessReinforcement2019]]

> is the first work to introduce spiking conversion methods to the domain of deep Q-learning. They demonstrated that both shallow and deep ReLU networks can be converted to SNNs without performance degradation on Atari game Breakout. Then, they showed that the converted SNN is more robust to input perturbations than the original neural network. However, it only focuses on improving the robustness rather than the performance of SNNs on Atari games.


[26] B. Rueckauer, I.-A. Lungu, Y. Hu, M. Pfeiffer, and S.-C. Liu, “Conversion of continuous-valued deep networks to efficient eventdriven networks for image classification,” Front. Neurosci., vol. 11, p. 682, Dec. 2017.
[[@rueckauerConversionContinuousValuedDeep2017]]

[44] J. Weng et al., “Tianshou: A highly modularized deep reinforcement learning library,” 2021, arXiv:2107.14171. 
[[@wengTianshouHighlyModularized2022]]

[45] Z. T. Wang and M. Ueda, “Convergent and efficient deep Q learning algorithm,” in Proc. Int. Conf. Learn. Represent., Mar. 2022, pp. 1–27.
[[@wangConvergentEfficientDeep2022]]

[^9]: Bendor, D. & Wilson, M. A. Biasing the content of hippocampal replay during sleep. Nature Neurosci. 15, 1439–1444 (2012).
[[@bendorBiasingContentHippocampal2012]]

[^10]: O’Neill, J., Pleydell-Bouverie, B., Dupret, D. & Csicsvari, J. Play it again: reactivation of waking experience and memory. Trends Neurosci. 33, 220–229 (2010). 
[[@oneillPlayItAgain2010]]

[[@zenkeVisualizingJointFuture2021]] 
[[@princeCurrentStateFuture2022]]
[[@mehonicBraininspiredComputingNeeds2022]]

[36] E. O. Neftci, H. Mostafa, and F. Zenke, “Surrogate gradient learning in spiking neural networks: Bringing the power of gradient-based optimization to spiking neural networks,” IEEE Signal Process. Mag., vol. 36, no. 6, pp. 51–63, Nov. 2019.