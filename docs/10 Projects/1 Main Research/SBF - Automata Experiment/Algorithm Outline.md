---
type: [development, abstract]
status: active
priority: p1
project: SBF-automata
creationtag: 2023-03-21 11:24
infotags: [SBF, algorithm]
people: na
date:
---

Spawned from :: [[SBF - Automata Experiment]]
See also:
- [[Weighted Majority Vote Version 27.01.23]]
- [[SBFA - Normalized Automata Vote]]
- [[SBF - Automata Algorithm Formalized]]


# Global conditions

Initialize oscillator agents $n_i=1,n$
Assign corresponding time check cycles $(tc)$ to oscillator agents: $n_{i} = n_{tc}$
Initialize weights $w_{n}= \frac{1}{n}$
Initialize reward interval $R_t$


# Weighted Majority Vote
Technically they are all WMV
as suggested by Anis
- [ ]  Check against current code


## Formal Format
**For** $t =0,T$ **do**
	Check “active” agents with check cycles in phase with current time step, where $t \ mod \ tc = 0$
	Take sum of weights of active agents, $w_{t} = \sum{w_{active}}$
	Take probability $P$ of polling environment for reward

**If** $P \geq w_t$ : do nothing and move to next time-step	

**If** $P \leq w_t$
	**If $R_t \ mod \ t = 0$** , **timestep is on a reward interval**:
		**Decrease weights of inactive agents**: $$w_{n-inactive} = w_{n-inactive} \times \frac{1}{2}$$**Active Agents are not updated**.
		**Divided all weights by sum of all weights**:$$w_{n} = \frac{w_{n}}{\sum\limits w_{n}}$$
	**Else**, timestep is **not** on a reward interval : do nothing and move to next time-step
	
**End For loop**

# Normalized Automata (no punishment)
The more automata version I made

This is more balanced or even (up until the cost variation) but not proportional.


## Formal Format

**For** $t =0,T$ **do**
	Check “active” agents with check cycles in phase with current time step, where $t \ mod \ tc = 0$
	Take sum of weights of active agents, $w_{t} = \sum{w_{active}}$
	Take probability $P$ of polling environment for reward

**If** $P \geq w_t$ **:** do nothing and move to next time-step	 
**If** $P \leq w_t$
	 **If $R_t \ mod \ t = 0$ :** 
			**Increase weights of active agents**: $$w_{n-active} = w_{n-active} + \alpha \frac{\sum w_{n-inactive}}{n_{active}}$$
			**Decrease weights of inactive agents**: $$w_{n-inactive} = w_{n-inactive} - \alpha \frac{\sum w_{n-inactive}}{n_{inactive}}$$
	**Else** $R_t \ mod \ t \neq 0$ **:** do nothing and move to next time-step
**End For**




## When punishment was added
This method was meant to add a simple punishment step **however I may have done it wrong and need to recheck**
This method was defective as the weights ran away to infinity around $timestep > 1200$.

The same as the above algo except append a condition at the  `else:`  where the update step was inverted such that:

**Else ($R_t \ mod \ t \neq 0$):** 
	**Decrease weights of active agents**: $$w_{n-active} = w_{n-active} - \alpha \frac{\sum w_{n-active}}{n_{active}}$$
	**Increase weights of active agents**: $$w_{n-inactive} = w_{n-inactive} + \alpha \frac{\sum w_{n-active}}{n_{inactive}}$$
		

# Normalized Automata v.2 with Punishment
- [ ] Fix this⏫ #p1 #SBFA 
## Formal Format

**For** $t =0,T$ **do**
	Check “active” agents with check cycles in phase with current time step, where $t \ mod \ tc = 0$
	Take sum of weights of active agents, $w_{t} = \sum{w_{active}}$
	Take probability $P$ of polling environment for reward

**If** $P \geq w_t$ **:** do nothing and move to next time-step	 
**If** $P \leq w_t$
	 **If $R_t \ mod \ t = 0$ :** 
			**Increase weights of active agents**: $$w_{n-active} = w_{n-active} + \alpha \frac{\sum w_{n-inactive}}{n_{active}}$$
			**Decrease weights of inactive agents**: $$w_{n-inactive} = w_{n-inactive} - \alpha \frac{\sum w_{n-inactive}}{n_{inactive}}$$
	**Else** $R_t \ mod \ t \neq 0$ **:** do nothing and move to next time-step
**End For**
