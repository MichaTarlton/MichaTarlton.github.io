---
type: comments
status: open
priority: p4
creationtag: 2022-05-08 15:58
infotags:
---

Not sure what is *orthogonalized* as in the abstaract.

Abstract in general is very dense. I’ll need to unpack this whole thing


> [!Nomenclature] 
> $u(t) \in \mathbb{R}$ is the **input signal**
> 
> **$\theta$ is the sliding window**
> 
> $m$ is the **state vector** with $d$ dimensions
> - They also call it the ***memory*** or **memory vector** at points
> - d-dimensional
> 
> $\mathbf{A,B}$ is the **state-matricies**
> 
> $(\overline{\mathbf{A}}, \overline{\mathbf{B}}, \theta)$ are the parameters of the memory
> - so I’m guessing this means the recorded state, or sum of previous states through the window
> $d$ is the degree (of the Legendres?)
> $\mathcal{P}_{i}(r)$ is the $i^{\text {th }}$ shifted Legendre polynomial
> - I don’t know what r is here but I assume it’s just some real number
> 
> $\mathbf{x}_{t}$  LMU input vector
> 
> $\mathbf{h}_{t} \in \mathbb{R}^{n}$ hidden state
> 
> $\mathbf{W}_{\mathbf{x}}, \mathbf{W}_{\mathbf{h}}, \mathbf{W}_{\mathbf{m}}$ are learned kernels 
> 

What’s the difference between **state-vector** and **state-matrices**?

## Layer design
### Learned kernels
So at time $t$ we have the [[learned kernels]] $W$ (whatever that means)
We have the input vector x
the hidden state from the previous timestep $h_{t-1}$
and the previous timestep memory vector $m_{t-1}$
each scaled against some respective learning kernels


> The parameters of the memory $(\overline{\mathbf{A}}, \overline{\mathbf{B}}, \theta)$ may be trained to adapt their time-scales by backpropagating through the ODE solver [9], although we do not require this in our experiments.

Not sure what is meant by this

> The time-scale $\theta$ is initialized based on prior knowledge of the task.

What do they decide on?
They must explain it in the methods I’m sure


![[50 Reading/citations/@voelkerLegendreMemoryUnits2019.md#^h713nh]]
So the weights are just set instead of trained.



## Memory 
See [[50 Reading/citations/@voelkerLegendreMemoryUnits2019#Parameter-State Trade-offs]]
There appears to be som trade off to *linear memory* vs other parameters and complexity.


## ![[How to read fig 2 (quick conversation with Gustavo about LMUs)]]