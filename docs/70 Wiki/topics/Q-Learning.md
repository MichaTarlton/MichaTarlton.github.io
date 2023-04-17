---
aliases: ["Q values", Q-Value]
type:  topics
status: open
priority: p4
creationtag: 2022-05-07 17:51
infotags: [RL,Q-Learning]
---
See: [[Deep Q-Learning]]

Q-Learning is the Reinforcement Learning alogrithm of assigning some Q-value to a policy of “environment condition” to “action”.

## From [NMA - RL tutorial 3]()
Now that we have our environment, how can we solve it? 

> One of the most famous algorithms for estimating action values (aka Q-values) is the [[Temporal Difference (TD)]] **control** algorithm known as *Q-learning* (Watkins, 1989). 
> 
> $$\begin{equation}
 Q(s_t,a_t) \leftarrow Q(s_t,a_t) + \alpha \big(r_t + \gamma\max_\limits{a} Q(s_{t+1},a_{t+1}) - Q(s_t,a_t)\big)
 \end{equation}$$
> 
> where 
> $Q(s,a)$ is the value function for action $a$ at state $s$, 
> $\alpha$ is the learning rate, 
> $r$ is the reward, and 
> $\gamma$ is the temporal discount rate.
> 
> The expression $r_t + \gamma\max_\limits{a} Q(s_{t+1},a_{t+1})$ is referred to as the TD target while the full expression
> 
> $$\begin{equation}
 r_t + \gamma\max_\limits{a} Q(s_{t+1},a_{t+1}) - Q(s_t,a_t),
 \end{equation}$$
> i.e., the difference between the TD target and the current Q-value, is referred to as the TD error, or reward prediction error.
> 
> Because of the max operator used to select the optimal Q-value in the TD target, Q-learning directly estimates the optimal action value, i.e. the cumulative future reward that would be obtained if the agent behaved optimally, regardless of the policy currently followed by the agent. For this reason, Q-learning is referred to as an **off-policy** method.


# Q-Values
From [[@pateriaHierarchicalReinforcementLearning2021| Pateria et al. 2021]]
![[50 Reading/citations/@pateriaHierarchicalReinforcementLearning2021#Q-Value]]
# SARSA
See also [[SARSA Algorithm]] which is an alternative to Q-Learning