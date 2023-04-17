---
aliases: ["Chen et al. 2022"]
type: citation
status: open
priority: P5
people: ["D. Chen", "P. Peng", "T. Huang", "Y. Tian"]
priority: p1
Project: [PENG9569]
creationtag: 2022-06-16 13:34
people: [Ding Chen, Peixi Peng, Tiejun Huang, Yonghong Tian]
title: "Deep Reinforcement Learning with Spiking Q-learning"
dateadd: 2022-05-10T14:42:38Z
citetype: journalArticle
year: 2022
journal: arXiv:2201.09754 [cs]
URL: "NA"
DOI: "NA"
citekey: chenDeepReinforcementLearning2022
collection: DRL, Reviews, SNN - RL
infotags: [Computer Science - Artificial Intelligence, Computer Science - Machine Learning, Computer Science - Neural and Evolutionary Computing, three factor, drl, snn, rl, DSQN]
---

# Deep Reinforcement Learning with Spiking Q-learning

> [!Excerpt] Abstract
> Read::  ✅ Deep Reinforcement Learning with Spiking Q-learning D. Chen, P. Peng, T. Huang, Y. Tian 2022  #reading #citation
Print::  ✅ 2022-05-19
Zotero Link:: NA
Files:: [@chenDeepReinforcementLearning2022-MDnotes.md](file:///home/michaelt/Insync/m@tarlton.info/Google%20Drive/05.%20Obsidian/Obsidian/oslomet/50%20Reading/Zotero%20Papers/@chenDeepReinforcementLearning2022-MDnotes.md); [arXiv.org Snapshot](file:///home/michaelt/Insync/m@tarlton.info/Google%20Drive/06.%20Zotero/storage/TKDBAXKR/2201.html); [Chen et al_2022_Deep Reinforcement Learning with Spiking Q-learning.pdf](file:///home/michaelt/Insync/m@tarlton.info/Google%20Drive/06.%20Zotero/storage/LU25QILL/Chen%20et%20al_2022_Deep%20Reinforcement%20Learning%20with%20Spiking%20Q-learning.pdf); [chenDeepReinforcementLearning2022-zotero.md](file:///home/michaelt/Insync/m@tarlton.info/Google%20Drive/05.%20Obsidian/Obsidian/oslomet/50%20Reading/Zotero%20Papers/chenDeepReinforcementLearning2022-zotero.md)
Reading Note:: [[Chen 2022]]
Reading Topics:: [[Chen 2022 - topics]]
Reading Comments:: [[Chen 2022 - comments]]
Reading Glossary:: [[Chen 2022 - glossary]]

```dataview
TABLE without id
file.link as "Related Files",
title as "Title",
type as "type"
FROM "" AND -"ZZ. planning"
WHERE citekey = "chenDeepReinforcementLearning2022" 
SORT file.cday DESC
```

# Abstract
With the help of special neuromorphic hardware, spiking neural networks (SNNs) are expected to realize artificial intelligence with less energy consumption. It provides a promising energy-efficient way for realistic control tasks by combing SNNs and deep reinforcement learning (RL). There are only a few existing SNN-based RL methods at present. Most of them either lack generalization ability or employ Artificial Neural Networks (ANNs) to estimate value function in training. The former needs to tune numerous hyper-parameters for each scenario, and the latter limits the application of different types of RL algorithm and ignores the large energy consumption in training. To develop a robust spike-based RL method, we draw inspiration from non-spiking interneurons found in insects and propose the deep spiking Q-network (DSQN), using the membrane voltage of non-spiking neurons as the representation of Q-value, which can directly learn robust policies from high-dimensional sensory inputs using end-to-end RL. Experiments conducted on 17 Atari games demonstrate the effectiveness of DSQN by outperforming the ANN-based deep Q-network (DQN) in most games. Moreover, the experimental results show superior learning stability and robustness to adversarial attacks of DSQN.

# Quick Reference


# Top Comments
- Ok so I’m picking back up my reading flow after a long time
- I am using mathpix for the parts I will need to latex in
- See [[Chen 2022 - glossary#Loss function (pg. 3)]] for Loss function and other formulae
- I’m actually not liking this paper very much
- They pretty much just take a basic DQN and add spiking neurons

## Architecture
- They really do not address if the LIF layer feed into the next trad layer
- The way it is organized is that the trad layer and previous SN layer **both** feed into the next SN layer
- So it’s kinda just a tacked on hypernet
- I have no idea (in fact it seems not) if the SN output is fed to the trad layer
## Spike decoding
- Ok so each SN layer actually consists of two parts a “neuronal” and “synaptic” layer, the latter of which is read as Voltage value of the input spikes (?)
- See Figure 2 and section 3.2
- So they aren’t actually communicating on the spike per-se, but instead the membrane voltage
- **Actually this sisn’t totally correct, as the synaptic layer they speak of is the trad layer**
- Really not sure the spike matters at all
	- Except for the reset 
	- In Liu et al 2022 they split this into a soft and hard reset
	- 

# Topics
![[Chen 2022 - topics]]


# Tasks

# Further Reading
- [ ] [[@bellecSolutionLearningDilemma2020]] #reading #p2 
- [ ] [[@mnihHumanlevelControlDeep2015]] #reading #p2


----
# Notes
- They use [[Leaky Integrate-and-Fire]] neurons

----
# Extracted Annotations and Comments

> . To overcome the limitations of SNN in solving high-dimensional control problems, it would be natural to combine the energyefficiency of SNN with the optimality of deep RL (p. 1) 

> , these methods only apply to shallow SNNs and low-dimensional control tasks, or need to tune numerous hyper-parameters for each scenario [1] (p. 1) 

> several methods aim to apply the surrogate gradient method [11] to train SNN in RL (p. 1) 

> Since SNN usually uses the firing rate as the equivalent activation value [17] which is a discrete value between 0 and 1, it is hard to represent the value function of RL which doesn’t have a certain range in training. (p. 1) 

> several methods [15; 19] aim to convert the trained DQN to SNN for execution. In addition, several methods based on hybrid framework [21; 22] utilize SNN to model policy function (i.e., a probability distribution), and resort ANN to estimate value function for auxiliary training (p. 1) 

> , these methods may lose the potential biological plausibility of SNN, and limit the application of different types of RL algorithm (p. 1) 

> , it is necessary to develop a spike-based RL method where only SNN is used in both training and execution (p. 1) 

> hod where only SNN is used in both training and execution. The key issue is to design a new neuarXiv:2201.09754v1 [cs.NE] 21 Jan 202 (p. 1) 

> ral coding method to decode the spike-train into the results of value function, realizing end-to-end spike-based RL (p. 2) 

> voltage in all simulation time and make the learning stable, we argue that the statistics of membrane voltage rather than the last membrane voltage should be used to represent Q-value. (p. 2) 

> ly enhance spike-based RL and ensure strong robustness. The main contributions of this paper is summarized as follows: 1. A novel spike-based RL method, referred to as deep spiking Q-network (DSQN), is proposed, which could represent Q-value by the membrane voltage of nonspiking neurons. 2. The method achieves end-to-end Q-learning without any additional ANN for auxiliary training, and maintains the high biological plausibility of SNN. 3. The method is evaluated on 17 Atari games, and our results outperform ANN-based DQN on most of the games. Moreover, the experimental results show superior learning stability and robustness to adversarial attacks such as FGSM [9]. (p. 2) 

> Reward-based Learning by Three-factor Learning Rules To bridge the gap between the time scales of behavior and neuronal action potential, modern theories of synaptic plasticity assume that the co-activation of presynaptic and postsynaptic neurons sets a flag at the synapse, called eligibility trace [18]. Only if a third factor, signaling reward, punishment, surprise or novelty, exists while the flag is set, the synaptic weight will change. Although the theoretical framework of three-factor learning rules has been developed in the past few decades, experimental evidence supporting eligibility trace has only been collected in the past few years. Through the derivation of the RL rule for continuous time, the existing approaches have been able to solve the standard control tasks [7] and robot control tasks [13] (p. 2) 

> and lowdimensional control tasks. To solve these problems, Bellec et al. [1] propose a learning method for recurrently connected networks of spiking neurons, which is called e-prop (p. 2) 

> 2.3 Co-learning of Hybrid Framework Tang et al. [20] first propose the hybrid framework, composed of a spiking actor network (SAN) and a deep critic network. Through the co-learning of the two networks, these methods [21; 22] avoid the problem of value estimation using SNNs. Hence, these methods only work for actor-critic structure, and the energy consumption in the training process is much higher than the pure SNN methods [10]. (p. 2) 

> Following the surrogate gradient method [11], the spikebased backpropagation (BP) algorithm has quickly become the mainstream solution for training multi-layer SNNs [6; 5]. As shown in several open-source frameworks of SNNs [4; 16], the membrane voltage of non-spiking neurons is feasible to represent a continuous value in a spike-based BP method. However, how to use it to effectively train SNN with Q-learning has not been systematically studied and remains unsolved, which is the goal of this paper. (p. 2) 

> coding method in the following sections. 3.5 Deep Spiking Q-network The typical architecture of DSQN is shown in Figure 5, which consists of synaptic layers and neuronal layers. The synaptic layers include convolutional layers and fully-connected (FC) layers, each of which is followed by a neuronal layer. Except that the LI layer is used after the last FC layer, the other synaptic layers are followed by LIF layers. In DSQN, all bias parameters are omitted and all weight parameters are shared at all simulation time-steps. (p. 4) 

# Figures

