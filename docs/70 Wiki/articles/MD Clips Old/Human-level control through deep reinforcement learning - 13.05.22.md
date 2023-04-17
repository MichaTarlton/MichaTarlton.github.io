---
created: 2022-05-13T11:43:14 (UTC +02:00)
tags: []
source: https://www.nature.com/articles/nature14236?wm=book_wap_0005
author: Hassabis, Demis
---

# Human-level control through deep reinforcement learning | Nature



> ## Excerpt
> An artificial agent is developed that learns to play&nbsp;a diverse range of classic Atari 2600 computer games directly from sensory experience, achieving a&nbsp;performance comparable to that of an expert human player; this work paves the way to building general-purpose learning algorithms that bridge the divide between perception and action. For an artificial agent to be considered truly intelligent it needs to excel at a variety of tasks considered challenging for humans. To date, it has only been possible to create individual algorithms able to master a single discipline — for example, IBM's Deep Blue beat the human world champion at chess but was not able to do anything else. Now a team working at Google's DeepMind subsidiary has developed an artificial agent — dubbed a deep Q-network — that learns to play 49 classic Atari 2600 'arcade' games directly from sensory experience, achieving performance on a par with that of an expert human player. By combining reinforcement learning (selecting actions that maximize reward — in this case the game score) with deep learning (multilayered feature extraction from high-dimensional data — in this case the pixels), the game-playing agent takes artificial intelligence a step nearer the goal of systems capable of learning a diversity of challenging tasks from scratch. The theory of reinforcement learning provides a normative account1, deeply rooted in psychological2 and neuroscientific3 perspectives on animal behaviour, of how agents may optimize their control of an environment. To use reinforcement learning successfully in situations approaching real-world complexity, however, agents are confronted with a difficult task: they must derive efficient representations of the environment from high-dimensional sensory inputs, and use these to generalize past experience to new situations. Remarkably, humans and other animals seem to solve this problem through a harmonious combination of reinforcement learning and hierarchical sensory processing systems4,5, the former evidenced by a wealth of neural data revealing notable parallels between the phasic signals emitted by dopaminergic neurons and temporal difference reinforcement learning algorithms3. While reinforcement learning agents have achieved some successes in a variety of domains6,7,8, their applicability has previously been limited to domains in which useful features can be handcrafted, or to domains with fully observed, low-dimensional state spaces. Here we use recent advances in training deep neural networks9,10,11 to develop a novel artificial agent, termed a deep Q-network, that can learn successful policies directly from high-dimensional sensory inputs using end-to-end reinforcement learning. We tested this agent on the challenging domain of classic Atari 2600 games12. We demonstrate that the deep Q-network agent, receiving only the pixels and the game score as inputs, was able to surpass the performance of all previous algorithms and achieve a level comparable to that of a professional human games tester across a set of 49 games, using the same algorithm, network architecture and hyperparameters. This work bridges the divide between high-dimensional sensory inputs and actions, resulting in the first artificial agent that is capable of learning to excel at a diverse array of challenging tasks.

---
## Abstract

The theory of reinforcement learning provides a normative account[1](https://www.nature.com/articles/nature14236#ref-CR1 "Sutton, R. & Barto, A. Reinforcement Learning: An Introduction (MIT Press, 1998)"), deeply rooted in psychological[2](https://www.nature.com/articles/nature14236#ref-CR2 "Thorndike, E. L. Animal Intelligence: Experimental studies (Macmillan, 1911)") and neuroscientific[3](https://www.nature.com/articles/nature14236#ref-CR3 "Schultz, W., Dayan, P. & Montague, P. R. A neural substrate of prediction and reward. Science 275, 1593–1599 (1997)") perspectives on animal behaviour, of how agents may optimize their control of an environment. To use reinforcement learning successfully in situations approaching real-world complexity, however, agents are confronted with a difficult task: they must derive efficient representations of the environment from high-dimensional sensory inputs, and use these to generalize past experience to new situations. Remarkably, humans and other animals seem to solve this problem through a harmonious combination of reinforcement learning and hierarchical sensory processing systems[4](https://www.nature.com/articles/nature14236#ref-CR4 "Serre, T., Wolf, L. & Poggio, T. Object recognition with features inspired by visual cortex. Proc. IEEE. Comput. Soc. Conf. Comput. Vis. Pattern. Recognit. 994–1000 (2005)"),[5](https://www.nature.com/articles/nature14236#ref-CR5 "Fukushima, K. Neocognitron: A self-organizing neural network model for a mechanism of pattern recognition unaffected by shift in position. Biol. Cybern. 36, 193–202 (1980)"), the former evidenced by a wealth of neural data revealing notable parallels between the phasic signals emitted by dopaminergic neurons and temporal difference reinforcement learning algorithms[3](https://www.nature.com/articles/nature14236#ref-CR3 "Schultz, W., Dayan, P. & Montague, P. R. A neural substrate of prediction and reward. Science 275, 1593–1599 (1997)"). While reinforcement learning agents have achieved some successes in a variety of domains[6](https://www.nature.com/articles/nature14236#ref-CR6 "Tesauro, G. Temporal difference learning and TD-Gammon. Commun. ACM 38, 58–68 (1995)"),[7](https://www.nature.com/articles/nature14236#ref-CR7 "Riedmiller, M., Gabel, T., Hafner, R. & Lange, S. Reinforcement learning for robot soccer. Auton. Robots 27, 55–73 (2009)"),[8](https://www.nature.com/articles/nature14236#ref-CR8 "Diuk, C., Cohen, A. & Littman, M. L. An object-oriented representation for efficient reinforcement learning. Proc. Int. Conf. Mach. Learn. 240–247 (2008)"), their applicability has previously been limited to domains in which useful features can be handcrafted, or to domains with fully observed, low-dimensional state spaces. Here we use recent advances in training deep neural networks[9](https://www.nature.com/articles/nature14236#ref-CR9 "Bengio, Y. Learning deep architectures for AI. Foundations and Trends in Machine Learning 2, 1–127 (2009)"),[10](https://www.nature.com/articles/nature14236#ref-CR10 "Krizhevsky, A., Sutskever, I. & Hinton, G. ImageNet classification with deep convolutional neural networks. Adv. Neural Inf. Process. Syst. 25, 1106–1114 (2012)"),[11](https://www.nature.com/articles/nature14236#ref-CR11 "Hinton, G. E. & Salakhutdinov, R. R. Reducing the dimensionality of data with neural networks. Science 313, 504–507 (2006)") to develop a novel artificial agent, termed a deep Q-network, that can learn successful policies directly from high-dimensional sensory inputs using end-to-end reinforcement learning. We tested this agent on the challenging domain of classic Atari 2600 games[12](https://www.nature.com/articles/nature14236#ref-CR12 "Bellemare, M. G., Naddaf, Y., Veness, J. & Bowling, M. The arcade learning environment: An evaluation platform for general agents. J. Artif. Intell. Res. 47, 253–279 (2013)"). We demonstrate that the deep Q-network agent, receiving only the pixels and the game score as inputs, was able to surpass the performance of all previous algorithms and achieve a level comparable to that of a professional human games tester across a set of 49 games, using the same algorithm, network architecture and hyperparameters. This work bridges the divide between high-dimensional sensory inputs and actions, resulting in the first artificial agent that is capable of learning to excel at a diverse array of challenging tasks.

## Main

We set out to create a single algorithm that would be able to develop a wide range of competencies on a varied range of challenging tasks—a central goal of general artificial intelligence[13](https://www.nature.com/articles/nature14236#ref-CR13 "Legg, S. & Hutter, M. Universal Intelligence: a definition of machine intelligence. Minds Mach. 17, 391–444 (2007)") that has eluded previous efforts[8](https://www.nature.com/articles/nature14236#ref-CR8 "Diuk, C., Cohen, A. & Littman, M. L. An object-oriented representation for efficient reinforcement learning. Proc. Int. Conf. Mach. Learn. 240–247 (2008)"),[14](https://www.nature.com/articles/nature14236#ref-CR14 "Genesereth, M., Love, N. & Pell, B. General game playing: overview of the AAAI competition. AI Mag. 26, 62–72 (2005)"),[15](https://www.nature.com/articles/nature14236#ref-CR15 "Bellemare, M. G., Veness, J. & Bowling, M. Investigating contingency awareness using Atari 2600 games. Proc. Conf. AAAI. Artif. Intell. 864–871 (2012)"). To achieve this, we developed a novel agent, a deep Q-network (DQN), which is able to combine reinforcement learning with a class of artificial neural network[16](https://www.nature.com/articles/nature14236#ref-CR16 "McClelland, J. L., Rumelhart, D. E. & Group, T. P. R. Parallel Distributed Processing: Explorations in the Microstructure of Cognition (MIT Press, 1986)") known as deep neural networks. Notably, recent advances in deep neural networks[9](https://www.nature.com/articles/nature14236#ref-CR9 "Bengio, Y. Learning deep architectures for AI. Foundations and Trends in Machine Learning 2, 1–127 (2009)"),[10](https://www.nature.com/articles/nature14236#ref-CR10 "Krizhevsky, A., Sutskever, I. & Hinton, G. ImageNet classification with deep convolutional neural networks. Adv. Neural Inf. Process. Syst. 25, 1106–1114 (2012)"),[11](https://www.nature.com/articles/nature14236#ref-CR11 "Hinton, G. E. & Salakhutdinov, R. R. Reducing the dimensionality of data with neural networks. Science 313, 504–507 (2006)"), in which several layers of nodes are used to build up progressively more abstract representations of the data, have made it possible for artificial neural networks to learn concepts such as object categories directly from raw sensory data. We use one particularly successful architecture, the deep convolutional network[17](https://www.nature.com/articles/nature14236#ref-CR17 "LeCun, Y., Bottou, L., Bengio, Y. & Haffner, P. Gradient-based learning applied to document recognition. Proc. IEEE 86, 2278–2324 (1998)"), which uses hierarchical layers of tiled convolutional filters to mimic the effects of receptive fields—inspired by Hubel and Wiesel’s seminal work on feedforward processing in early visual cortex[18](https://www.nature.com/articles/nature14236#ref-CR18 "Hubel, D. H. & Wiesel, T. N. Shape and arrangement of columns in cat’s striate cortex. J. Physiol. 165, 559–568 (1963)")—thereby exploiting the local spatial correlations present in images, and building in robustness to natural transformations such as changes of viewpoint or scale.

We consider tasks in which the agent interacts with an environment through a sequence of observations, actions and rewards. The goal of the agent is to select actions in a fashion that maximizes cumulative future reward. More formally, we use a deep convolutional neural network to approximate the optimal action-value function

![](https://media.springernature.com/lw365/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_Equ1_HTML.jpg)

which is the maximum sum of rewards *r**t* discounted by *γ* at each time-step *t*, achievable by a behaviour policy *π = P*(*a|s*), after making an observation (*s*) and taking an action (*a*) (see Methods)[19](https://www.nature.com/articles/nature14236#ref-CR19 "Watkins, C. J. & Dayan, P. Q-learning. Mach. Learn. 8, 279–292 (1992)").

Reinforcement learning is known to be unstable or even to diverge when a nonlinear function approximator such as a neural network is used to represent the action-value (also known as ![](https://media.springernature.com/lw13/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq1_HTML.jpg)) function[20](https://www.nature.com/articles/nature14236#ref-CR20 "Tsitsiklis, J. & Roy, B. V. An analysis of temporal-difference learning with function approximation. IEEE Trans. Automat. Contr. 42, 674–690 (1997)"). This instability has several causes: the correlations present in the sequence of observations, the fact that small updates to ![](https://media.springernature.com/lw12/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq2_HTML.jpg) may significantly change the policy and therefore change the data distribution, and the correlations between the action-values (![](https://media.springernature.com/lw13/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq3_HTML.jpg)) and the target values ![](https://media.springernature.com/lw129/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq4_HTML.jpg). We address these instabilities with a novel variant of Q-learning, which uses two key ideas. First, we used a biologically inspired mechanism termed experience replay[21](https://www.nature.com/articles/nature14236#ref-CR21 "McClelland, J. L., McNaughton, B. L. & O’Reilly, R. C. Why there are complementary learning systems in the hippocampus and neocortex: insights from the successes and failures of connectionist models of learning and memory. Psychol. Rev. 102, 419–457 (1995)"),[22](https://www.nature.com/articles/nature14236#ref-CR22 "O’Neill, J., Pleydell-Bouverie, B., Dupret, D. & Csicsvari, J. Play it again: reactivation of waking experience and memory. Trends Neurosci. 33, 220–229 (2010)"),[23](https://www.nature.com/articles/nature14236#ref-CR23 "Lin, L.-J. Reinforcement learning for robots using neural networks. Technical Report, DTIC Document. (1993)") that randomizes over the data, thereby removing correlations in the observation sequence and smoothing over changes in the data distribution (see below for details). Second, we used an iterative update that adjusts the action-values (![](https://media.springernature.com/lw13/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq5_HTML.jpg)) towards target values that are only periodically updated, thereby reducing correlations with the target.

While other stable methods exist for training neural networks in the reinforcement learning setting, such as neural fitted Q-iteration[24](https://www.nature.com/articles/nature14236#ref-CR24 "Riedmiller, M. Neural fitted Q iteration - first experiences with a data efficient neural reinforcement learning method. Mach. Learn.: ECML 3720, 317–328 (Springer, 2005)"), these methods involve the repeated training of networks *de novo* on hundreds of iterations. Consequently, these methods, unlike our algorithm, are too inefficient to be used successfully with large neural networks. We parameterize an approximate value function ![](https://media.springernature.com/lw60/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq6_HTML.jpg) using the deep convolutional neural network shown in [Fig. 1](https://www.nature.com/articles/nature14236#Fig1), in which *θ*i are the parameters (that is, weights) of the Q-network at iteration *i*. To perform experience replay we store the agent’s experiences *e**t* = (*s**t*,*a**t*,*r**t*,*s**t* + 1) at each time-step *t* in a data set *D**t* = {*e*1,…,*e**t*}. During learning, we apply Q-learning updates, on samples (or minibatches) of experience (*s*,*a*,*r*,*s′*) ∼ *U*(*D*), drawn uniformly at random from the pool of stored samples. The Q-learning update at iteration ![](https://media.springernature.com/lw5/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq7_HTML.jpg) uses the following loss function:

![](https://media.springernature.com/lw382/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_Equ2_HTML.jpg)

in which *γ* is the discount factor determining the agent’s horizon, *θ**i* are the parameters of the Q-network at iteration *i* and ![](https://media.springernature.com/lw19/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq8_HTML.jpg) are the network parameters used to compute the target at iteration *i*. The target network parameters ![](https://media.springernature.com/lw19/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq9_HTML.jpg) are only updated with the Q-network parameters (*θ**i*) every *C* steps and are held fixed between individual updates (see Methods).

**Figure 1: Schematic illustration of the convolutional neural network.**

[![figure 1](https://media.springernature.com/lw685/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_Fig1_HTML.jpg)](https://www.nature.com/articles/nature14236/figures/1)

The details of the architecture are explained in the Methods. The input to the neural network consists of an 84 × 84 × 4 image produced by the preprocessing map ![](https://media.springernature.com/lw8/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq55_HTML.jpg), followed by three convolutional layers (note: snaking blue line symbolizes sliding of each filter across input image) and two fully connected layers with a single output for each valid action. Each hidden layer is followed by a rectifier nonlinearity (that is, ![](https://media.springernature.com/lw58/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq56_HTML.jpg)).

[PowerPoint slide](https://www.nature.com/articles/nature14236#MOESM118)

[Full size image](https://www.nature.com/articles/nature14236/figures/1)

To evaluate our DQN agent, we took advantage of the Atari 2600 platform, which offers a diverse array of tasks (*n* = 49) designed to be difficult and engaging for human players. We used the same network architecture, hyperparameter values (see [Extended Data Table 1](https://www.nature.com/articles/nature14236#Tab1)) and learning procedure throughout—taking high-dimensional data (![](https://media.springernature.com/lw67/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq10_HTML.jpg) colour video at 60 Hz) as input—to demonstrate that our approach robustly learns successful policies over a variety of games based solely on sensory inputs with only very minimal prior knowledge (that is, merely the input data were visual images, and the number of actions available in each game, but not their correspondences; see Methods). Notably, our method was able to train large neural networks using a reinforcement learning signal and stochastic gradient descent in a stable manner— illustrated by the temporal evolution of two indices of learning (the agent’s average score-per-episode and average predicted Q-values; see [Fig. 2](https://www.nature.com/articles/nature14236#Fig2) and Supplementary Discussion for details).

**Figure 2: Training curves tracking the agent’s average score and average predicted action-value.**

[![figure 2](https://media.springernature.com/lw685/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_Fig2_HTML.jpg)](https://www.nature.com/articles/nature14236/figures/2)

**a**, Each point is the average score achieved per episode after the agent is run with *ε*\-greedy policy (*ε* = 0.05) for 520 k frames on Space Invaders. **b**, Average score achieved per episode for Seaquest. **c**, Average predicted action-value on a held-out set of states on Space Invaders. Each point on the curve is the average of the action-value Q computed over the held-out set of states. Note that Q-values are scaled due to clipping of rewards (see Methods). **d**, Average predicted action-value on Seaquest. See Supplementary Discussion for details.

[PowerPoint slide](https://www.nature.com/articles/nature14236#MOESM119)

[Full size image](https://www.nature.com/articles/nature14236/figures/2)

We compared DQN with the best performing methods from the reinforcement learning literature on the 49 games where results were available[12](https://www.nature.com/articles/nature14236#ref-CR12 "Bellemare, M. G., Naddaf, Y., Veness, J. & Bowling, M. The arcade learning environment: An evaluation platform for general agents. J. Artif. Intell. Res. 47, 253–279 (2013)"),[15](https://www.nature.com/articles/nature14236#ref-CR15 "Bellemare, M. G., Veness, J. & Bowling, M. Investigating contingency awareness using Atari 2600 games. Proc. Conf. AAAI. Artif. Intell. 864–871 (2012)"). In addition to the learned agents, we also report scores for a professional human games tester playing under controlled conditions and a policy that selects actions uniformly at random ([Extended Data Table 2](https://www.nature.com/articles/nature14236#Tab2) and [Fig. 3](https://www.nature.com/articles/nature14236#Fig3), denoted by 100% (human) and 0% (random) on *y* axis; see Methods). Our DQN method outperforms the best existing reinforcement learning methods on 43 of the games without incorporating any of the additional prior knowledge about Atari 2600 games used by other approaches (for example, refs [12](https://www.nature.com/articles/nature14236#ref-CR12 "Bellemare, M. G., Naddaf, Y., Veness, J. & Bowling, M. The arcade learning environment: An evaluation platform for general agents. J. Artif. Intell. Res. 47, 253–279 (2013)"), [15](https://www.nature.com/articles/nature14236#ref-CR15 "Bellemare, M. G., Veness, J. & Bowling, M. Investigating contingency awareness using Atari 2600 games. Proc. Conf. AAAI. Artif. Intell. 864–871 (2012)")). Furthermore, our DQN agent performed at a level that was comparable to that of a professional human games tester across the set of 49 games, achieving more than 75% of the human score on more than half of the games (29 games; see [Fig. 3](https://www.nature.com/articles/nature14236#Fig3), Supplementary Discussion and [Extended Data Table 2](https://www.nature.com/articles/nature14236#Tab2)). In additional simulations (see Supplementary Discussion and [Extended Data Tables 3](https://www.nature.com/articles/nature14236#Tab3) and [4](https://www.nature.com/articles/nature14236#Tab4)), we demonstrate the importance of the individual core components of the DQN agent—the replay memory, separate target Q-network and deep convolutional network architecture—by disabling them and demonstrating the detrimental effects on performance.

**Figure 3: Comparison of the DQN agent with the best reinforcement learning methods[15](https://www.nature.com/articles/nature14236#ref-CR15 "Bellemare, M. G., Veness, J. & Bowling, M. Investigating contingency awareness using Atari 2600 games. Proc. Conf. AAAI. Artif. Intell. 864–871 (2012)") in the literature.**

[![figure 3](https://media.springernature.com/lw685/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_Fig3_HTML.jpg)](https://www.nature.com/articles/nature14236/figures/3)

The performance of DQN is normalized with respect to a professional human games tester (that is, 100% level) and random play (that is, 0% level). Note that the normalized performance of DQN, expressed as a percentage, is calculated as: 100 × (DQN score − random play score)/(human score − random play score). It can be seen that DQN outperforms competing methods (also see [Extended Data Table 2](https://www.nature.com/articles/nature14236#Tab2)) in almost all the games, and performs at a level that is broadly comparable with or superior to a professional human games tester (that is, operationalized as a level of 75% or above) in the majority of games. Audio output was disabled for both human players and agents. Error bars indicate s.d. across the 30 evaluation episodes, starting with different initial conditions.

[PowerPoint slide](https://www.nature.com/articles/nature14236#MOESM120)

[Full size image](https://www.nature.com/articles/nature14236/figures/3)

We next examined the representations learned by DQN that underpinned the successful performance of the agent in the context of the game Space Invaders (see [Supplementary Video 1](https://www.nature.com/articles/nature14236#MOESM123) for a demonstration of the performance of DQN), by using a technique developed for the visualization of high-dimensional data called ‘t-SNE’[25](https://www.nature.com/articles/nature14236#ref-CR25 "Van der Maaten, L. J. P. & Hinton, G. E. Visualizing high-dimensional data using t-SNE. J. Mach. Learn. Res. 9, 2579–2605 (2008)") ([Fig. 4](https://www.nature.com/articles/nature14236#Fig4)). As expected, the t-SNE algorithm tends to map the DQN representation of perceptually similar states to nearby points. Interestingly, we also found instances in which the t-SNE algorithm generated similar embeddings for DQN representations of states that are close in terms of expected reward but perceptually dissimilar ([Fig. 4](https://www.nature.com/articles/nature14236#Fig4), bottom right, top left and middle), consistent with the notion that the network is able to learn representations that support adaptive behaviour from high-dimensional sensory inputs. Furthermore, we also show that the representations learned by DQN are able to generalize to data generated from policies other than its own—in simulations where we presented as input to the network game states experienced during human and agent play, recorded the representations of the last hidden layer, and visualized the embeddings generated by the t-SNE algorithm ([Extended Data Fig. 1](https://www.nature.com/articles/nature14236#Fig5) and Supplementary Discussion). [Extended Data Fig. 2](https://www.nature.com/articles/nature14236#Fig6) provides an additional illustration of how the representations learned by DQN allow it to accurately predict state and action values.

**Figure 4: Two-dimensional t-SNE embedding of the representations in the last hidden layer assigned by DQN to game states experienced while playing Space Invaders.**

[![figure 4](https://media.springernature.com/lw685/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_Fig4_HTML.jpg)](https://www.nature.com/articles/nature14236/figures/4)

The plot was generated by letting the DQN agent play for 2 h of real game time and running the t-SNE algorithm[25](https://www.nature.com/articles/nature14236#ref-CR25 "Van der Maaten, L. J. P. & Hinton, G. E. Visualizing high-dimensional data using t-SNE. J. Mach. Learn. Res. 9, 2579–2605 (2008)") on the last hidden layer representations assigned by DQN to each experienced game state. The points are coloured according to the state values (*V*, maximum expected reward of a state) predicted by DQN for the corresponding game states (ranging from dark red (highest *V*) to dark blue (lowest *V*)). The screenshots corresponding to a selected number of points are shown. The DQN agent predicts high state values for both full (top right screenshots) and nearly complete screens (bottom left screenshots) because it has learned that completing a screen leads to a new screen full of enemy ships. Partially completed screens (bottom screenshots) are assigned lower state values because less immediate reward is available. The screens shown on the bottom right and top left and middle are less perceptually similar than the other examples but are still mapped to nearby representations and similar values because the orange bunkers do not carry great significance near the end of a level. With permission from Square Enix Limited.

[PowerPoint slide](https://www.nature.com/articles/nature14236#MOESM121)

[Full size image](https://www.nature.com/articles/nature14236/figures/4)

It is worth noting that the games in which DQN excels are extremely varied in their nature, from side-scrolling shooters (River Raid) to boxing games (Boxing) and three-dimensional car-racing games (Enduro). Indeed, in certain games DQN is able to discover a relatively long-term strategy (for example, Breakout: the agent learns the optimal strategy, which is to first dig a tunnel around the side of the wall allowing the ball to be sent around the back to destroy a large number of blocks; see [Supplementary Video 2](https://www.nature.com/articles/nature14236#MOESM124) for illustration of development of DQN’s performance over the course of training). Nevertheless, games demanding more temporally extended planning strategies still constitute a major challenge for all existing agents including DQN (for example, Montezuma’s Revenge).

In this work, we demonstrate that a single architecture can successfully learn control policies in a range of different environments with only very minimal prior knowledge, receiving only the pixels and the game score as inputs, and using the same algorithm, network architecture and hyperparameters on each game, privy only to the inputs a human player would have. In contrast to previous work[24](https://www.nature.com/articles/nature14236#ref-CR24 "Riedmiller, M. Neural fitted Q iteration - first experiences with a data efficient neural reinforcement learning method. Mach. Learn.: ECML 3720, 317–328 (Springer, 2005)"),[26](https://www.nature.com/articles/nature14236#ref-CR26 "Lange, S. & Riedmiller, M. Deep auto-encoder neural networks in reinforcement learning. Proc. Int. Jt. Conf. Neural. Netw. 1–8 (2010)"), our approach incorporates ‘end-to-end’ reinforcement learning that uses reward to continuously shape representations within the convolutional network towards salient features of the environment that facilitate value estimation. This principle draws on neurobiological evidence that reward signals during perceptual learning may influence the characteristics of representations within primate visual cortex[27](https://www.nature.com/articles/nature14236#ref-CR27 "Law, C.-T. & Gold, J. I. Reinforcement learning can account for associative and perceptual learning on a visual decision task. Nature Neurosci. 12, 655 (2009)"),[28](https://www.nature.com/articles/nature14236#ref-CR28 "Sigala, N. & Logothetis, N. K. Visual categorization shapes feature selectivity in the primate temporal cortex. Nature 415, 318–320 (2002)"). Notably, the successful integration of reinforcement learning with deep network architectures was critically dependent on our incorporation of a replay algorithm[21](https://www.nature.com/articles/nature14236#ref-CR21 "McClelland, J. L., McNaughton, B. L. & O’Reilly, R. C. Why there are complementary learning systems in the hippocampus and neocortex: insights from the successes and failures of connectionist models of learning and memory. Psychol. Rev. 102, 419–457 (1995)"),[22](https://www.nature.com/articles/nature14236#ref-CR22 "O’Neill, J., Pleydell-Bouverie, B., Dupret, D. & Csicsvari, J. Play it again: reactivation of waking experience and memory. Trends Neurosci. 33, 220–229 (2010)"),[23](https://www.nature.com/articles/nature14236#ref-CR23 "Lin, L.-J. Reinforcement learning for robots using neural networks. Technical Report, DTIC Document. (1993)") involving the storage and representation of recently experienced transitions. Convergent evidence suggests that the hippocampus may support the physical realization of such a process in the mammalian brain, with the time-compressed reactivation of recently experienced trajectories during offline periods[21](https://www.nature.com/articles/nature14236#ref-CR21 "McClelland, J. L., McNaughton, B. L. & O’Reilly, R. C. Why there are complementary learning systems in the hippocampus and neocortex: insights from the successes and failures of connectionist models of learning and memory. Psychol. Rev. 102, 419–457 (1995)"),[22](https://www.nature.com/articles/nature14236#ref-CR22 "O’Neill, J., Pleydell-Bouverie, B., Dupret, D. & Csicsvari, J. Play it again: reactivation of waking experience and memory. Trends Neurosci. 33, 220–229 (2010)") (for example, waking rest) providing a putative mechanism by which value functions may be efficiently updated through interactions with the basal ganglia[22](https://www.nature.com/articles/nature14236#ref-CR22 "O’Neill, J., Pleydell-Bouverie, B., Dupret, D. & Csicsvari, J. Play it again: reactivation of waking experience and memory. Trends Neurosci. 33, 220–229 (2010)"). In the future, it will be important to explore the potential use of biasing the content of experience replay towards salient events, a phenomenon that characterizes empirically observed hippocampal replay[29](https://www.nature.com/articles/nature14236#ref-CR29 "Bendor, D. & Wilson, M. A. Biasing the content of hippocampal replay during sleep. Nature Neurosci. 15, 1439–1444 (2012)"), and relates to the notion of ‘prioritized sweeping’[30](https://www.nature.com/articles/nature14236#ref-CR30 "Moore, A. & Atkeson, C. Prioritized sweeping: reinforcement learning with less data and less real time. Mach. Learn. 13, 103–130 (1993)") in reinforcement learning. Taken together, our work illustrates the power of harnessing state-of-the-art machine learning techniques with biologically inspired mechanisms to create agents that are capable of learning to master a diverse array of challenging tasks.

## Methods

### Preprocessing

Working directly with raw Atari 2600 frames, which are 210 × 160 pixel images with a 128-colour palette, can be demanding in terms of computation and memory requirements. We apply a basic preprocessing step aimed at reducing the input dimensionality and dealing with some artefacts of the Atari 2600 emulator. First, to encode a single frame we take the maximum value for each pixel colour value over the frame being encoded and the previous frame. This was necessary to remove flickering that is present in games where some objects appear only in even frames while other objects appear only in odd frames, an artefact caused by the limited number of sprites Atari 2600 can display at once. Second, we then extract the Y channel, also known as luminance, from the RGB frame and rescale it to 84 × 84. The function ![](https://media.springernature.com/lw8/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq11_HTML.jpg) from algorithm 1 described below applies this preprocessing to the *m* most recent frames and stacks them to produce the input to the Q-function, in which *m* = 4, although the algorithm is robust to different values of *m* (for example, 3 or 5).

### Code availability

The source code can be accessed at [https://sites.google.com/a/deepmind.com/dqn](https://sites.google.com/a/deepmind.com/dqn) for non-commercial uses only.

### Model architecture

There are several possible ways of parameterizing Q using a neural network. Because Q maps history–action pairs to scalar estimates of their Q-value, the history and the action have been used as inputs to the neural network by some previous approaches[24](https://www.nature.com/articles/nature14236#ref-CR24 "Riedmiller, M. Neural fitted Q iteration - first experiences with a data efficient neural reinforcement learning method. Mach. Learn.: ECML 3720, 317–328 (Springer, 2005)"),[26](https://www.nature.com/articles/nature14236#ref-CR26 "Lange, S. & Riedmiller, M. Deep auto-encoder neural networks in reinforcement learning. Proc. Int. Jt. Conf. Neural. Netw. 1–8 (2010)"). The main drawback of this type of architecture is that a separate forward pass is required to compute the Q-value of each action, resulting in a cost that scales linearly with the number of actions. We instead use an architecture in which there is a separate output unit for each possible action, and only the state representation is an input to the neural network. The outputs correspond to the predicted Q-values of the individual actions for the input state. The main advantage of this type of architecture is the ability to compute Q-values for all possible actions in a given state with only a single forward pass through the network.

The exact architecture, shown schematically in [Fig. 1](https://www.nature.com/articles/nature14236#Fig1), is as follows. The input to the neural network consists of an 84 × 84 × 4 image produced by the preprocessing map ![](https://media.springernature.com/lw8/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq12_HTML.jpg). The first hidden layer convolves 32 filters of 8 × 8 with stride 4 with the input image and applies a rectifier nonlinearity[31](https://www.nature.com/articles/nature14236#ref-CR31 "Jarrett, K., Kavukcuoglu, K., Ranzato, M. A. & LeCun, Y. What is the best multi-stage architecture for object recognition? Proc. IEEE. Int. Conf. Comput. Vis. 2146–2153 (2009)"),[32](https://www.nature.com/articles/nature14236#ref-CR32 "Nair, V. & Hinton, G. E. Rectified linear units improve restricted Boltzmann machines. Proc. Int. Conf. Mach. Learn. 807–814 (2010)"). The second hidden layer convolves 64 filters of 4 × 4 with stride 2, again followed by a rectifier nonlinearity. This is followed by a third convolutional layer that convolves 64 filters of 3 × 3 with stride 1 followed by a rectifier. The final hidden layer is fully-connected and consists of 512 rectifier units. The output layer is a fully-connected linear layer with a single output for each valid action. The number of valid actions varied between 4 and 18 on the games we considered.

### Training details

We performed experiments on 49 Atari 2600 games where results were available for all other comparable methods[12](https://www.nature.com/articles/nature14236#ref-CR12 "Bellemare, M. G., Naddaf, Y., Veness, J. & Bowling, M. The arcade learning environment: An evaluation platform for general agents. J. Artif. Intell. Res. 47, 253–279 (2013)"),[15](https://www.nature.com/articles/nature14236#ref-CR15 "Bellemare, M. G., Veness, J. & Bowling, M. Investigating contingency awareness using Atari 2600 games. Proc. Conf. AAAI. Artif. Intell. 864–871 (2012)"). A different network was trained on each game: the same network architecture, learning algorithm and hyperparameter settings (see [Extended Data Table 1](https://www.nature.com/articles/nature14236#Tab1)) were used across all games, showing that our approach is robust enough to work on a variety of games while incorporating only minimal prior knowledge (see below). While we evaluated our agents on unmodified games, we made one change to the reward structure of the games during training only. As the scale of scores varies greatly from game to game, we clipped all positive rewards at 1 and all negative rewards at −1, leaving 0 rewards unchanged. Clipping the rewards in this manner limits the scale of the error derivatives and makes it easier to use the same learning rate across multiple games. At the same time, it could affect the performance of our agent since it cannot differentiate between rewards of different magnitude. For games where there is a life counter, the Atari 2600 emulator also sends the number of lives left in the game, which is then used to mark the end of an episode during training.

In these experiments, we used the RMSProp (see [http://www.cs.toronto.edu/~tijmen/csc321/slides/lecture\_slides\_lec6.pdf](http://www.cs.toronto.edu/~tijmen/csc321/slides/lecture_slides_lec6.pdf) ) algorithm with minibatches of size 32. The behaviour policy during training was *ε*\-greedy with *ε* annealed linearly from 1.0 to 0.1 over the first million frames, and fixed at 0.1 thereafter. We trained for a total of 50 million frames (that is, around 38 days of game experience in total) and used a replay memory of 1 million most recent frames.

Following previous approaches to playing Atari 2600 games, we also use a simple frame-skipping technique[15](https://www.nature.com/articles/nature14236#ref-CR15 "Bellemare, M. G., Veness, J. & Bowling, M. Investigating contingency awareness using Atari 2600 games. Proc. Conf. AAAI. Artif. Intell. 864–871 (2012)"). More precisely, the agent sees and selects actions on every *k*th frame instead of every frame, and its last action is repeated on skipped frames. Because running the emulator forward for one step requires much less computation than having the agent select an action, this technique allows the agent to play roughly *k* times more games without significantly increasing the runtime. We use *k* = 4 for all games.

The values of all the hyperparameters and optimization parameters were selected by performing an informal search on the games Pong, Breakout, Seaquest, Space Invaders and Beam Rider. We did not perform a systematic grid search owing to the high computational cost. These parameters were then held fixed across all other games. The values and descriptions of all hyperparameters are provided in [Extended Data Table 1](https://www.nature.com/articles/nature14236#Tab1).

Our experimental setup amounts to using the following minimal prior knowledge: that the input data consisted of visual images (motivating our use of a convolutional deep network), the game-specific score (with no modification), number of actions, although not their correspondences (for example, specification of the up ‘button’) and the life count.

### Evaluation procedure

The trained agents were evaluated by playing each game 30 times for up to 5 min each time with different initial random conditions (‘no-op’; see [Extended Data Table 1](https://www.nature.com/articles/nature14236#Tab1)) and an *ε*\-greedy policy with *ε* = 0.05. This procedure is adopted to minimize the possibility of overfitting during evaluation. The random agent served as a baseline comparison and chose a random action at 10 Hz which is every sixth frame, repeating its last action on intervening frames. 10 Hz is about the fastest that a human player can select the ‘fire’ button, and setting the random agent to this frequency avoids spurious baseline scores in a handful of the games. We did also assess the performance of a random agent that selected an action at 60 Hz (that is, every frame). This had a minimal effect: changing the normalized DQN performance by more than 5% in only six games (Boxing, Breakout, Crazy Climber, Demon Attack, Krull and Robotank), and in all these games DQN outperformed the expert human by a considerable margin.

The professional human tester used the same emulator engine as the agents, and played under controlled conditions. The human tester was not allowed to pause, save or reload games. As in the original Atari 2600 environment, the emulator was run at 60 Hz and the audio output was disabled: as such, the sensory input was equated between human player and agents. The human performance is the average reward achieved from around 20 episodes of each game lasting a maximum of 5 min each, following around 2 h of practice playing each game.

### Algorithm

We consider tasks in which an agent interacts with an environment, in this case the Atari emulator, in a sequence of actions, observations and rewards. At each time-step the agent selects an action ![](https://media.springernature.com/lw12/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq13_HTML.jpg) from the set of legal game actions, ![](https://media.springernature.com/lw92/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq14_HTML.jpg). The action is passed to the emulator and modifies its internal state and the game score. In general the environment may be stochastic. The emulator’s internal state is not observed by the agent; instead the agent observes an image ![](https://media.springernature.com/lw37/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq15_HTML.jpg) from the emulator, which is a vector of pixel values representing the current screen. In addition it receives a reward *r**t* representing the change in game score. Note that in general the game score may depend on the whole previous sequence of actions and observations; feedback about an action may only be received after many thousands of time-steps have elapsed.

Because the agent only observes the current screen, the task is partially observed[33](https://www.nature.com/articles/nature14236#ref-CR33 "Kaelbling, L. P., Littman, M. L. & Cassandra, A. R. Planning and acting in partially observable stochastic domains. Artificial Intelligence 101, 99–134 (1994)") and many emulator states are perceptually aliased (that is, it is impossible to fully understand the current situation from only the current screen ![](https://media.springernature.com/lw12/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq16_HTML.jpg)). Therefore, sequences of actions and observations, ![](https://media.springernature.com/lw139/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq17_HTML.jpg), are input to the algorithm, which then learns game strategies depending upon these sequences. All sequences in the emulator are assumed to terminate in a finite number of time-steps. This formalism gives rise to a large but finite Markov decision process (MDP) in which each sequence is a distinct state. As a result, we can apply standard reinforcement learning methods for MDPs, simply by using the complete sequence *s**t* as the state representation at time *t*.

The goal of the agent is to interact with the emulator by selecting actions in a way that maximizes future rewards. We make the standard assumption that future rewards are discounted by a factor of *γ* per time-step (*γ* was set to 0.99 throughout), and define the future discounted return at time *t* as ![](https://media.springernature.com/lw97/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq18_HTML.jpg), in which *T* is the time-step at which the game terminates. We define the optimal action-value function ![](https://media.springernature.com/lw45/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq19_HTML.jpg) as the maximum expected return achievable by following any policy, after seeing some sequence ![](https://media.springernature.com/lw6/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq20_HTML.jpg) and then taking some action *a*, ![](https://media.springernature.com/lw183/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq21_HTML.jpg) in which *π* is a policy mapping sequences to actions (or distributions over actions).

The optimal action-value function obeys an important identity known as the Bellman equation. This is based on the following intuition: if the optimal value ![](https://media.springernature.com/lw53/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq22_HTML.jpg) of the sequence *s′* at the next time-step was known for all possible actions *a′*, then the optimal strategy is to select the action *a′* maximizing the expected value of ![](https://media.springernature.com/lw82/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq23_HTML.jpg):

![](https://media.springernature.com/lw209/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_Equ3_HTML.jpg)

The basic idea behind many reinforcement learning algorithms is to estimate the action-value function by using the Bellman equation as an iterative update, ![](https://media.springernature.com/lw209/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq24_HTML.jpg). Such value iteration algorithms converge to the optimal action-value function, ![](https://media.springernature.com/lw47/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq25_HTML.jpg) as ![](https://media.springernature.com/lw33/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq26_HTML.jpg). In practice, this basic approach is impractical, because the action-value function is estimated separately for each sequence, without any generalization. Instead, it is common to use a function approximator to estimate the action-value function, ![](https://media.springernature.com/lw113/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq27_HTML.jpg). In the reinforcement learning community this is typically a linear function approximator, but sometimes a nonlinear function approximator is used instead, such as a neural network. We refer to a neural network function approximator with weights *θ* as a Q-network. A Q-network can be trained by adjusting the parameters *θ**i* at iteration *i* to reduce the mean-squared error in the Bellman equation, where the optimal target values ![](https://media.springernature.com/lw125/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq28_HTML.jpg) are substituted with approximate target values ![](https://media.springernature.com/lw144/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq29_HTML.jpg), using parameters ![](https://media.springernature.com/lw16/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq30_HTML.jpg)from some previous iteration. This leads to a sequence of loss functions *L**i*(*θ**i*) that changes at each iteration *i*,

![](https://media.springernature.com/lw253/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_Equ4_HTML.jpg)

Note that the targets depend on the network weights; this is in contrast with the targets used for supervised learning, which are fixed before learning begins. At each stage of optimization, we hold the parameters from the previous iteration *θ**i*− fixed when optimizing the *i*th loss function *L**i*(*θ**i*), resulting in a sequence of well-defined optimization problems. The final term is the variance of the targets, which does not depend on the parameters *θ**i* that we are currently optimizing, and may therefore be ignored. Differentiating the loss function with respect to the weights we arrive at the following gradient:

![](https://media.springernature.com/lw391/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_Equ5_HTML.jpg)

Rather than computing the full expectations in the above gradient, it is often computationally expedient to optimize the loss function by stochastic gradient descent. The familiar Q-learning algorithm[19](https://www.nature.com/articles/nature14236#ref-CR19 "Watkins, C. J. & Dayan, P. Q-learning. Mach. Learn. 8, 279–292 (1992)") can be recovered in this framework by updating the weights after every time step, replacing the expectations using single samples, and setting ![](https://media.springernature.com/lw60/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq31_HTML.jpg).

Note that this algorithm is model-free: it solves the reinforcement learning task directly using samples from the emulator, without explicitly estimating the reward and transition dynamics ![](https://media.springernature.com/lw59/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq32_HTML.jpg). It is also off-policy: it learns about the greedy policy ![](https://media.springernature.com/lw135/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq33_HTML.jpg), while following a behaviour distribution that ensures adequate exploration of the state space. In practice, the behaviour distribution is often selected by an *ε*\-greedy policy that follows the greedy policy with probability 1 − *ε* and selects a random action with probability *ε*.

### Training algorithm for deep Q-networks

The full algorithm for training deep Q-networks is presented in Algorithm 1. The agent selects and executes actions according to an *ε*\-greedy policy based on ![](https://media.springernature.com/lw11/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq34_HTML.jpg). Because using histories of arbitrary length as inputs to a neural network can be difficult, our Q-function instead works on a fixed length representation of histories produced by the function *ϕ* described above. The algorithm modifies standard online Q-learning in two ways to make it suitable for training large neural networks without diverging.

First, we use a technique known as experience replay[23](https://www.nature.com/articles/nature14236#ref-CR23 "Lin, L.-J. Reinforcement learning for robots using neural networks. Technical Report, DTIC Document. (1993)") in which we store the agent’s experiences at each time-step, *e**t* = (*s**t*, *a**t*, *r**t*, *s**t +* 1), in a data set *D**t* = {*e*1,…,*e**t*}, pooled over many episodes (where the end of an episode occurs when a terminal state is reached) into a replay memory. During the inner loop of the algorithm, we apply Q-learning updates, or minibatch updates, to samples of experience, (*s*, *a*, *r*, *s*′) ∼ *U*(*D*), drawn at random from the pool of stored samples. This approach has several advantages over standard online Q-learning. First, each step of experience is potentially used in many weight updates, which allows for greater data efficiency. Second, learning directly from consecutive samples is inefficient, owing to the strong correlations between the samples; randomizing the samples breaks these correlations and therefore reduces the variance of the updates. Third, when learning on-policy the current parameters determine the next data sample that the parameters are trained on. For example, if the maximizing action is to move left then the training samples will be dominated by samples from the left-hand side; if the maximizing action then switches to the right then the training distribution will also switch. It is easy to see how unwanted feedback loops may arise and the parameters could get stuck in a poor local minimum, or even diverge catastrophically[20](https://www.nature.com/articles/nature14236#ref-CR20 "Tsitsiklis, J. & Roy, B. V. An analysis of temporal-difference learning with function approximation. IEEE Trans. Automat. Contr. 42, 674–690 (1997)"). By using experience replay the behaviour distribution is averaged over many of its previous states, smoothing out learning and avoiding oscillations or divergence in the parameters. Note that when learning by experience replay, it is necessary to learn off-policy (because our current parameters are different to those used to generate the sample), which motivates the choice of Q-learning.

In practice, our algorithm only stores the last *N* experience tuples in the replay memory, and samples uniformly at random from *D* when performing updates. This approach is in some respects limited because the memory buffer does not differentiate important transitions and always overwrites with recent transitions owing to the finite memory size *N*. Similarly, the uniform sampling gives equal importance to all transitions in the replay memory. A more sophisticated sampling strategy might emphasize transitions from which we can learn the most, similar to prioritized sweeping[30](https://www.nature.com/articles/nature14236#ref-CR30 "Moore, A. & Atkeson, C. Prioritized sweeping: reinforcement learning with less data and less real time. Mach. Learn. 13, 103–130 (1993)").

The second modification to online Q-learning aimed at further improving the stability of our method with neural networks is to use a separate network for generating the targets *y**j* in the Q-learning update. More precisely, every *C* updates we clone the network ![](https://media.springernature.com/lw11/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq35_HTML.jpg) to obtain a target network ![](https://media.springernature.com/lw11/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq36_HTML.jpg) and use ![](https://media.springernature.com/lw11/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq37_HTML.jpg) for generating the Q-learning targets *y**j* for the following *C* updates to ![](https://media.springernature.com/lw11/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq38_HTML.jpg). This modification makes the algorithm more stable compared to standard online Q-learning, where an update that increases ![](https://media.springernature.com/lw43/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq39_HTML.jpg) often also increases ![](https://media.springernature.com/lw58/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq40_HTML.jpg) for all *a* and hence also increases the target *y**j*, possibly leading to oscillations or divergence of the policy. Generating the targets using an older set of parameters adds a delay between the time an update to ![](https://media.springernature.com/lw11/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq41_HTML.jpg) is made and the time the update affects the targets *y**j*, making divergence or oscillations much more unlikely.

We also found it helpful to clip the error term from the update ![](https://media.springernature.com/lw189/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq42_HTML.jpg) to be between −1 and 1. Because the absolute value loss function |*x*| has a derivative of −1 for all negative values of *x* and a derivative of 1 for all positive values of *x*, clipping the squared error to be between −1 and 1 corresponds to using an absolute value loss function for errors outside of the (−1,1) interval. This form of error clipping further improved the stability of the algorithm.

### Algorithm 1: deep Q-learning with experience replay

Initialize replay memory *D* to capacity *N*

Initialize action-value function ![](https://media.springernature.com/lw11/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq43_HTML.jpg) with random weights *θ*

Initialize target action-value function ![](https://media.springernature.com/lw11/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq44_HTML.jpg) with weights *θ*−  *= θ*

**For** episode = 1, *M* **do**

Initialize sequence ![](https://media.springernature.com/lw55/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq45_HTML.jpg) and preprocessed sequence ![](https://media.springernature.com/lw61/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq46_HTML.jpg)

**For** *t* = 1,T **do**

With probability *ε* select a random action *a**t*

otherwise select ![](https://media.springernature.com/lw136/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq47_HTML.jpg)

Execute action *a**t* in emulator and observe reward *r**t* and image *x**t* + 1

Set ![](https://media.springernature.com/lw98/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq48_HTML.jpg) and preprocess ![](https://media.springernature.com/lw90/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq49_HTML.jpg)

Store transition ![](https://media.springernature.com/lw88/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq50_HTML.jpg) in *D*

Sample random minibatch of transitions ![](https://media.springernature.com/lw87/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq51_HTML.jpg) from *D*

Set ![](https://media.springernature.com/lw385/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq52_HTML.jpg)

Perform a gradient descent step on ![](https://media.springernature.com/lw119/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq53_HTML.jpg) with respect to the network parameters *θ*

Every *C* steps reset ![](https://media.springernature.com/lw38/springer-static/image/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_IEq54_HTML.jpg)

**End For**

**End For**

## References

1.  Sutton, R. & Barto, A. *Reinforcement Learning: An Introduction* (MIT Press, 1998)
    
    [MATH](http://www.emis.de/MATH-item?1407.68009)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Reinforcement%20Learning%3A%20An%20Introduction&publication_year=1998&author=Sutton%2CR&author=Barto%2CA) 
    
2.  Thorndike, E. L. *Animal Intelligence: Experimental studies* (Macmillan, 1911)
    
    [Book](https://doi.org/10.5962%2Fbhl.title.55072)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Animal%20Intelligence%3A%20Experimental%20studies&publication_year=1911&author=Thorndike%2CEL) 
    
3.  Schultz, W., Dayan, P. & Montague, P. R. A neural substrate of prediction and reward. *Science* **275**, 1593–1599 (1997)
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DyaK2sXhvFSntro%3D)  [Article](https://doi.org/10.1126%2Fscience.275.5306.1593)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=A%20neural%20substrate%20of%20prediction%20and%20reward&journal=Science&volume=275&pages=1593-1599&publication_year=1997&author=Schultz%2CW&author=Dayan%2CP&author=Montague%2CPR) 
    
4.  Serre, T., Wolf, L. & Poggio, T. Object recognition with features inspired by visual cortex. *Proc. IEEE. Comput. Soc. Conf. Comput. Vis. Pattern. Recognit.* 994–1000 (2005)
    
    [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Object%20recognition%20with%20features%20inspired%20by%20visual%20cortex&pages=994-1000&publication_year=2005&author=Serre%2CT&author=Wolf%2CL&author=Poggio%2CT) 
    
5.  Fukushima, K. Neocognitron: A self-organizing neural network model for a mechanism of pattern recognition unaffected by shift in position. *Biol. Cybern.* **36**, 193–202 (1980)
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:STN:280:DyaL3c7nsFKntw%3D%3D)  [Article](https://doi.org/10.1007%2FBF00344251)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Neocognitron%3A%20A%20self-organizing%20neural%20network%20model%20for%20a%20mechanism%20of%20pattern%20recognition%20unaffected%20by%20shift%20in%20position&journal=Biol.%20Cybern.&volume=36&pages=193-202&publication_year=1980&author=Fukushima%2CK) 
    
6.  Tesauro, G. Temporal difference learning and TD-Gammon. *Commun. ACM* **38**, 58–68 (1995)
    
    [Article](https://doi.org/10.1145%2F203330.203343)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Temporal%20difference%20learning%20and%20TD-Gammon&journal=Commun.%20ACM&volume=38&pages=58-68&publication_year=1995&author=Tesauro%2CG) 
    
7.  Riedmiller, M., Gabel, T., Hafner, R. & Lange, S. Reinforcement learning for robot soccer. *Auton. Robots* **27**, 55–73 (2009)
    
    [Article](https://doi.org/10.1007%2Fs10514-009-9120-4)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Reinforcement%20learning%20for%20robot%20soccer&journal=Auton.%20Robots&volume=27&pages=55-73&publication_year=2009&author=Riedmiller%2CM&author=Gabel%2CT&author=Hafner%2CR&author=Lange%2CS) 
    
8.  Diuk, C., Cohen, A. & Littman, M. L. An object-oriented representation for efficient reinforcement learning. *Proc. Int. Conf. Mach. Learn.* 240–247 (2008)
    
    [Google Scholar](http://scholar.google.com/scholar_lookup?&title=An%20object-oriented%20representation%20for%20efficient%20reinforcement%20learning&pages=240-247&publication_year=2008&author=Diuk%2CC&author=Cohen%2CA&author=Littman%2CML) 
    
9.  Bengio, Y. Learning deep architectures for AI. *Foundations and Trends in Machine Learning* **2**, 1–127 (2009)
    
    [Article](https://doi.org/10.1561%2F2200000006)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Learning%20deep%20architectures%20for%20AI&journal=Foundations%20and%20Trends%20in%20Machine%20Learning&volume=2&pages=1-127&publication_year=2009&author=Bengio%2CY) 
    
10.  Krizhevsky, A., Sutskever, I. & Hinton, G. ImageNet classification with deep convolutional neural networks. *Adv. Neural Inf. Process. Syst.* **25**, 1106–1114 (2012)
    
    [Google Scholar](http://scholar.google.com/scholar_lookup?&title=ImageNet%20classification%20with%20deep%20convolutional%20neural%20networks&journal=Adv.%20Neural%20Inf.%20Process.%20Syst.&volume=25&pages=1106-1114&publication_year=2012&author=Krizhevsky%2CA&author=Sutskever%2CI&author=Hinton%2CG) 
    
11.  Hinton, G. E. & Salakhutdinov, R. R. Reducing the dimensionality of data with neural networks. *Science* **313**, 504–507 (2006)
    
    [ADS](http://adsabs.harvard.edu/cgi-bin/nph-data_query?link_type=ABSTRACT&bibcode=2006Sci...313..504H)  [MathSciNet](http://www.ams.org/mathscinet-getitem?mr=2242509)  [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BD28Xnt1KntrY%3D)  [Article](https://doi.org/10.1126%2Fscience.1127647)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Reducing%20the%20dimensionality%20of%20data%20with%20neural%20networks&journal=Science&volume=313&pages=504-507&publication_year=2006&author=Hinton%2CGE&author=Salakhutdinov%2CRR) 
    
12.  Bellemare, M. G., Naddaf, Y., Veness, J. & Bowling, M. The arcade learning environment: An evaluation platform for general agents. *J. Artif. Intell. Res.* **47**, 253–279 (2013)
    
    [Article](https://doi.org/10.1613%2Fjair.3912)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=The%20arcade%20learning%20environment%3A%20An%20evaluation%20platform%20for%20general%20agents&journal=J.%20Artif.%20Intell.%20Res.&volume=47&pages=253-279&publication_year=2013&author=Bellemare%2CMG&author=Naddaf%2CY&author=Veness%2CJ&author=Bowling%2CM) 
    
13.  Legg, S. & Hutter, M. Universal Intelligence: a definition of machine intelligence. *Minds Mach.* **17**, 391–444 (2007)
    
    [Article](https://doi.org/10.1007%2Fs11023-007-9079-x)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Universal%20Intelligence%3A%20a%20definition%20of%20machine%20intelligence&journal=Minds%20Mach.&volume=17&pages=391-444&publication_year=2007&author=Legg%2CS&author=Hutter%2CM) 
    
14.  Genesereth, M., Love, N. & Pell, B. General game playing: overview of the AAAI competition. *AI Mag.* **26**, 62–72 (2005)
    
    [Google Scholar](http://scholar.google.com/scholar_lookup?&title=General%20game%20playing%3A%20overview%20of%20the%20AAAI%20competition&journal=AI%20Mag.&volume=26&pages=62-72&publication_year=2005&author=Genesereth%2CM&author=Love%2CN&author=Pell%2CB) 
    
15.  Bellemare, M. G., Veness, J. & Bowling, M. Investigating contingency awareness using Atari 2600 games. *Proc. Conf. AAAI. Artif. Intell.* 864–871 (2012)
    
    [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Investigating%20contingency%20awareness%20using%20Atari%202600%20games&pages=864-871&publication_year=2012&author=Bellemare%2CMG&author=Veness%2CJ&author=Bowling%2CM) 
    
16.  McClelland, J. L., Rumelhart, D. E. & Group, T. P. R. *Parallel Distributed Processing: Explorations in the Microstructure of Cognition* (MIT Press, 1986)
    
    [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Parallel%20Distributed%20Processing%3A%20Explorations%20in%20the%20Microstructure%20of%20Cognition&publication_year=1986&author=McClelland%2CJL&author=Rumelhart%2CDE&author=Group%2CTPR) 
    
17.  LeCun, Y., Bottou, L., Bengio, Y. & Haffner, P. Gradient-based learning applied to document recognition. *Proc. IEEE* **86**, 2278–2324 (1998)
    
    [Article](https://doi.org/10.1109%2F5.726791)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Gradient-based%20learning%20applied%20to%20document%20recognition&journal=Proc.%20IEEE&volume=86&pages=2278-2324&publication_year=1998&author=LeCun%2CY&author=Bottou%2CL&author=Bengio%2CY&author=Haffner%2CP) 
    
18.  Hubel, D. H. & Wiesel, T. N. Shape and arrangement of columns in cat’s striate cortex. *J. Physiol.* **165**, 559–568 (1963)
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:STN:280:DyaF387kslWitA%3D%3D)  [Article](https://doi.org/10.1113%2Fjphysiol.1963.sp007079)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Shape%20and%20arrangement%20of%20columns%20in%20cat%E2%80%99s%20striate%20cortex&journal=J.%20Physiol.&volume=165&pages=559-568&publication_year=1963&author=Hubel%2CDH&author=Wiesel%2CTN) 
    
19.  Watkins, C. J. & Dayan, P. Q-learning. *Mach. Learn.* **8**, 279–292 (1992)
    
    [MATH](http://www.emis.de/MATH-item?0773.68062)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Q-learning&journal=Mach.%20Learn.&volume=8&pages=279-292&publication_year=1992&author=Watkins%2CCJ&author=Dayan%2CP) 
    
20.  Tsitsiklis, J. & Roy, B. V. An analysis of temporal-difference learning with function approximation. *IEEE Trans. Automat. Contr.* **42**, 674–690 (1997)
    
    [MathSciNet](http://www.ams.org/mathscinet-getitem?mr=1454208)  [Article](https://doi.org/10.1109%2F9.580874)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=An%20analysis%20of%20temporal-difference%20learning%20with%20function%20approximation&journal=IEEE%20Trans.%20Automat.%20Contr.&volume=42&pages=674-690&publication_year=1997&author=Tsitsiklis%2CJ&author=Roy%2CBV) 
    
21.  McClelland, J. L., McNaughton, B. L. & O’Reilly, R. C. Why there are complementary learning systems in the hippocampus and neocortex: insights from the successes and failures of connectionist models of learning and memory. *Psychol. Rev.* **102**, 419–457 (1995)
    
    [Article](https://doi.org/10.1037%2F0033-295X.102.3.419)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Why%20there%20are%20complementary%20learning%20systems%20in%20the%20hippocampus%20and%20neocortex%3A%20insights%20from%20the%20successes%20and%20failures%20of%20connectionist%20models%20of%20learning%20and%20memory&journal=Psychol.%20Rev.&volume=102&pages=419-457&publication_year=1995&author=McClelland%2CJL&author=McNaughton%2CBL&author=O%E2%80%99Reilly%2CRC) 
    
22.  O’Neill, J., Pleydell-Bouverie, B., Dupret, D. & Csicsvari, J. Play it again: reactivation of waking experience and memory. *Trends Neurosci.* **33**, 220–229 (2010)
    
    [Article](https://doi.org/10.1016%2Fj.tins.2010.01.006)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Play%20it%20again%3A%20reactivation%20of%20waking%20experience%20and%20memory&journal=Trends%20Neurosci.&volume=33&pages=220-229&publication_year=2010&author=O%E2%80%99Neill%2CJ&author=Pleydell-Bouverie%2CB&author=Dupret%2CD&author=Csicsvari%2CJ) 
    
23.  Lin, L.-J. Reinforcement learning for robots using neural networks. Technical Report, DTIC Document. (1993)
    
24.  Riedmiller, M. Neural fitted Q iteration - first experiences with a data efficient neural reinforcement learning method. *Mach. Learn.: ECML* **3720**, 317–328 (Springer, 2005)
    
    [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Neural%20fitted%20Q%20iteration%20-%20first%20experiences%20with%20a%20data%20efficient%20neural%20reinforcement%20learning%20method&journal=Mach.%20Learn.%3A%20ECML&volume=3720&pages=317-328&publication_year=2005&author=Riedmiller%2CM) 
    
25.  Van der Maaten, L. J. P. & Hinton, G. E. Visualizing high-dimensional data using t-SNE. *J. Mach. Learn. Res.* **9**, 2579–2605 (2008)
    
    [MATH](http://www.emis.de/MATH-item?1225.68219)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Visualizing%20high-dimensional%20data%20using%20t-SNE&journal=J.%20Mach.%20Learn.%20Res.&volume=9&pages=2579-2605&publication_year=2008&author=Van%20der%20Maaten%2CLJP&author=Hinton%2CGE) 
    
26.  Lange, S. & Riedmiller, M. Deep auto-encoder neural networks in reinforcement learning. *Proc. Int. Jt. Conf. Neural. Netw.* 1–8 (2010)
    
    [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Deep%20auto-encoder%20neural%20networks%20in%20reinforcement%20learning&pages=1-8&publication_year=2010&author=Lange%2CS&author=Riedmiller%2CM) 
    
27.  Law, C.-T. & Gold, J. I. Reinforcement learning can account for associative and perceptual learning on a visual decision task. *Nature Neurosci.* **12**, 655 (2009)
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BD1MXks12ktbw%3D)  [Article](https://doi.org/10.1038%2Fnn.2304)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Reinforcement%20learning%20can%20account%20for%20associative%20and%20perceptual%20learning%20on%20a%20visual%20decision%20task&journal=Nature%20Neurosci.&volume=12&publication_year=2009&author=Law%2CC-T&author=Gold%2CJI) 
    
28.  Sigala, N. & Logothetis, N. K. Visual categorization shapes feature selectivity in the primate temporal cortex. *Nature* **415**, 318–320 (2002)
    
    [ADS](http://adsabs.harvard.edu/cgi-bin/nph-data_query?link_type=ABSTRACT&bibcode=2002Natur.415..318S)  [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BD38Xptlajsg%3D%3D)  [Article](https://doi.org/10.1038%2F415318a)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Visual%20categorization%20shapes%20feature%20selectivity%20in%20the%20primate%20temporal%20cortex&journal=Nature&volume=415&pages=318-320&publication_year=2002&author=Sigala%2CN&author=Logothetis%2CNK) 
    
29.  Bendor, D. & Wilson, M. A. Biasing the content of hippocampal replay during sleep. *Nature Neurosci.* **15**, 1439–1444 (2012)
    
    [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BC38Xht12js7bO)  [Article](https://doi.org/10.1038%2Fnn.3203)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Biasing%20the%20content%20of%20hippocampal%20replay%20during%20sleep&journal=Nature%20Neurosci.&volume=15&pages=1439-1444&publication_year=2012&author=Bendor%2CD&author=Wilson%2CMA) 
    
30.  Moore, A. & Atkeson, C. Prioritized sweeping: reinforcement learning with less data and less real time. *Mach. Learn.* **13**, 103–130 (1993)
    
    [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Prioritized%20sweeping%3A%20reinforcement%20learning%20with%20less%20data%20and%20less%20real%20time&journal=Mach.%20Learn.&volume=13&pages=103-130&publication_year=1993&author=Moore%2CA&author=Atkeson%2CC) 
    
31.  Jarrett, K., Kavukcuoglu, K., Ranzato, M. A. & LeCun, Y. What is the best multi-stage architecture for object recognition? *Proc. IEEE. Int. Conf. Comput. Vis.* 2146–2153 (2009)
    
    [Google Scholar](http://scholar.google.com/scholar_lookup?&title=What%20is%20the%20best%20multi-stage%20architecture%20for%20object%20recognition&pages=2146-2153&publication_year=2009&author=Jarrett%2CK&author=Kavukcuoglu%2CK&author=Ranzato%2CMA&author=LeCun%2CY) 
    
32.  Nair, V. & Hinton, G. E. Rectified linear units improve restricted Boltzmann machines. *Proc. Int. Conf. Mach. Learn.* 807–814 (2010)
    
33.  Kaelbling, L. P., Littman, M. L. & Cassandra, A. R. Planning and acting in partially observable stochastic domains. *Artificial Intelligence* **101**, 99–134 (1994)
    
    [MathSciNet](http://www.ams.org/mathscinet-getitem?mr=1641530)  [Article](https://doi.org/10.1016%2FS0004-3702%2898%2900023-X)  [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Planning%20and%20acting%20in%20partially%20observable%20stochastic%20domains&journal=Artificial%20Intelligence&volume=101&pages=99-134&publication_year=1994&author=Kaelbling%2CLP&author=Littman%2CML&author=Cassandra%2CAR) 
    

[Download references](https://citation-needed.springer.com/v2/references/10.1038/nature14236?format=refman&flavour=references)

## Acknowledgements

We thank G. Hinton, P. Dayan and M. Bowling for discussions, A. Cain and J. Keene for work on the visuals, K. Keller and P. Rogers for help with the visuals, G. Wayne for comments on an earlier version of the manuscript, and the rest of the DeepMind team for their support, ideas and encouragement.

## Author information

Author notes

1.  Volodymyr Mnih, Koray Kavukcuoglu and David Silver: These authors contributed equally to this work.
    

### Affiliations

1.  Google DeepMind, 5 New Street Square, London EC4A 3TW, UK
    
    Volodymyr Mnih, Koray Kavukcuoglu, David Silver, Andrei A. Rusu, Joel Veness, Marc G. Bellemare, Alex Graves, Martin Riedmiller, Andreas K. Fidjeland, Georg Ostrovski, Stig Petersen, Charles Beattie, Amir Sadik, Ioannis Antonoglou, Helen King, Dharshan Kumaran, Daan Wierstra, Shane Legg & Demis Hassabis
    

Authors

1.  Volodymyr Mnih
    
    You can also search for this author in [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=search&term=Volodymyr%20Mnih) [Google Scholar](http://scholar.google.co.uk/scholar?as_q=&num=10&btnG=Search+Scholar&as_epq=&as_oq=&as_eq=&as_occt=any&as_sauthors=%22Volodymyr%20Mnih%22&as_publication=&as_ylo=&as_yhi=&as_allsubj=all&hl=en)
    
2.  Koray Kavukcuoglu
    
    You can also search for this author in [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=search&term=Koray%20Kavukcuoglu) [Google Scholar](http://scholar.google.co.uk/scholar?as_q=&num=10&btnG=Search+Scholar&as_epq=&as_oq=&as_eq=&as_occt=any&as_sauthors=%22Koray%20Kavukcuoglu%22&as_publication=&as_ylo=&as_yhi=&as_allsubj=all&hl=en)
    
3.  David Silver
    
    You can also search for this author in [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=search&term=David%20Silver) [Google Scholar](http://scholar.google.co.uk/scholar?as_q=&num=10&btnG=Search+Scholar&as_epq=&as_oq=&as_eq=&as_occt=any&as_sauthors=%22David%20Silver%22&as_publication=&as_ylo=&as_yhi=&as_allsubj=all&hl=en)
    
4.  Andrei A. Rusu
    
    You can also search for this author in [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=search&term=Andrei%20A.%20Rusu) [Google Scholar](http://scholar.google.co.uk/scholar?as_q=&num=10&btnG=Search+Scholar&as_epq=&as_oq=&as_eq=&as_occt=any&as_sauthors=%22Andrei%20A.%20Rusu%22&as_publication=&as_ylo=&as_yhi=&as_allsubj=all&hl=en)
    
5.  Joel Veness
    
    You can also search for this author in [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=search&term=Joel%20Veness) [Google Scholar](http://scholar.google.co.uk/scholar?as_q=&num=10&btnG=Search+Scholar&as_epq=&as_oq=&as_eq=&as_occt=any&as_sauthors=%22Joel%20Veness%22&as_publication=&as_ylo=&as_yhi=&as_allsubj=all&hl=en)
    
6.  Marc G. Bellemare
    
    You can also search for this author in [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=search&term=Marc%20G.%20Bellemare) [Google Scholar](http://scholar.google.co.uk/scholar?as_q=&num=10&btnG=Search+Scholar&as_epq=&as_oq=&as_eq=&as_occt=any&as_sauthors=%22Marc%20G.%20Bellemare%22&as_publication=&as_ylo=&as_yhi=&as_allsubj=all&hl=en)
    
7.  Alex Graves
    
    You can also search for this author in [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=search&term=Alex%20Graves) [Google Scholar](http://scholar.google.co.uk/scholar?as_q=&num=10&btnG=Search+Scholar&as_epq=&as_oq=&as_eq=&as_occt=any&as_sauthors=%22Alex%20Graves%22&as_publication=&as_ylo=&as_yhi=&as_allsubj=all&hl=en)
    
8.  Martin Riedmiller
    
    You can also search for this author in [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=search&term=Martin%20Riedmiller) [Google Scholar](http://scholar.google.co.uk/scholar?as_q=&num=10&btnG=Search+Scholar&as_epq=&as_oq=&as_eq=&as_occt=any&as_sauthors=%22Martin%20Riedmiller%22&as_publication=&as_ylo=&as_yhi=&as_allsubj=all&hl=en)
    
9.  Andreas K. Fidjeland
    
    You can also search for this author in [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=search&term=Andreas%20K.%20Fidjeland) [Google Scholar](http://scholar.google.co.uk/scholar?as_q=&num=10&btnG=Search+Scholar&as_epq=&as_oq=&as_eq=&as_occt=any&as_sauthors=%22Andreas%20K.%20Fidjeland%22&as_publication=&as_ylo=&as_yhi=&as_allsubj=all&hl=en)
    
10.  Georg Ostrovski
    
    You can also search for this author in [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=search&term=Georg%20Ostrovski) [Google Scholar](http://scholar.google.co.uk/scholar?as_q=&num=10&btnG=Search+Scholar&as_epq=&as_oq=&as_eq=&as_occt=any&as_sauthors=%22Georg%20Ostrovski%22&as_publication=&as_ylo=&as_yhi=&as_allsubj=all&hl=en)
    
11.  Stig Petersen
    
    You can also search for this author in [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=search&term=Stig%20Petersen) [Google Scholar](http://scholar.google.co.uk/scholar?as_q=&num=10&btnG=Search+Scholar&as_epq=&as_oq=&as_eq=&as_occt=any&as_sauthors=%22Stig%20Petersen%22&as_publication=&as_ylo=&as_yhi=&as_allsubj=all&hl=en)
    
12.  Charles Beattie
    
    You can also search for this author in [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=search&term=Charles%20Beattie) [Google Scholar](http://scholar.google.co.uk/scholar?as_q=&num=10&btnG=Search+Scholar&as_epq=&as_oq=&as_eq=&as_occt=any&as_sauthors=%22Charles%20Beattie%22&as_publication=&as_ylo=&as_yhi=&as_allsubj=all&hl=en)
    
13.  Amir Sadik
    
    You can also search for this author in [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=search&term=Amir%20Sadik) [Google Scholar](http://scholar.google.co.uk/scholar?as_q=&num=10&btnG=Search+Scholar&as_epq=&as_oq=&as_eq=&as_occt=any&as_sauthors=%22Amir%20Sadik%22&as_publication=&as_ylo=&as_yhi=&as_allsubj=all&hl=en)
    
14.  Ioannis Antonoglou
    
    You can also search for this author in [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=search&term=Ioannis%20Antonoglou) [Google Scholar](http://scholar.google.co.uk/scholar?as_q=&num=10&btnG=Search+Scholar&as_epq=&as_oq=&as_eq=&as_occt=any&as_sauthors=%22Ioannis%20Antonoglou%22&as_publication=&as_ylo=&as_yhi=&as_allsubj=all&hl=en)
    
15.  Helen King
    
    You can also search for this author in [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=search&term=Helen%20King) [Google Scholar](http://scholar.google.co.uk/scholar?as_q=&num=10&btnG=Search+Scholar&as_epq=&as_oq=&as_eq=&as_occt=any&as_sauthors=%22Helen%20King%22&as_publication=&as_ylo=&as_yhi=&as_allsubj=all&hl=en)
    
16.  Dharshan Kumaran
    
    You can also search for this author in [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=search&term=Dharshan%20Kumaran) [Google Scholar](http://scholar.google.co.uk/scholar?as_q=&num=10&btnG=Search+Scholar&as_epq=&as_oq=&as_eq=&as_occt=any&as_sauthors=%22Dharshan%20Kumaran%22&as_publication=&as_ylo=&as_yhi=&as_allsubj=all&hl=en)
    
17.  Daan Wierstra
    
    You can also search for this author in [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=search&term=Daan%20Wierstra) [Google Scholar](http://scholar.google.co.uk/scholar?as_q=&num=10&btnG=Search+Scholar&as_epq=&as_oq=&as_eq=&as_occt=any&as_sauthors=%22Daan%20Wierstra%22&as_publication=&as_ylo=&as_yhi=&as_allsubj=all&hl=en)
    
18.  Shane Legg
    
    You can also search for this author in [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=search&term=Shane%20Legg) [Google Scholar](http://scholar.google.co.uk/scholar?as_q=&num=10&btnG=Search+Scholar&as_epq=&as_oq=&as_eq=&as_occt=any&as_sauthors=%22Shane%20Legg%22&as_publication=&as_ylo=&as_yhi=&as_allsubj=all&hl=en)
    
19.  Demis Hassabis
    
    You can also search for this author in [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=search&term=Demis%20Hassabis) [Google Scholar](http://scholar.google.co.uk/scholar?as_q=&num=10&btnG=Search+Scholar&as_epq=&as_oq=&as_eq=&as_occt=any&as_sauthors=%22Demis%20Hassabis%22&as_publication=&as_ylo=&as_yhi=&as_allsubj=all&hl=en)
    

### Contributions

V.M., K.K., D.S., J.V., M.G.B., M.R., A.G., D.W., S.L. and D.H. conceptualized the problem and the technical framework. V.M., K.K., A.A.R. and D.S. developed and tested the algorithms. J.V., S.P., C.B., A.A.R., M.G.B., I.A., A.K.F., G.O. and A.S. created the testing platform. K.K., H.K., S.L. and D.H. managed the project. K.K., D.K., D.H., V.M., D.S., A.G., A.A.R., J.V. and M.G.B. wrote the paper.

### Corresponding authors

Correspondence to [Koray Kavukcuoglu](mailto:korayk@google.com) or [Demis Hassabis](mailto:demishassabis@google.com).

## Ethics declarations

### Competing interests

The authors declare no competing financial interests.

## Extended data figures and tables

### [Extended Data Figure 1 Two-dimensional t-SNE embedding of the representations in the last hidden layer assigned by DQN to game states experienced during a combination of human and agent play in Space Invaders.](https://www.nature.com/articles/nature14236/figures/5)

The plot was generated by running the t-SNE algorithm[25](https://www.nature.com/articles/nature14236#ref-CR25 "Van der Maaten, L. J. P. & Hinton, G. E. Visualizing high-dimensional data using t-SNE. J. Mach. Learn. Res. 9, 2579–2605 (2008)") on the last hidden layer representation assigned by DQN to game states experienced during a combination of human (30 min) and agent (2 h) play. The fact that there is similar structure in the two-dimensional embeddings corresponding to the DQN representation of states experienced during human play (orange points) and DQN play (blue points) suggests that the representations learned by DQN do indeed generalize to data generated from policies other than its own. The presence in the t-SNE embedding of overlapping clusters of points corresponding to the network representation of states experienced during human and agent play shows that the DQN agent also follows sequences of states similar to those found in human play. Screenshots corresponding to selected states are shown (human: orange border; DQN: blue border).

### [Extended Data Figure 2 Visualization of learned value functions on two games, Breakout and Pong.](https://www.nature.com/articles/nature14236/figures/6)

**a**, A visualization of the learned value function on the game Breakout. At time points 1 and 2, the state value is predicted to be ∼17 and the agent is clearing the bricks at the lowest level. Each of the peaks in the value function curve corresponds to a reward obtained by clearing a brick. At time point 3, the agent is about to break through to the top level of bricks and the value increases to ∼21 in anticipation of breaking out and clearing a large set of bricks. At point 4, the value is above 23 and the agent has broken through. After this point, the ball will bounce at the upper part of the bricks clearing many of them by itself. **b**, A visualization of the learned action-value function on the game Pong. At time point 1, the ball is moving towards the paddle controlled by the agent on the right side of the screen and the values of all actions are around 0.7, reflecting the expected value of this state based on previous experience. At time point 2, the agent starts moving the paddle towards the ball and the value of the ‘up’ action stays high while the value of the ‘down’ action falls to −0.9. This reflects the fact that pressing ‘down’ would lead to the agent losing the ball and incurring a reward of −1. At time point 3, the agent hits the ball by pressing ‘up’ and the expected reward keeps increasing until time point 4, when the ball reaches the left edge of the screen and the value of all actions reflects that the agent is about to receive a reward of 1. Note, the dashed line shows the past trajectory of the ball purely for illustrative purposes (that is, not shown during the game). With permission from Atari Interactive, Inc.

**Extended Data Table 1 List of hyperparameters and their values**

[Full size table](https://www.nature.com/articles/nature14236/tables/1)

**Extended Data Table 2 Comparison of games scores obtained by DQN agents with methods from the literature[12](https://www.nature.com/articles/nature14236#ref-CR12 "Bellemare, M. G., Naddaf, Y., Veness, J. & Bowling, M. The arcade learning environment: An evaluation platform for general agents. J. Artif. Intell. Res. 47, 253–279 (2013)"),[15](https://www.nature.com/articles/nature14236#ref-CR15 "Bellemare, M. G., Veness, J. & Bowling, M. Investigating contingency awareness using Atari 2600 games. Proc. Conf. AAAI. Artif. Intell. 864–871 (2012)") and a professional human games tester**

[Full size table](https://www.nature.com/articles/nature14236/tables/2)

**Extended Data Table 3 The effects of replay and separating the target Q-network**

[Full size table](https://www.nature.com/articles/nature14236/tables/3)

**Extended Data Table 4 Comparison of DQN performance with linear function approximator**

[Full size table](https://www.nature.com/articles/nature14236/tables/4)

## Supplementary information

### [Supplementary Information](https://static-content.springer.com/esm/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_MOESM122_ESM.pdf)

This file contains a Supplementary Discussion. (PDF 110 kb)

### [Performance of DQN in the Game Space Invaders](https://static-content.springer.com/esm/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_MOESM123_ESM.mov)

This video shows the performance of the DQN agent while playing the game of Space Invaders. The DQN agent successfully clears the enemy ships on the screen while the enemy ships move down and sideways with gradually increasing speed. (MOV 5106 kb)

### [Demonstration of Learning Progress in the Game Breakout](https://static-content.springer.com/esm/art%3A10.1038%2Fnature14236/MediaObjects/41586_2015_BFnature14236_MOESM124_ESM.mov)

This video shows the improvement in the performance of DQN over training (i.e. after 100, 200, 400 and 600 episodes). After 600 episodes DQN finds and exploits the optimal strategy in this game, which is to make a tunnel around the side, and then allow the ball to hit blocks by bouncing behind the wall. Note: the score is displayed at the top left of the screen (maximum for clearing one screen is 448 points), number of lives remaining is shown in the middle (starting with 5 lives), and the “1” on the top right indicates this is a 1-player game. (MOV 1500 kb)

## PowerPoint slides

## Rights and permissions

## About this article

[![Verify currency and authenticity via CrossMark](data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjgxIiB3aWR0aD0iNTciIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PGcgZmlsbD0ibm9uZSIgZmlsbC1ydWxlPSJldmVub2RkIj48cGF0aCBkPSJtMTcuMzUgMzUuNDUgMjEuMy0xNC4ydi0xNy4wM2gtMjEuMyIgZmlsbD0iIzk4OTg5OCIvPjxwYXRoIGQ9Im0zOC42NSAzNS40NS0yMS4zLTE0LjJ2LTE3LjAzaDIxLjMiIGZpbGw9IiM3NDc0NzQiLz48cGF0aCBkPSJtMjggLjVjLTEyLjk4IDAtMjMuNSAxMC41Mi0yMy41IDIzLjVzMTAuNTIgMjMuNSAyMy41IDIzLjUgMjMuNS0xMC41MiAyMy41LTIzLjVjMC02LjIzLTIuNDgtMTIuMjEtNi44OC0xNi42Mi00LjQxLTQuNC0xMC4zOS02Ljg4LTE2LjYyLTYuODh6bTAgNDEuMjVjLTkuOCAwLTE3Ljc1LTcuOTUtMTcuNzUtMTcuNzVzNy45NS0xNy43NSAxNy43NS0xNy43NSAxNy43NSA3Ljk1IDE3Ljc1IDE3Ljc1YzAgNC43MS0xLjg3IDkuMjItNS4yIDEyLjU1cy03Ljg0IDUuMi0xMi41NSA1LjJ6IiBmaWxsPSIjNTM1MzUzIi8+PHBhdGggZD0ibTQxIDM2Yy01LjgxIDYuMjMtMTUuMjMgNy40NS0yMi40MyAyLjktNy4yMS00LjU1LTEwLjE2LTEzLjU3LTcuMDMtMjEuNWwtNC45Mi0zLjExYy00Ljk1IDEwLjctMS4xOSAyMy40MiA4Ljc4IDI5LjcxIDkuOTcgNi4zIDIzLjA3IDQuMjIgMzAuNi00Ljg2eiIgZmlsbD0iIzljOWM5YyIvPjxwYXRoIGQ9Im0uMiA1OC40NWMwLS43NS4xMS0xLjQyLjMzLTIuMDFzLjUyLTEuMDkuOTEtMS41Yy4zOC0uNDEuODMtLjczIDEuMzQtLjk0LjUxLS4yMiAxLjA2LS4zMiAxLjY1LS4zMi41NiAwIDEuMDYuMTEgMS41MS4zNS40NC4yMy44MS41IDEuMS44MWwtLjkxIDEuMDFjLS4yNC0uMjQtLjQ5LS40Mi0uNzUtLjU2LS4yNy0uMTMtLjU4LS4yLS45My0uMi0uMzkgMC0uNzMuMDgtMS4wNS4yMy0uMzEuMTYtLjU4LjM3LS44MS42Ni0uMjMuMjgtLjQxLjYzLS41MyAxLjA0LS4xMy40MS0uMTkuODgtLjE5IDEuMzkgMCAxLjA0LjIzIDEuODYuNjggMi40Ni40NS41OSAxLjA2Ljg4IDEuODQuODguNDEgMCAuNzctLjA3IDEuMDctLjIzcy41OS0uMzkuODUtLjY4bC45MSAxYy0uMzguNDMtLjguNzYtMS4yOC45OS0uNDcuMjItMSAuMzQtMS41OC4zNC0uNTkgMC0xLjEzLS4xLTEuNjQtLjMxLS41LS4yLS45NC0uNTEtMS4zMS0uOTEtLjM4LS40LS42Ny0uOS0uODgtMS40OC0uMjItLjU5LS4zMy0xLjI2LS4zMy0yLjAyem04LjQtNS4zM2gxLjYxdjIuNTRsLS4wNSAxLjMzYy4yOS0uMjcuNjEtLjUxLjk2LS43MnMuNzYtLjMxIDEuMjQtLjMxYy43MyAwIDEuMjcuMjMgMS42MS43MS4zMy40Ny41IDEuMTQuNSAyLjAydjQuMzFoLTEuNjF2LTQuMWMwLS41Ny0uMDgtLjk3LS4yNS0xLjIxLS4xNy0uMjMtLjQ1LS4zNS0uODMtLjM1LS4zIDAtLjU2LjA4LS43OS4yMi0uMjMuMTUtLjQ5LjM2LS43OC42NHY0LjhoLTEuNjF6bTcuMzcgNi40NWMwLS41Ni4wOS0xLjA2LjI2LTEuNTEuMTgtLjQ1LjQyLS44My43MS0xLjE0LjI5LS4zLjYzLS41NCAxLjAxLS43MS4zOS0uMTcuNzgtLjI1IDEuMTgtLjI1LjQ3IDAgLjg4LjA4IDEuMjMuMjQuMzYuMTYuNjUuMzguODkuNjdzLjQyLjYzLjU0IDEuMDNjLjEyLjQxLjE4Ljg0LjE4IDEuMzIgMCAuMzItLjAyLjU3LS4wNy43NmgtNC4zNmMuMDcuNjIuMjkgMS4xLjY1IDEuNDQuMzYuMzMuODIuNSAxLjM4LjUuMjkgMCAuNTctLjA0LjgzLS4xM3MuNTEtLjIxLjc2LS4zN2wuNTUgMS4wMWMtLjMzLjIxLS42OS4zOS0xLjA5LjUzLS40MS4xNC0uODMuMjEtMS4yNi4yMS0uNDggMC0uOTItLjA4LTEuMzQtLjI1LS40MS0uMTYtLjc2LS40LTEuMDctLjctLjMxLS4zMS0uNTUtLjY5LS43Mi0xLjEzLS4xOC0uNDQtLjI2LS45NS0uMjYtMS41MnptNC42LS42MmMwLS41NS0uMTEtLjk4LS4zNC0xLjI4LS4yMy0uMzEtLjU4LS40Ny0xLjA2LS40Ny0uNDEgMC0uNzcuMTUtMS4wNy40NS0uMzEuMjktLjUuNzMtLjU4IDEuM3ptMi41LjYyYzAtLjU3LjA5LTEuMDguMjgtMS41My4xOC0uNDQuNDMtLjgyLjc1LTEuMTNzLjY5LS41NCAxLjEtLjcxYy40Mi0uMTYuODUtLjI0IDEuMzEtLjI0LjQ1IDAgLjg0LjA4IDEuMTcuMjNzLjYxLjM0Ljg1LjU3bC0uNzcgMS4wMmMtLjE5LS4xNi0uMzgtLjI4LS41Ni0uMzctLjE5LS4wOS0uMzktLjE0LS42MS0uMTQtLjU2IDAtMS4wMS4yMS0xLjM1LjYzLS4zNS40MS0uNTIuOTctLjUyIDEuNjcgMCAuNjkuMTcgMS4yNC41MSAxLjY2LjM0LjQxLjc4LjYyIDEuMzIuNjIuMjggMCAuNTQtLjA2Ljc4LS4xNy4yNC0uMTIuNDUtLjI2LjY0LS40MmwuNjcgMS4wM2MtLjMzLjI5LS42OS41MS0xLjA4LjY1LS4zOS4xNS0uNzguMjMtMS4xOC4yMy0uNDYgMC0uOS0uMDgtMS4zMS0uMjQtLjQtLjE2LS43NS0uMzktMS4wNS0uN3MtLjUzLS42OS0uNy0xLjEzYy0uMTctLjQ1LS4yNS0uOTYtLjI1LTEuNTN6bTYuOTEtNi40NWgxLjU4djYuMTdoLjA1bDIuNTQtMy4xNmgxLjc3bC0yLjM1IDIuOCAyLjU5IDQuMDdoLTEuNzVsLTEuNzctMi45OC0xLjA4IDEuMjN2MS43NWgtMS41OHptMTMuNjkgMS4yN2MtLjI1LS4xMS0uNS0uMTctLjc1LS4xNy0uNTggMC0uODcuMzktLjg3IDEuMTZ2Ljc1aDEuMzR2MS4yN2gtMS4zNHY1LjZoLTEuNjF2LTUuNmgtLjkydi0xLjJsLjkyLS4wN3YtLjcyYzAtLjM1LjA0LS42OC4xMy0uOTguMDgtLjMxLjIxLS41Ny40LS43OXMuNDItLjM5LjcxLS41MWMuMjgtLjEyLjYzLS4xOCAxLjA0LS4xOC4yNCAwIC40OC4wMi42OS4wNy4yMi4wNS40MS4xLjU3LjE3em0uNDggNS4xOGMwLS41Ny4wOS0xLjA4LjI3LTEuNTMuMTctLjQ0LjQxLS44Mi43Mi0xLjEzLjMtLjMxLjY1LS41NCAxLjA0LS43MS4zOS0uMTYuOC0uMjQgMS4yMy0uMjRzLjg0LjA4IDEuMjQuMjRjLjQuMTcuNzQuNCAxLjA0Ljcxcy41NC42OS43MiAxLjEzYy4xOS40NS4yOC45Ni4yOCAxLjUzcy0uMDkgMS4wOC0uMjggMS41M2MtLjE4LjQ0LS40Mi44Mi0uNzIgMS4xM3MtLjY0LjU0LTEuMDQuNy0uODEuMjQtMS4yNC4yNC0uODQtLjA4LTEuMjMtLjI0LS43NC0uMzktMS4wNC0uN2MtLjMxLS4zMS0uNTUtLjY5LS43Mi0xLjEzLS4xOC0uNDUtLjI3LS45Ni0uMjctMS41M3ptMS42NSAwYzAgLjY5LjE0IDEuMjQuNDMgMS42Ni4yOC40MS42OC42MiAxLjE4LjYyLjUxIDAgLjktLjIxIDEuMTktLjYyLjI5LS40Mi40NC0uOTcuNDQtMS42NiAwLS43LS4xNS0xLjI2LS40NC0xLjY3LS4yOS0uNDItLjY4LS42My0xLjE5LS42My0uNSAwLS45LjIxLTEuMTguNjMtLjI5LjQxLS40My45Ny0uNDMgMS42N3ptNi40OC0zLjQ0aDEuMzNsLjEyIDEuMjFoLjA1Yy4yNC0uNDQuNTQtLjc5Ljg4LTEuMDIuMzUtLjI0LjctLjM2IDEuMDctLjM2LjMyIDAgLjU5LjA1Ljc4LjE0bC0uMjggMS40LS4zMy0uMDljLS4xMS0uMDEtLjIzLS4wMi0uMzgtLjAyLS4yNyAwLS41Ni4xLS44Ni4zMXMtLjU1LjU4LS43NyAxLjF2NC4yaC0xLjYxem0tNDcuODcgMTVoMS42MXY0LjFjMCAuNTcuMDguOTcuMjUgMS4yLjE3LjI0LjQ0LjM1LjgxLjM1LjMgMCAuNTctLjA3LjgtLjIyLjIyLS4xNS40Ny0uMzkuNzMtLjczdi00LjdoMS42MXY2Ljg3aC0xLjMybC0uMTItMS4wMWgtLjA0Yy0uMy4zNi0uNjMuNjQtLjk4Ljg2LS4zNS4yMS0uNzYuMzItMS4yNC4zMi0uNzMgMC0xLjI3LS4yNC0xLjYxLS43MS0uMzMtLjQ3LS41LTEuMTQtLjUtMi4wMnptOS40NiA3LjQzdjIuMTZoLTEuNjF2LTkuNTloMS4zM2wuMTIuNzJoLjA1Yy4yOS0uMjQuNjEtLjQ1Ljk3LS42My4zNS0uMTcuNzItLjI2IDEuMS0uMjYuNDMgMCAuODEuMDggMS4xNS4yNC4zMy4xNy42MS40Ljg0LjcxLjI0LjMxLjQxLjY4LjUzIDEuMTEuMTMuNDIuMTkuOTEuMTkgMS40NCAwIC41OS0uMDkgMS4xMS0uMjUgMS41Ny0uMTYuNDctLjM4Ljg1LS42NSAxLjE2LS4yNy4zMi0uNTguNTYtLjk0LjczLS4zNS4xNi0uNzIuMjUtMS4xLjI1LS4zIDAtLjYtLjA3LS45LS4ycy0uNTktLjMxLS44Ny0uNTZ6bTAtMi4zYy4yNi4yMi41LjM3LjczLjQ1LjI0LjA5LjQ2LjEzLjY2LjEzLjQ2IDAgLjg0LS4yIDEuMTUtLjYuMzEtLjM5LjQ2LS45OC40Ni0xLjc3IDAtLjY5LS4xMi0xLjIyLS4zNS0xLjYxLS4yMy0uMzgtLjYxLS41Ny0xLjEzLS41Ny0uNDkgMC0uOTkuMjYtMS41Mi43N3ptNS44Ny0xLjY5YzAtLjU2LjA4LTEuMDYuMjUtMS41MS4xNi0uNDUuMzctLjgzLjY1LTEuMTQuMjctLjMuNTgtLjU0LjkzLS43MXMuNzEtLjI1IDEuMDgtLjI1Yy4zOSAwIC43My4wNyAxIC4yLjI3LjE0LjU0LjMyLjgxLjU1bC0uMDYtMS4xdi0yLjQ5aDEuNjF2OS44OGgtMS4zM2wtLjExLS43NGgtLjA2Yy0uMjUuMjUtLjU0LjQ2LS44OC42NC0uMzMuMTgtLjY5LjI3LTEuMDYuMjctLjg3IDAtMS41Ni0uMzItMi4wNy0uOTVzLS43Ni0xLjUxLS43Ni0yLjY1em0xLjY3LS4wMWMwIC43NC4xMyAxLjMxLjQgMS43LjI2LjM4LjY1LjU4IDEuMTUuNTguNTEgMCAuOTktLjI2IDEuNDQtLjc3di0zLjIxYy0uMjQtLjIxLS40OC0uMzYtLjctLjQ1LS4yMy0uMDgtLjQ2LS4xMi0uNy0uMTItLjQ1IDAtLjgyLjE5LTEuMTMuNTktLjMxLjM5LS40Ni45NS0uNDYgMS42OHptNi4zNSAxLjU5YzAtLjczLjMyLTEuMy45Ny0xLjcxLjY0LS40IDEuNjctLjY4IDMuMDgtLjg0IDAtLjE3LS4wMi0uMzQtLjA3LS41MS0uMDUtLjE2LS4xMi0uMy0uMjItLjQzcy0uMjItLjIyLS4zOC0uM2MtLjE1LS4wNi0uMzQtLjEtLjU4LS4xLS4zNCAwLS42OC4wNy0xIC4ycy0uNjMuMjktLjkzLjQ3bC0uNTktMS4wOGMuMzktLjI0LjgxLS40NSAxLjI4LS42My40Ny0uMTcuOTktLjI2IDEuNTQtLjI2Ljg2IDAgMS41MS4yNSAxLjkzLjc2cy42MyAxLjI1LjYzIDIuMjF2NC4wN2gtMS4zMmwtLjEyLS43NmgtLjA1Yy0uMy4yNy0uNjMuNDgtLjk4LjY2cy0uNzMuMjctMS4xNC4yN2MtLjYxIDAtMS4xLS4xOS0xLjQ4LS41Ni0uMzgtLjM2LS41Ny0uODUtLjU3LTEuNDZ6bTEuNTctLjEyYzAgLjMuMDkuNTMuMjcuNjcuMTkuMTQuNDIuMjEuNzEuMjEuMjggMCAuNTQtLjA3Ljc3LS4ycy40OC0uMzEuNzMtLjU2di0xLjU0Yy0uNDcuMDYtLjg2LjEzLTEuMTguMjMtLjMxLjA5LS41Ny4xOS0uNzYuMzFzLS4zMy4yNS0uNDEuNGMtLjA5LjE1LS4xMy4zMS0uMTMuNDh6bTYuMjktMy42M2gtLjk4di0xLjJsMS4wNi0uMDcuMi0xLjg4aDEuMzR2MS44OGgxLjc1djEuMjdoLTEuNzV2My4yOGMwIC44LjMyIDEuMi45NyAxLjIuMTIgMCAuMjQtLjAxLjM3LS4wNC4xMi0uMDMuMjQtLjA3LjM0LS4xMWwuMjggMS4xOWMtLjE5LjA2LS40LjEyLS42NC4xNy0uMjMuMDUtLjQ5LjA4LS43Ni4wOC0uNCAwLS43NC0uMDYtMS4wMi0uMTgtLjI3LS4xMy0uNDktLjMtLjY3LS41Mi0uMTctLjIxLS4zLS40OC0uMzctLjc4LS4wOC0uMy0uMTItLjY0LS4xMi0xLjAxem00LjM2IDIuMTdjMC0uNTYuMDktMS4wNi4yNy0xLjUxcy40MS0uODMuNzEtMS4xNGMuMjktLjMuNjMtLjU0IDEuMDEtLjcxLjM5LS4xNy43OC0uMjUgMS4xOC0uMjUuNDcgMCAuODguMDggMS4yMy4yNC4zNi4xNi42NS4zOC44OS42N3MuNDIuNjMuNTQgMS4wM2MuMTIuNDEuMTguODQuMTggMS4zMiAwIC4zMi0uMDIuNTctLjA3Ljc2aC00LjM3Yy4wOC42Mi4yOSAxLjEuNjUgMS40NC4zNi4zMy44Mi41IDEuMzguNS4zIDAgLjU4LS4wNC44NC0uMTMuMjUtLjA5LjUxLS4yMS43Ni0uMzdsLjU0IDEuMDFjLS4zMi4yMS0uNjkuMzktMS4wOS41M3MtLjgyLjIxLTEuMjYuMjFjLS40NyAwLS45Mi0uMDgtMS4zMy0uMjUtLjQxLS4xNi0uNzctLjQtMS4wOC0uNy0uMy0uMzEtLjU0LS42OS0uNzItMS4xMy0uMTctLjQ0LS4yNi0uOTUtLjI2LTEuNTJ6bTQuNjEtLjYyYzAtLjU1LS4xMS0uOTgtLjM0LTEuMjgtLjIzLS4zMS0uNTgtLjQ3LTEuMDYtLjQ3LS40MSAwLS43Ny4xNS0xLjA4LjQ1LS4zMS4yOS0uNS43My0uNTcgMS4zem0zLjAxIDIuMjNjLjMxLjI0LjYxLjQzLjkyLjU3LjMuMTMuNjMuMi45OC4yLjM4IDAgLjY1LS4wOC44My0uMjNzLjI3LS4zNS4yNy0uNmMwLS4xNC0uMDUtLjI2LS4xMy0uMzctLjA4LS4xLS4yLS4yLS4zNC0uMjgtLjE0LS4wOS0uMjktLjE2LS40Ny0uMjNsLS41My0uMjJjLS4yMy0uMDktLjQ2LS4xOC0uNjktLjMtLjIzLS4xMS0uNDQtLjI0LS42Mi0uNHMtLjMzLS4zNS0uNDUtLjU1Yy0uMTItLjIxLS4xOC0uNDYtLjE4LS43NSAwLS42MS4yMy0xLjEuNjgtMS40OS40NC0uMzggMS4wNi0uNTcgMS44My0uNTcuNDggMCAuOTEuMDggMS4yOS4yNXMuNzEuMzYuOTkuNTdsLS43NC45OGMtLjI0LS4xNy0uNDktLjMyLS43My0uNDItLjI1LS4xMS0uNTEtLjE2LS43OC0uMTYtLjM1IDAtLjYuMDctLjc2LjIxLS4xNy4xNS0uMjUuMzMtLjI1LjU0IDAgLjE0LjA0LjI2LjEyLjM2cy4xOC4xOC4zMS4yNmMuMTQuMDcuMjkuMTQuNDYuMjFsLjU0LjE5Yy4yMy4wOS40Ny4xOC43LjI5cy40NC4yNC42NC40Yy4xOS4xNi4zNC4zNS40Ni41OC4xMS4yMy4xNy41LjE3LjgyIDAgLjMtLjA2LjU4LS4xNy44My0uMTIuMjYtLjI5LjQ4LS41MS42OC0uMjMuMTktLjUxLjM0LS44NC40NS0uMzQuMTEtLjcyLjE3LTEuMTUuMTctLjQ4IDAtLjk1LS4wOS0xLjQxLS4yNy0uNDYtLjE5LS44Ni0uNDEtMS4yLS42OHoiIGZpbGw9IiM1MzUzNTMiLz48L2c+PC9zdmc+)](https://crossmark.crossref.org/dialog/?doi=10.1038/nature14236)

### Cite this article

Mnih, V., Kavukcuoglu, K., Silver, D. *et al.* Human-level control through deep reinforcement learning. *Nature* **518,** 529–533 (2015). https://doi.org/10.1038/nature14236

[Download citation](https://citation-needed.springer.com/v2/references/10.1038/nature14236?format=refman&flavour=citation)

-   Received: 10 July 2014
    
-   Accepted: 16 January 2015
    
-   Published: 25 February 2015
    
-   Issue Date: 26 February 2015
    
-   DOI: https://doi.org/10.1038/nature14236
    

### Subjects

## Further reading

## Comments

By submitting a comment you agree to abide by our [Terms](https://www.nature.com/info/tandc.html) and [Community Guidelines](https://www.nature.com/info/community-guidelines.html). If you find something abusive or that does not comply with our terms or guidelines please flag it as inappropriate.
