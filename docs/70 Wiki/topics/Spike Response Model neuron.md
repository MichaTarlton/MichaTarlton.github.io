---
aliases: 
type: topics
status: open
priority: p4
creationtag: 2022-09-21 10:51
infotags: [neuron, synapse, SNN]
---
# Extracts
From [[@vasilakiSpikeBasedReinforcementLearning2009#Three-factor learning rule for spiking neurons]]

Thus the total membrane potential of the Spike Response Model neuron is [20]:
$$
u_i(t)=u_{\text {rest }}+\sum_{j=1}^N w_{i j} \sum_{t_j^{\prime} \in x_j} \varepsilon\left(t-t_j^f\right)+\sum_{t_i \in y_{i, t}} \eta\left(t-t_i^f\right)
$$
where $u_{\text {rest }}$ is the resting potential, $x_j$ is the set of presynaptic spikes, $y_{i, t}=\left\{t_i^1, t_i^2, \ldots, t_i^F<t\right\}$ is the set of postsynaptic spikes up to time $t$.



# Search
```query 
line:("Spike Response Model neuron")
```