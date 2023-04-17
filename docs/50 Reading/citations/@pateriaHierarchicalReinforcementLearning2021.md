---
title: Hierarchical Reinforcement Learning: A Comprehensive Survey
authors: Shubham Pateria, Budhitama Subagdja, Ah-hwee Tan, Chai Quek
year: 2021
https://doi.org/10.1145/3453160
citekey: pateriaHierarchicalReinforcementLearning2021
---
# Abstract
Hierarchical Reinforcement Learning (HRL) enables autonomous decomposition of challenging long-horizon decision-making tasks into simpler subtasks. During the past years, the landscape of HRL research has grown profoundly, resulting in copious approaches. A comprehensive overview of this vast landscape is necessary to study HRL in an organized manner. We provide a survey of the diverse HRL approaches concerning the challenges of learning hierarchical policies, subtask discovery, transfer learning, and multi-agent learning using HRL. The survey is presented according to a novel taxonomy of the approaches. Based on the survey, a set of important open problems is proposed to motivate the future research in HRL. Furthermore, we outline a few suitable task domains for evaluating the HRL approaches and a few interesting examples of the practical applications of HRL in the Supplementary Material.


# Notes
![[@pateriaHierarchicalReinforcementLearning2021-comments]]
# Extracts
## RL
To learn the optimal policy, the agent explores the state and action spaces relevant to the task by executing various sequences of state-action-next state transitions. The average length of such sequences^[The length of a sequence is defined as the number of items in that sequence. In this case, an item is an action.] is called the task horizon. 

If the horizon is long while the task involves large state and action spaces, then the exploration space also becomes large. This results in the poor performance of the standard RL algorithms [56, 68, 100] on such long-horizon tasks without sophisticated exploration techniques [10, 71, 75].

## HRL
[[Hierarchical Reinforcement Learning]] (HRL) decomposes a long-horizon reinforcement learning task into a hierarchy of subproblems or subtasks such that a higher-level policy learns to perform the task by choosing optimal subtasks as the higher-level actions. 

A subtask may itself be a reinforcement learning problem with a lower-level policy learning to solve it [39]. This hierarchy of policies collectively determines the behavior of the agent. 

Task decomposition effectively reduces the original task’s long horizon into a shorter horizon in terms of the sequences of subtasks. 

This is because each subtask is a higher-level action that persists for a longer timescale compared to a lower-level action, a property that is often referred to as **[[temporal abstraction]]** [7, 20, 93]. ^vefzvx

Temporal abstraction can also enable efficient credit assignment over longer timescales [99]. At the same time, a subtask may itself be easier to learn and the learned subtasks lead to more structured exploration over the course of training of the HRL agent [71].


## Contributions of this survey. 
The objective of this survey is to thoroughly review the literature on HRL and provide a panorama of the approaches developed so far. The key contributions are as follows: 
1. We conduct a comprehensive survey of the work done so far in the field of HRL. The survey includes the approaches for learning hierarchies of policies, independent subtask discovery, unified HRL, multi-task/transfer learning with HRL, and multi-agent HRL. 
2.  We provide a novel taxonomy to organize the HRL approaches along important characteristic dimensions such as single-agent vs. multi-agent, single-task vs. multi-task, and without subtask discovery vs. with subtask discovery. 
3. We identify a set of important open problems to provide the directions for future research concerning the scalability, efficiency, and theoretical robustness of HRL.

## What are the differences between this survey and the previous ones?
Barto et al [7]provided a survey of the advances in HRL up to the year 2003. That survey includes an important overview of the classical approaches, mainly MAXQ, Options [93], and HAMs [73]. Significant developments have occurred in the field of HRL since the time of that survey, such as subtask discovery using graph analysis, variational inference, autoencoding, unified HRL, subtask discovery in multi-agent HRL, transfer learning with HRL, and so on. Our survey mainly differs from that of Barto et al. [7] in the sense that we review the new HRL approaches that have emerged after their survey in addition to the classical approaches covered by them.

