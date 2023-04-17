---
aliases: [e-decay,]
type: topics
status: open
priority: p4
creationtag: 2022-09-07 10:45
infotags: [automata, MAB, RL]
---

# ϵ-Decay Strategies
[Taken from](https://towardsdatascience.com/multi-armed-bandits-and-reinforcement-learning-dc9001dcb8da)

The ϵ-greedy strategies have an obvious weakness in that they continue to include random noise no matter how many examples they see. It would be better for these to settle on an optimal solution and continue to exploit it. To this end, we can introduce ϵ-decay which reduces the probability of exploration with every step. This works by defining ϵ as a function of the number of steps, _n_.
$$\epsilon (n) = \frac{1}{1+n \beta} $$
Where β<1 is introduced as a scaling factor to reduce the scaling rate so that the algorithm has sufficient opportunity to explore. In this case, we also include +1 in the denominator to prevent infinities from appearing.
```query 
line:("Epsilon Decay") OR  line:("e-decay") 
```