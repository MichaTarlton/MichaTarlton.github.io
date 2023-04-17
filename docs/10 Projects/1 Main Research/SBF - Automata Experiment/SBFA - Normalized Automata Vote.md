---
type: development
status: active
priority: p4
project: SBF-automata
creationtag: 2023-02-10 10:28
infotags: [dev, pseudocode]
people:
date:
---

**This is current as of 06.03.23**

See also: [[SBF - Automata Algorithm Formalized]]
# Algorithm Outline
Do this in the style of the previous non-pseduo code version

Example of formal algo:
[[image-20230110170543307.png]]

---
## Algo
- We set timesteps $t$ from $0$ to $T$ 
	- $T$ is the end step
- We set a reward phase of $R$
	- Which is the cyclic number of timesteps that pass before the reward is available
	- So for every $t$ which divides by $R$, there is an award available
---
- We have agents (or “oscillator”) $n$ which contribute to the ***action vote***, 
	- each has a unique phase $n_t$ , a time step cycle, at which they can contribute to the action vote
	- if the current timestep is not in phase with the agent, that is the current timestep is not divisible by the agent’s unique cyclic phase, the agent can not contribute to the ***action vote***
	- Each agent’s vote has some weight $w_n$
		- This initial weight is $w_{n}= \frac{1}{n}$
- Some learning control parameter $\alpha$
	-  This is set to $\alpha = 0.5$
---
- At each timestep, there occurs an ***action vote*** where the collective agents may decide to act on the environment to check for a reward
	- The collective weighted vote of the agents, decides a probability that an action will take place at each timestep
- If the action vote **fails:**
	- No further actions occur and environment moves to the next timestep
---
 If the action vote **succeeds:**
	- The environment is checked for a reward
	- **If reward is unavailable:**
		- No further actions occur and environment moves to the next timestep
	- **If reward is available:**
		- The weights of inactive agents are reduced:
			- $$w_{n-inactive} = w_{n-inactive} - \alpha \frac{\sum w_{n-inactive}}{n_{inactive}}$$
		- The The weights of agents in phase with the rewarded timestep are rewarded
			- $$w_{n-active} = w_{n-active} + \alpha \frac{\sum w_{n-inactive}}{n_{active}}$$
		- No further actions occur and environment moves to the next timestep
- This is looped 

---

## Formal Format
Initialize oscillator agents $n_i=1,n$
Initialize weights $w_{n}= \frac{1}{n}$
Initialize reward phase $R_t$

**For** $t =0,T$ **do**
	Check “active” agents, where $t \ mod \ n = 0$
	Take sum of weights of active agents, $w_{t} = sum{w_active}$
	Take probability of polling environment $P = w_t$
	**If** $P \leq w_t$
		**Increase weights of active agents**: $$w_{n-active} = w_{n-active} + \alpha \frac{\sum w_{n-inactive}}{n_{active}}$$
		**Decrease weights of inactive agents**: $$w_{n-inactive} = w_{n-inactive} - \alpha \frac{\sum w_{n-inactive}}{n_{inactive}}$$
	**Else**: do nothing and move to next time-step
	**End If**
**End For**

---



# Pseudocode
See [[Pseudocode for SBF Automata]]