Al-Emran et al.^[[Hierarchical Reinforcement Learning: A Survey](https://journal.uob.edu.bh/handle/123456789/443)] performed a survey from the perspective of the practical applications of HRL. However, it does not include several important approaches that do not apply to the chosen applications, such as the recent unified HRL techniques, transfer learning with HRL, multi-agent HRL, and so on. In contrast, we survey the HRL approaches broadly and provide a general taxonomy that is application-agnostic.

The most recent survey by Mendonca et al.^[@mendoncaGraphBasedSkillAcquisition2019] gives a detailed review of the graph-based approaches for subtask discovery. Due to this limited scope, their survey goes into the depths of the graph-based subtask discovery but excludes other important aspects of HRL research such as the techniques for learning a hierarchy of policies, subtask discovery using variational inference, unified HRL, transfer learning with HRL, multi-agent HRL, and so on. However, we review all such approaches along with the graph-based subtask discovery (Section 3.3.1) in the spirit of providing a broader view of the HRL research

---

## 2 PRELIMINARIES
### 2.1 Reinforcement Learning
RL refers to learning how to take actions in different states of an environment to maximize cumulative future reward [91], where the reward is a form of feedback associated with a task and received in response to an action.

The majority of the current RL research is built upon the theory of **Markov Decision Processes (MDPs)** [12].  An MDP is control process defined using a tuple $\langle S, A, P, r\rangle$. 
Here, 
- $S$ is the state space of the environment, where a state $s \in S$ represents a situation of the environment. 
- $A$ is the set of actions that can be taken by an agent. $r: S \times A \rightarrow \mathbb{R}$ is the numerical reward obtained as a function of state and action. 
- The effect of an action on the future state is captured by a probabilistic transition function $P\left(s_{t+1} \mid s_{t}, a_{t}\right) \rightarrow[0,1]$ where $s_{t+1} \in S$ is the next state observed after taking action $a_{t} \in A$ in a state $s_{t} \in S$ at time $t$. 
- An MDP is stochastic if there exists a state-action pair $\left(s_{t}, a_{t}\right)$ for which $P\left(s_{t+1} \mid s_{t}, a_{t}\right) \neq 1$, because the effect of an action is not deterministic. 
- Contrarily, an MDP is deterministic if for every state-action pair $\left(s_{t}, a_{t}\right)$, $P\left(s_{t+1} \mid s_{t}, a_{t}\right)=1$. The agent takes actions according to a policy $\pi: S \times A \rightarrow[0,1]$. This policy may be stochastic.

One step of interaction between the agent and the environment produces a transition from current state $s_{t}$ to next state $s_{t+1}$, observed as an experience data sample $\left(s_{t}, a_{t}, r_{t}, s_{t+1}\right)$. 

A sequence of such transitions constitutes a trajectory. The trajectory taken from any starting state and action pair $\left(s_{t}, a_{t}\right)$ is affected by the stochasticity in the policy and in the state transitions (as per $\left.P\left(s_{t+1} \mid s_{t}, a_{t}\right)\right)$. 
#### Q-Value
Thus, the value of taking $a_{t}$ in $s_{t}$ is formally calculated as the expected (or average) cumulative reward obtained over all possible trajectories, as follows: ^qi51p3
$$
Q^{\pi}\left(s_{t}, a_{t}\right)=r\left(s_{t}, a_{t}\right)+\mathbb{E}_{a \sim \pi(s)}\left[\sum_{i=1}^{\infty} \gamma^{i} r\left(s_{t+i}, a_{t+i}\right) \mid s_{t}, a_{t}\right] .
$$
Here, $Q^{\pi}\left(s_{t}, a_{t}\right)$ is called the Q-Value of the state-action pair while an agent follows a policy $\pi$. $\gamma \in[0,1)$ is called the [[discount factor]]. $a \sim \pi(s)$ implies that an action is sampled using the policy $\pi$. The core objective of $\mathbf{R L}$ is to learn an optimal policy $\pi^{*}$ that satisfies the following condition:
$$
\pi^{*}=\arg \max _{\pi} Q^{\pi}(s, a), \forall s \in S, \forall a \in A .
$$

### 2.2 Hierarchical Reinforcement Learning
It can be inferred from Equations (1) and (2) that the objective of an RL agent is to search for a policy that maximizes the cumulative reward averaged over various possible trajectories the agent can take while following that policy. While exploring the state and action spaces to learn the optimal policy, the agent takes various trajectories whose expected length is the task horizon (the horizon is shown as theoretically infinite in Equation (1), but in practice it may be finite). As mentioned in Section 1, when the state and action spaces are large, and the task horizon is long, the exploration becomes challenging using the standard RL approach $[10,71,75]$.

HRL provides a mechanism to perform a challenging task by decomposing it into simpler subtasks using a hierarchy of policies learned via reinforcement learning. In such a hierarchy, the highest-level policy generally chooses the subtasks of the main task as its actions [39]. This policy is trained to perform the main task in terms of the sequence of its subtasks, using the rewards obtained in the main task. 

At a lower level in the hierarchy, a subtask chosen by the higher-level is itself a reinforcement learning problem. A lower-level policy learns to perform that subtask using the internal rewards related to it (optionally, the main task reward may also be added). The lowest-level policies choose the basic actions that are henceforth referred to as **[[primitive actions]]**.

#### 2.2.1 Formal Definition of a Subtask. 
The definition of a subtask in the formal context of HRL is provided in this subsection. This definition is a culmination of the different ways in which different HRL approaches define the subtasks. Hence, it should be considered as a general definition. A particular HRL approach may only use selective components of the general definition. The specifics are further discussed in Section $3 .$

First, we denote the main long-horizon task as $\Gamma$ and the task policy as $\pi_{\Gamma}$. 
The task policy is at the top of a hierarchy, for e.g., $\pi_{G T H}$ in Figure 1 . 

A subtask is denoted as $\omega$. It is defined using the components described as follows:
- $\pi_{\omega}$, which is the policy of the subtask. It maps the environment states to primitive actions or to the subtasks of $\omega$ [93].
- **The objective components:**
	- $r_{\omega}$, which is the subtask reward used to train $\pi_{\omega}$. 
		- This is typically different from the reward associated with the main task $[51,69,99]$,
	- $g_{\omega}$, which is a subgoal or a set of subgoals associated with $\omega$.  ^srvptu
		- A subgoal might be a state $s \in S$ itself $[64,84,87]$, an abstract form of a state [54, 69], a [[learned embedding]] [70, 88 , 99], and so on. The reward $r_{\omega}$ might be defined with respect to the subgoal(s).
- **The execution components:**
	- $I_{\omega}$, which is the initiation condition of $\omega$. It may be defined as a set of states in which $\omega$ can be chosen for execution [93], as a function that modulates the probability of choosing $\omega$ in a particular state [45], as a set of logical conditions [74], and so on.
	- $\beta_{\omega}$, which is the termination condition of $\omega$. It may be defined as a set of states in which $\omega$ should terminate if it is being executed $[19,51]$, as a function that modulates the probability of terminating $\omega$ in a particular state $[3,93]$, as a fixed time-limit $[54,69]$, and so on. If $g_{\omega}$ is defined, then the subgoal state is also usually included as a state in which $\omega$ must terminate [51].

In the remainder of this article, the term "subtask" should be inferred as referring to this formal definition.


![[@pateriaHierarchicalReinforcementLearning2021-comments#^n16zdf]]

#### 2.2.2 Formalism of HRL Based on Semi-Markov Decision Process. 
HRL is formalized on the basis of the theory of [[Semi-Markov Decision Process (SMDP)]] ^[[Semi‐Markov Decision Processes - Baykal‐Gürsoy - 2011](https://onlinelibrary.wiley.com/doi/10.1002/9780470400531.eorms0757)]. 
An SMDP is a stochastic control process similar to an MDP (Section 2.1), but unlike MDP, it also involves the concept of time for which an action is executed after it has been chosen.  ^g2foca

In the context of HRL, the actions with the concept of time are the subtasks. 

Starting from a state $s_{t} \in S$, assume that an agent chooses a subtask $\omega_{t} \in \Omega$, 
where $\Omega$ is the set of subtasks (or the subtask space). 

Then, the transition function of the SMDP is defined as a joint distribution 
$$
P\left(s_{t+c_{\omega_{t}}}, c_{\omega_{t}} \mid s_{t}, \omega_{t}\right)=P\left(s_{t+c_{\omega_{t}}} \mid s_{t}, \omega_{t}, c_{\omega_{t}}\right) P\left(c_{\omega_{t}} \mid s_{t}, \omega_{t}\right) .
$$
- $c_{\omega_{t}}$ denotes the number of timesteps for which $\omega_{t}$ is executed, starting from the state $s_{t} \cdot c_{\omega_{t}}$ is actually determined by the termination condition $\beta_{\omega_{t}}$, which is one of the execution components defined in Section 2.2.1.

The reward obtained in response to performing the subtask $\omega_{t}$ starting from state $s_{t}$ is denoted as $R\left(s_{t}, \omega_{t}\right)$, calculated as follows,
$$
R\left(s_{t}, \omega_{t}\right)=\mathbb{E}_{a \sim \pi_{\omega_{t}}(s)}\left[\sum_{i=0}^{c_{\omega_{t}}-1} \gamma^{i} r\left(s_{t+i}, a_{t+i}\right) \mid s_{t}, a_{t}=\pi_{\omega_{t}}\left(s_{t}\right)\right] .
$$
Equation (4) indicates that the reward $R\left(s_{t}, \omega_{t}\right)$ is equal to the expected cumulative reward obtained while following the subtask policy $\pi_{\omega_{t}}$ from time $t$ until the termination of $\omega_{t}$ after $c_{\omega_{t}}$ timesteps. Now, an optimal task policy would be the one that leads to the following desired maximum Qvalue:
$$
Q\left(s_{t}, \omega_{t}\right)=R\left(s_{t}, \omega_{t}\right)+\sum_{s_{t+c_{\omega t}}, c_{\omega_{t}}} \gamma^{c_{\omega_{t}}} P\left(s_{t+c_{\omega_{t}}}, c_{\omega_{t}} \mid s_{t}, \omega_{t}\right) \max _{\omega_{t+c_{\omega} t}} Q\left(s_{t+c_{\omega_{t}}}, \omega_{t+c_{\omega_{t}}}\right)
$$
$\forall s \in S$ and $\forall \omega \in \Omega$.

It should be noted that the Q-value in Equation (5) also depends on $R\left(s_{t}, \omega_{t}\right)$ and $P\left(s_{t+c_{\omega_{t}}}, c_{\omega_{t}} \mid s_{t}, \omega_{t}\right)$. 

These two quantities are determined by the execution of $\omega_{t}$ using its policy $\pi_{\omega_{t}}$. Therefore, an agent actually needs to learn multiple policies at different levels of a task decomposition hierarchy, including $\pi_{\Gamma}$ and the policies of all the subtasks (e.g., Figure 1). 
> ![[Pasted image 20220507183306.png]]

We extend the notations of subtasks and policies for a multi-level hierarchy as defined below. Please refer to Figure 2 for an example of these notations in the context of an HRL agent with a three-level hierarchy.
- $\omega^{l}$ : a subtask at level $l$ of the hierarchy,
- $\Omega_{\omega^{l}}$ : set of subtasks under the subtask $\omega^{l}$ such that $\omega^{l-1} \in \Omega_{\omega^{l}}$,
	- ![[@pateriaHierarchicalReinforcementLearning2021-comments#^c6fdtz]] 
- $\pi_{\omega^{l}}: S \times \Omega_{\omega^{l}} \rightarrow[0,1]:$ policy of the subtask $\omega^{l}$. In other words, $\omega^{l-1}$ is chosen by $\pi_{\omega^{l}}$,
- $\Omega_{\omega^{1}}=A$, i.e., the output space of a subtask at the lowest level $(l=1)$ is the primitive action space $A$,
- $\pi_{\Gamma}$ and $\Omega_{\Gamma}$ denote the main task policy and the set of subtasks at the highest level, respectively.

Consolidating all the definitions provided above, there are two principal parts of an HRL agent:
- Subtask space ( $\Omega_{\text {hierarchy }}$ ). This is the super-set of all the subtasks used in a hierarchy, i.e., $\Omega_{\text {hierarchy }}=\left\{\Omega_{\omega^{2}}, \Omega_{\omega^{3}}, \Omega_{\omega^{4}}, \ldots, \Omega_{\Gamma}\right\}$.
- Hierarchical policy $\left(\pi_{\text {hierarchy }}\right)$. The primitive action taken by the HRL agent is the result of the recursive choices of subtasks. Consider the three-level hierarchy depicted in Figure 2. In this hierarchy, the main policy $\pi_{\Gamma}$ chooses a level 2 subtask, i.e., $\omega^{2}=\pi_{\Gamma}(s)$ where $\omega^{2} \in \Omega_{\Gamma}$. The policy of $\omega^{2}$ is executed until its termination as per $\beta_{\omega^{2}}$. It chooses the lowest-level subtask $\omega^{1}=\pi_{\omega^{2}}(s)$ where $\omega^{1} \in \Omega_{\omega^{2}}$. The policy of $\omega^{1}$ is executed until its termination as per $\beta_{\omega^{1}}$. This lowest-level policy selects a primitive action, i.e., $a=\pi_{\omega^{1}}(s)$. This complete state-to-subtask-to-action mapping from $\pi_{\omega^{1}}$ is called the hierarchical policy, denoted as $\pi_{\text {hierarchy. }}$. Now, the primitive action taken by the HRL agent as a whole can be equivalently expressed as $a=\pi_{\text {hierarchy }}(s)$. This description can be extrapolated to the hierarchies with more than three levels.

Based on the definitions provided above, the expected discounted cumulative reward received by the HRL agent can be written as,
$$
Q^{\text {hierarchy }}\left(s_{t}, a_{t}\right)=\mathbb{E}_{a \sim \pi_{\text {hierarchy }} \mid \Omega_{\text {hierarchy }}}\left[\sum_{i=0}^{\infty} \gamma^{t+i} r\left(s_{t+i}, a_{t+i}\right) \mid s_{t}, a_{t}\right] \text {, }
$$
where $a \sim \pi_{\text {hierarchy }} \mid \Omega_{\text {hierarchy }}$ indicates that a primitive action $a$ is sampled using the hierarchical policy $\pi_{\text {hierarchy }}$ conditioned on the available subtask space $\Omega_{\text {hierarchy }}$.

> ![[Pasted image 20220507183306.png]]

#### 2.2.3 Problem Definition of HRL. 
The general problem definition of HRL is to find the optimal hierarchical policy $\pi_{\text {hierarchy }}^{*}$ and the optimal subtask space $\Omega_{\text {hierarchy }}^{*}$ as the solution to:

$$\Omega_{\text {hierarchy }}^{*}, \pi_{\text {hierarchy }}^{*}=\operatorname{argmax}_{\Omega_{\text {hierarchy }}} \operatorname{argmax}_{\pi_{\text {hierarchy }} \mid \Omega_{\text {hierarchy }}} Q^{\text {hierarchy }}(s, a), \forall s \in S, a \in A .$$
The HRL problem expressed in Equation (7) can be divided into two parts. The first part is learning hierarchical policy, which refers to finding the optimal hierarchical policy conditioned on the available subtask space (i.e., $\operatorname{argmax}_{\pi_{\text {hierarchy }} \mid \Omega_{\text {hierarchy }}}$ ). 

This is essential, because the hierarchical policy determines the behavior of an HRL agent on any given task. The policies at various levels of $\pi_{\text {hierarchy }}$ can be learned simultaneously in an end-to-end manner $[3,21,52,54,69]$ or they may be learned one level at a time in a bottom-to-top manner $[25,28,60]$. 

The second part is subtask discovery, which refers to automatically finding the optimal subtask space using the HRL agent's experience data (i.e., $\operatorname{argmax}_{\Omega_{\text {hierarchy }}}$ ). Subtask discovery is not essential, because a subtask space could be handcrafted using precise domain knowledge. However, it is necessary for generalized HRL without dependence on the manual handcrafting.

### 2.3 Definitions of Common Terms and Concepts 
A few important terms and concepts that appear commonly in the rest of this article are defined here. Skill. A “skill” is a semantic term for referring to a primitive action policy learnt to perform a subtask, in the sense that such a policy represents the ability of an agent to do something well.

***Universal policy.*** 
In this article, a "universal policy" means a policy that can learn all the possible subtasks by taking the corresponding subgoals $[19,54,99]$ or instructions [41] as input, i.e., $\pi_{\omega}(s)=$ $\pi\left(s, g_{\omega}\right)$, where $\pi\left(s, g_{\omega}\right)$ is the universal policy.

***State abstraction.***
A state abstraction is a mapping, say, $\phi$, that maps the original state space $S$ to some finite lower-dimensional abstract space. If $\phi(s)=\phi\left(s^{\prime}\right)$ for a pair $s, s^{\prime} \in S$, then the two states in the original state space are represented by the same state in the abstract space.

***Reward abstraction.*** 
A reward abstraction means that the rewards given as part of the main task are hidden from the subtask policies and only received by the highest-level policy.

***"Global" initiation condition.***
In the case of definition of a subtask in the tables provided in Section 3, wherever the term "global" is used in reference to the initiation condition $I_{\omega}$, it means that the subtask can be chosen for execution in any of the states in the global state space.

> ![[Pasted image 20220507192438.png]]

## 3 APPROACHES FOR HIERARCHICAL REINFORCEMENT LEARNING

This section presents the review and classification of a wide range of approaches developed Hierarchical Reinforcement Learning. The review is structured according to a novel taxonomy depicted in Figure 3 . To design this taxonomy, the surveyed HRL approaches are arranged along three independent dimensions, which are as follows: (1) Approaches with subtask discovery or without it. (2) Approaches for training single agent or multiple agents. (3) Approaches for learning on single task or multiple tasks. There can be eight possible divisions (octants) of this three-dimensional space. We identify that the majority of the HRL approaches lie in six of these divisions. The approaches are further grouped into five major classes-LHP, UNI, ISD, MAHRL, and TransferHRLbased on the broad challenge addressed by them. The divisions and classes are as follows: