---
type: development
status: active
priority: p4
project: sbf-automata
creationtag: 2022-11-29 10:13
infotags:
people:
date:
---

# The SBF Automata Design
This automata is designed with the purpose of discovering some temporal pattern in reward response from an environment. We describe a basic model here and will expand by describing possible variations throughout.

# The Time Basis of the Model 
The environment is a discrete time space, divided into discrete time-steps. All elements of the model will be temporally fixed to the start time, $t_0$ , with no option to modify or change their patterns in relation to $t_0$.  Future variations we will modify the option of variability in the time space. This environment, makes available a reward at certain cyclic rate, which begins at $t_0$ and repeats within the time space. The environment must be interacted with by the agent(s), at these cyclic points in the time space in order to receive the reward. Thus this *temporal bandit* acts much in the same way as a multi-option bandit problem. However the optimal choice to be selected is a $n$ -phase reward cycle, where $n$ is the number of discrete timesteps at which the cycle repeats.

# The agents
The elemental agents of this model likewise poll the environment at a $n$ phase cycle which is distinct and unique to each agent. We begin with an arbitrary distribution of $n$-phase agents (e.g. in our experiment below we use the first twenty-five prime numbers). in the future we may use a more defined distribution such as a Gaussian.

The model contains $n = (1, 2, …, N)$ cyclic agents, where $N$ is the max cycle size. These elementary agents inform a downstream “master” node, which ultimately makes the decision to poll the environment at each time step. This decision is informed by the upstream nodes via weighted majority decision.

The master node makes the decision to poll the environment with some probability:  $P = \sum w_{active}$.

The weight of the contribution from the upstream nodes to the final decision is determined by their contribution when a reward is received. The sum of the weights should equal 1 , such that:  $\sum\limits^{N} w_{n}=1$. Weights are incremented to elemental agents which are active at time steps where a reward is issued, $w_{active}$, such that, at $t_{reward}$:  $w_{active} = w_{active} + \frac{1}{N} \alpha$  & $\space w_{inactive} = w_{inactive} - \frac{1}{N} \beta$. Where  $\alpha$ and $\beta$ control the learning rate and decay rate, respectively. No update occurs during time-steps where no update occurs.


See outcome: [[First python implementation - conditions and results]]