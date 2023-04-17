---
aliases:
type: topics
status: open
priority: p4
creationtag: 2022-10-15 18:28
infotags:
---
From [NMA Model-Based RL tutorial](https://compneuro.neuromatch.io/tutorials/W3D4_ReinforcementLearning/student/W3D4_Tutorial4.html)
See your git implementation.

  

> In this section, we will implement Dyna-Q, one of the simplest model-based reinforcement learning algorithms. A Dyna-Q agent combines acting, learning, and planning. The first two components -- acting and learning -- are just like what we have studied previously. Q-learning, for example, learns by acting in the world, and therefore combines acting and learning. But a Dyna-Q agent also implements planning, or simulating experiences from a model--and learns from them.
> 
> In theory, one can think of a Dyna-Q agent as implementing acting, learning, and planning simultaneously, at all times. But, in practice, one needs to specify the algorithm as a sequence of steps. The most common way in which the Dyna-Q agent is implemented is by adding a planning routine to a Q-learning agent: after the agent acts in the real world and learns from the observed experience, the agent is allowed a series of $k$ *planning steps*. At each one of those $k$ planning steps, the model generates a simulated experience by randomly sampling from the history of all previously experienced state-action pairs. The agent then learns from this simulated experience, again using the same Q-learning rule that you implemented for learning from real experience. This simulated experience is simply a one-step transition, i.e., a state, an action, and the resulting state and reward. So, in practice, a Dyna-Q agent learns (via Q-learning) from one step of **real** experience during acting, and then from k steps of **simulated** experience during planning. 
> 
> There's one final detail about this algorithm: where does the simulated experiences come from or, in other words, what is the "model"? In Dyna-Q, as the agent interacts with the environment, the agent also learns the model. For simplicity, Dyna-Q implements model-learning in an almost trivial way, as simply caching the results of each transition. Thus, after each one-step transition in the environment, the agent saves the results of this transition in a big matrix, and consults that matrix during each of the planning steps. Obviously, this model-learning strategy only makes sense if the world is deterministic (so that each state-action pair always leads to the same state and reward), and this is the setting of the exercise below. However, even this simple setting can already highlight one of Dyna-Q major strengths: the fact that the planning is done at the same time as the agent interacts with the environment, which means that new information gained from the interaction may change the model and thereby interact with planning in potentially interesting ways.

---
**TABULAR DYNA-Q**

Initialize $Q(s,a)$ and $Model(s,a)$ for all $s \in S$ and $a \in A$.

Loop forever:

> (a) $S$ &larr; current (nonterminal) state <br>
> (b) $A$ &larr; $\epsilon$-greedy$(S,Q)$ <br>
> (c) Take action $A$; observe resultant reward, $R$, and state, $S'$ <br>
> (d) $Q(S,A)$ &larr; $Q(S,A) + \alpha \left[R + \gamma \max_{a} Q(S',a) - Q(S,A)\right]$ <br>
> (e) $Model(S,A)$ &larr; $R,S'$ (assuming deterministic environment) <br>
> (f) Loop repeat $k$ times: <br>
>> $S$ &larr; random previously observed state <br>
>> $A$ &larr; random action previously taken in $S$ <br>
>> $R,S'$ &larr; $Model(S,A)$ <br>
>> $Q(S,A)$ &larr; $Q(S,A) + \alpha \left[R + \gamma \max_{a} Q(S',a) - Q(S,A)\right]$ <br>


---

```query 
line:("Dyna-Q")
```