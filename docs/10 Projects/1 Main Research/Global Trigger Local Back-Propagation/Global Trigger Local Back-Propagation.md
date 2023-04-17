---
aliases: [GTLBP, Golden Seed]
type:  project
project: GTLBP
status: open
priority: p4
creationtag: 2022-06-14 18:58
infotags: [SNN, CAP, DRL]
---

```dataview
table rows.file.link AS "Related",
file.ctime as "Created",
infotags as "Tags"
FROM ""
WHERE contains(project,"GTLBP")
GROUP BY type
SORT file.ctime asc 
```


# Some headway made with the discussion with Leonardo

![[Gustavo and Anis quick Meeting - 14.06.22#Local BP]]

# Quick Idea
## Reading [[Mello 2016]] and the section on [[Scalar Expectancy Theory]]
Possibly my idea in relation to this is that the network or subnetwork stable state that represents a episode, elicits a neural oscillation which acts as a ***pacemaker***  in the SET framework. Or there is an integrator neurons that gives a regular pulse corresponding to the stable state, while simultaneously acting as the ***switch***. When the episode ends, and the network stable state converts to a different structure, and thus emits pulses on a different integrator neuron, this is the stop of one episode and the start of another.

The pulses from the switch/integrator neuron are issued directly to the memory-accumulator circuit.

# Local BP as in my whiteboard design ()
## Pics
![[20220614_143929.jpg|300]] ![[20220614_143934.jpg|300]] ![[20220614_143939.jpg|200]]

# Stipulations
- We use this as an approach to the [[Credit Assignment Problem]] in SNN 
- Neural oscillations, which are cause by firing rates of neuron populations, represent some stable state in the neuronal network activity


# Self-Sparsifying Behavior
The ability to sparsify a connection when the plasticity weight falls below a certain threshold
- How to dedal with “rebound”



# The Self Organized output layer
***You would still need some output and input layer***

The output layer will likely need to be fully connected, even if the rest of the watershed is sparse or architectured

I think to have this idea make sense, where you briefly have very linear in/out layers, and then a very recurrent blob in the center, or some architecture of blobs, as opposed to straightforward linear system  

# The watershed (non-reservoir) design
***A spiking LSM/ESM/Reservoir is not plastic!***

Reservoirs are not plastic

There is need for some self stabilizing, self-organizing “pool” of neurons.