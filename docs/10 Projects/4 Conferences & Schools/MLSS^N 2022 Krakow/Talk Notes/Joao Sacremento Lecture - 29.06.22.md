---
type: lecture
status: open
priority: p4
project: "MLSS^N 2022 Krakow"
creationtag: 2022-06-29 09:01
infotags: [rnn, steady state, equilibrium, dynamics]
people: "Joao Sacremento"
date:
---
# Materials
[MLSS^N Day 3 - 29.06.2022 - YouTube](https://www.youtube.com/watch?v=1eFzU_Qr1SQ&t=630s)
![[Bilevel optimization in Krakow.pdf]]

# Lecture Notes
Shall continue after this point
# Unifying theme

# Neuro and ML
- take and give between the two worlds

# Part 1
- fixed point 
- equilibrium rnns

# RNN
![[image-20220629091029656.png]]

- sigma is the activation function

$x$ - input activity vector
$\phi-$ neural state vector (spike  train sorta, the values)
$W$ - recurrent weight matrix
$U-$ input weight matrix
$\sigma$ - elementwise transfer function (activation fnc)

#  Learning optimization
![[image-20220629091352428.png]]

# SGD

![[image-20220629091458352.png]]


# Gradient

![[image-20220629091733153.png]]



- COstly proceedure
- have to store your interim steps(?)

# COnstant in time
![[image-20220629091839557.png]]


- reaches some steady state
- Dynamics go to fixed point


# Eq. RNN
![[image-20220629092006025.png]]


-  can only … at equilibirum

# FFNN as special case

- FF are contained in the rnns


# Beyond FFNs


- higher order features influence lower level processes
- Currently an interest in shallow rnns, but I think this is an optimization of FFNs
- 


#  Implicit diff
![[image-20220629093301990.png]]


- how do small changes in our parameters change our equilibrium point?
- implicit fun thm is still difficult due to invertible matrix

## Qna
ASsuming at eq 
rnn doesn’t need to be at total eq


# Recurrent BP
![[image-20220629093717285.png]]
- known for awhile
- the helper variable makes it to where you don’t need to invert, somehow…

#  Back to Eq. RNN
![[image-20220629093849956.png]]
![[image-20220629094031333.png]]

- all nodes have a backwards weight
- not functional, but instead w_{ji}
- **Static input to RNN**

# Graph Summ

![[image-20220629094106289.png]]
![[image-20220629094208959.png]]

#  Rep. in the brain
![[image-20220629094424259.png]]
- The few examples he thinks is weird
- So the thing he thinks is implausible about it in biology
- [ ] Weight Transport #topics 
	- feedback and feedforward weights are equal

# Energy-minimizing neural dynamics
![[image-20220629094807464.png]]

# Hopfield energy
![[image-20220629095059630.png]]


- using symmetric weights
	- Can’t you do a directional ising with this?
	- *”weights have to be symmetric”* for this function to work
- Strictly increasing activation fnc


# Learning as bilevel opt
![[image-20220629095238533.png]]

- hmm the Emin v lossmin sounds a little like my question about maximizing ent to energy

# Eq. Prop
![[image-20220629095352479.png]]
- $\beta$ gives control

- 
![[image-20220629095521925.png]]

 
 
 # Grad. Est.
![[image-20220629095624651.png]]

- Not sure that you can use this for time-series

# Learning Hop nets with EP
![[image-20220629095723540.png]]


# Eq. Prop in Brain
![[image-20220629095838029.png]]

- Need two phases,
	- learning phase
	- and nudge phase with teacher

# Interim Summary
![[image-20220629100036376.png]]
- Can be applied to predictive coding circuits
 
---
Switched out to Alex

# Surrogate objective
![[image-20220629100356284.png]]
![[image-20220629100434338.png]]

- minimizing surrogate objective we  minimize our original objective

![[image-20220629100515186.png]]


![[image-20220629100716833.png]]
- some sort of oracle(?)
- Control input drives your network towards the target
- Want to minimize the amount of control needed


# Insert Slide
Should be in ss folder

![[image-20220629100829941.png]]


![[image-20220629100945801.png]]

![[image-20220629100959597.png]]

![[image-20220629101107836.png]]




![[image-20220629101405149.png]]
- terminal cost is the amount control needed
- 
- Surrogate objective is the minimal amount of control

![[image-20220629101553056.png]]

![[image-20220629101656321.png]]


![[image-20220629101815930.png]]

![[image-20220629101932876.png]]

![[image-20220629102042514.png]]


![[image-20220629102349700.png]]

![[image-20220629102529374.png]]

![[image-20220629102621117.png]]

![[image-20220629102702546.png]]


# QnA
- [ ] Deep Equilibrium Networks #topics
	- Perhaps what I am trying to describe with watersheds 
- [ ] Deep Declarative networks? #topics

What does the architecture of these networks look like?
- They haven’t really checked

Did $\beta$ change? It goes to infinity now instead of being a weak nudge
- No, it’s just a little different here 
- Can’t exactly say how, but apparently it will 

---
#  Part 2: Meta Learning

## Wheel Bandit
- sample a new radius each time 
- which decides which action is optimal


## Meta learning problem
- learning across different timescales
- Slow and fast parameters
	- Slow does long term adaptation while fast does immediate adaptation
- pg 68
	- Computing the grad of min fnc
## BP thru training


## meta with bilevel
- fast params are learned to a local optima

---
hand off to 
##  Recurrent BP
pg 76. beginning at 0












# Questions

How do you ensure attractor state is at an edge of chaos for generalizability?
Is there a way to balance between energy minimization and entropy?

Can they expand on how the fast parameters inform the slow parameters?

What does a “convolutionally structured RNN” look like?

# Notes from Onyx
Re: Bilevel learning
On so they optimize the net work for energy, but what about entropy.
It sounds like they want it to fit for more subtasks and still generalize well.
They are trading off be energy and effectiveness?