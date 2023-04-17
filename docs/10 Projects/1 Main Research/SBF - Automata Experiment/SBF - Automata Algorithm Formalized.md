---
aliases:
type: development
project: Survey Paper/SBF-Model/SBF-automata
status: active
priority: p1
creationtag: 2023-01-27 10:55
infotags: [automata, sbf]
---
 See: [[Weighted Majority Vote Version 27.01.23]]
 See: [[SBFA - Normalized Automata Vote]]


# Initial Outline of Model to be created
This is the description of a simplistic model. Variations can be added and will be discussed. 
## Time basis of model
- This environment will be a discrete time space, divided into discrete time-steps
- All elements of the model will be temporally fixed to the start time: $t_0$ 
- With no option to modify or change their patterns in relation to $t_0$
	- though in future variations we will modify this option
- The challenge, is an environment which makes available a reward at certain cyclic rate, which begins at $t_0$ and repeats within the time space
- The environment must be polled / interacted with, by the agent(s), at these cyclic points in the time space
- Thus this *temporal bandit* acts in the same multi-option bandit of the prototypical multi-arm bandit, how ever the optimal choice to be selected is a $n$ -phase cycle, where $n$ is the number of discrete timesteps at which the cycle repeats
## The agents
- Likewise, the elemental agents of this model, poll the environment, at a distinct and unique to each agent, $n$ phase cycle 
- We include a (?) distribution of $n$-phase agents 
	- Arbitrary distribution to start 
		- Though at some point we will have a more defined distribution such as a Gaussian
	- We begin with $n = (1, 2, …, N)$ cycle agents 
	- Where $N$ is the arbitrary max cycle size
- These elementary agents inform a downstream node
- This master node, makes the decision to poll the environment at each time step
- This decision is informed by the upstream nodes via weighted majority decision
- The weight of the contribution from the upstream nodes to the final decision is determined by their contribution to reward
	- Do this through simple back-propagation
	- The sum of the weights should equal 1 , such that:  $\sum\limits^{N} w_{n}=1$ 
- Weights are incremented to elemental agents which are active at time steps where a reward is issued: $w_{active}$
	- Such that, at $t_{reward}$:
		- $w_{active} = w_{active} + \frac{1}{N} \alpha$
		- $\& \space w_{inactive} = w_{inactive} - \frac{1}{N} \beta$ 
			- Adding the decay parameter beta for code
			- beta can be set equal to alpha
			- May add condition such that no update occurs where no reward took place
			- Should I make it keep these static?
			- No that would saturate
		- Where $\alpha$ is some control parameter
			- We can do without it for now, so that $\alpha=1$
- The master node makes the decision to poll the environment with some probability:
	- $P = \sum w_{active}$
	- 
	- When a pull is rewarded it will apply the update to the weights as seen above