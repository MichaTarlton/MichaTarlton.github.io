---
title:
type: lecture
status: open
priority: p1
project: "MLSS^N 2022 Krakow"
creationtag: 2022-06-27 08:58
infotags: DL
people: "Razvan Pascnau"
date:
---
# Materials
[MLSS^N Day 1 - 27.06.2022 - YouTube](https://youtu.be/N447XbErsGE?t=412)
![[Learning Dynamics 2022.pdf]]

- Zaslavsky thm (1975)

Partitioning the space into regions

With deep networks you can add “more regions” with more hidden layers

Hidden units are “folding the space”

- [ ] Ozair, Bengio 2014 #reading #p3 


So everything is partitions, jus tin higher dimensional space

- century cones?

- ConvNet
- Circular Matricies
	- projections into 
- Local translation invariance
- Inductive Bias
- Approximate v stochastic dropout

# Learning Process

- [How neural networks are trained](https://ml4a.github.io/ml4a/how_neural_networks_are_trained/)
- [ ] Bray and dean 2007 #reading #p4 #stat_phys
- [ ] Fyodorov and WIlliams 2007 #reading #p4 #stat_phys 
- [ ] Liu, Zhu, Belkin, “Loss Landscapes and optimization…“ #reading #p4 
- [ ] arxiv 1703.04933 #reading #p4 
- [ ] Swircz, Czarmecki, Pascanu, 2017 “Local minima in traiing neural networks” #reading #p4 
- [ ] “on recurrent and DNN” Pascanu 2014 #reading #p1
- RMSprop / Adam
- AdaGRad
- [The Evolution of Gradient Descend Optimization Algorithm | by Ramraj Chandradevan | Medium](https://medium.com/@ramrajchandradevan/the-evolution-of-gradient-descend-optimization-algorithm-4106a6702d39)

# Optimization
“Why does it matter that backprop goes from top to bottom?”
- Only have to do vector manipulation versus matrix manipulations

- Recurrent learning #topics #p1 
Forward differentiation as a biologically plausible  model 


## RNNs
DOT(s)
DT
as opposed to stacked rnns



## ESNs
- [ ] Sutskever et al. 2013 “on the importance of initialization and momentum in deep learning” #reading #p2 

## LSTM
and GRUs


- [ ] Gu et al 2020 #reading #p2 
	- non- BP gradient
	- Gradient prop (saturated regimes)
# QNA

## Bioplausible learning
- Tigerprop
	- Breaks the chain rule
	- local updates at each layer
	- [[Tigerprop]]
- Mentioned one other lab


# Initialization in DL
- [ ] Stabilizing Transformers for RL #p1 #reading 
	- [[@parisottoStabilizingTransformersReinforcement2020]]


## Sparsification of wieghts
- [ ] “Powerpropagation: A sparsity inducing weight represenation” Schwarz et al.  #reading #p3 

## Optimization v regularization

Optimizing for a “flat” minima (largest eigenvalue)
Generalizes better than a sharp minima
Need a def of flatness

## Sharpness aware minimization (SAM)
Foret et al.

## Credit Assignment


Avoid tug of war dynamics
- [ ] Schaul et al 2019 “ray interference” #rd #tp
	- Train one task and then another
	- maximize the optimization for one task, and then you can learn another
	- 


