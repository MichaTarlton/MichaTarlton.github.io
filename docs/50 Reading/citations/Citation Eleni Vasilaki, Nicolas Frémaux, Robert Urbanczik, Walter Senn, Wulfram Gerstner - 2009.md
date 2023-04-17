---
Topics: 
type: citation
citetype: 
title: Spike-Based Reinforcement Learning in Continuous State and Action Space: When Policy Gradient Methods Fail
author2: [object Object]
authors: [Eleni Vasilaki, Nicolas Frémaux, Robert Urbanczik, Walter Senn, Wulfram Gerstner]
year: 2009
URL: "https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1000586"
citekey: vasilakiSpikeBasedReinforcementLearning2009
infotags: []

---

[[@vasilakiSpikeBasedReinforcementLearning2009]]

[Zotero Link](zotero://select/items/@vasilakiSpikeBasedReinforcementLearning2009)
PDF: 
Files: 

# Spike-Based Reinforcement Learning in Continuous State and Action Space: When Policy Gradient Methods Fail
# Abstract
Changes of synaptic connections between neurons are thought to be the physiological basis of learning. These changes can be gated by neuromodulators that encode the presence of reward. We study a family of reward-modulated synaptic learning rules for spiking neurons on a learning task in continuous space inspired by the Morris Water maze. The synaptic update rule modifies the release probability of synaptic transmission and depends on the timing of presynaptic spike arrival, postsynaptic action potentials, as well as the membrane potential of the postsynaptic neuron. The family of learning rules includes an optimal rule derived from policy gradient methods as well as reward modulated Hebbian learning. The synaptic update rule is implemented in a population of spiking neurons using a network architecture that combines feedforward input with lateral connections. Actions are represented by a population of hypothetical action cells with strong mexican-hat connectivity and are read out at theta frequency. We show that in this architecture, a standard policy gradient rule fails to solve the Morris watermaze task, whereas a variant with a Hebbian bias can learn the task within 20 trials, consistent with experiments. This result does not depend on implementation details such as the size of the neuronal populations. Our theoretical approach shows how learning new behaviors can be linked to reward-modulated plasticity at the level of single synapses and makes predictions about the voltage and spike-timing dependence of synaptic plasticity and the influence of neuromodulators such as dopamine. It is an important step towards connecting formal theories of reinforcement learning with neuronal and synaptic properties.


