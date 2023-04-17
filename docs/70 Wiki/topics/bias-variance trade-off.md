---
aliases: 
type: topics
status: open
priority: p4
creationtag: 2023-04-12 22:25
infotags:
---


> The **bias–variance trade-off** [26](https://www.sciencedirect.com/science/article/pii/S1364661318301931?via%3Dihub#bib0130), [27](https://www.sciencedirect.com/science/article/pii/S1364661318301931?via%3Dihub#bib0135) provides a formal lens through which to view this issue: an RL agent can reduce bias (the difference between the learned and true value function) by finely decomposing the state space, but only at the expense of increasing variance (sensitivity to noise in the training data). 
> 
> Balancing bias and variance requires state representations that permit some degree of generalization. 
> 
> In the context of timing, this balance can be achieved using state representations that change smoothly over time. Temporal smoothness acts as a soft constraint on the function class, effectively low-pass filtering the value function and thereby suppressing noise.
> 
> We can think about the bias–variance trade-off in neurobiological terms by imagining a set of neurons whose firing represents the activation of particular substates. If the neurons are narrowly tuned, and only respond during the interval corresponding to their preferred substate, then bias will be low and variance will be high: the value function can be precisely represented at each time interval, but the estimated values will be unreliable. 
> 
> If the neurons are broadly tuned, and thus respond partially to neighboring time intervals, then bias will increase and variance will be reduced: the value function can only be imprecisely represented at each time interval, but the estimated values will be more reliable because the neurons collect partial credit for rewards received outside their preferred time interval, effectively increasing the amount of data available to each neuron.

- From [[@petterIntegratingModelsInterval2018]]



```query 
line:("bias-variance trade-off") OR  line:("") 
```