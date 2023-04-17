---
type: lecture
status: open
priority: p4
project: MLSS^N 2022 Krakow
creationtag: 2022-07-01 13:14
infotags: [DL, neuro, deepmind]
people: "Grabaska-Barwinska"
date:
---

# A rapid and efficient learning rule

# DL in brain

![[image-20220701132223473.png]]



# typical neuron ReLU

![[image-20220701132329552.png]]




# How do brains learn

![[image-20220701132448158.png]] ![[image-20220701132507376.png]]

- Temporal difference learning was found in the brain?
- The dabney paper expands on this
- 

![[image-20220701133534703.png]]

- we’ll be tallking about supervised learning today
- 


#  Learning via Grad Desc
![[image-20220701134058033.png]]


![[image-20220701134025611.png]]
![[image-20220701134300054.png]]
![[image-20220701134455993.png]]
![[image-20220701135054503.png]]

There was a good question here but I spaced out
No representation learning

Good online learner, because the local learning

Approximating dense connections

Didn’t want to multiplex
- fuck spaced out here too

How much inductive bias occurs from adding layers?
- “output will be smoother as you add layers”

# GLN
![[image-20220701140733847.png]]

![[image-20220701140851533.png]]

![[image-20220701140932382.png]]
Blue: single input scalar


![[image-20220701141012671.png]]

Depending on where the input falls in this space decides…

![[image-20220701141049832.png]]


![[image-20220701141344767.png]]

single input is a single dot

![[image-20220701141516529.png]]

this was animated


![[image-20220701141533145.png]]

![[image-20220701141553056.png]]

Sparseness is required from a bio perspective?


# Dendritic Gated Neurons
![[image-20220701141727520.png]]


![[image-20220701141818532.png]]

![[image-20220701141909933.png]]
Gates are binary 
tried softgates which were no binary and they worked as well
Inputs control gates at each layer

They do not train the gates

Compression language fields?

![[image-20220701143001082.png]]

![[image-20220701143135925.png]]

![[image-20220701143156386.png]]


![[image-20220701143045028.png]]

Animation here but it was asynchronous

![[image-20220701143256970.png]]

![[image-20220701143304370.png]]
![[image-20220701143340585.png]]


also animated


![[image-20220701143414990.png]]


![[image-20220701143944871.png]]

# Biological aspect
![[image-20220701144246923.png]]
![[image-20220701144345925.png]]

![[image-20220701144443866.png]]

![[image-20220701144516908.png]]
![[image-20220701144618722.png]]
![[image-20220701144646535.png]]

![[image-20220701144659115.png]]

![[image-20220701145028011.png]]




















# #reading
- [ ] Dabney et al. 2020 Nature #dopamine #rl #reading #p3 
- [ ] Banino et al 2018 Nature grid cells in navigating RL agents #reading #p3 #rl 
- [ ] Lillicrap, TP et al 2020 #reading #credit #p3
- [ ]  Veness et al (2017; 2021) #reading #GLN #p3
- [ ] Clark, Abbott, Chung, 2021 #reading #GLN #fish #p4

# #Topics 
- [ ] Sparse coding #topics
	- “You ask your neurons to not be active all the time”
	- 
- [ ] predictive coding (seen in previous talk) #topics
- [ ] distributional RL #topics
- [ ] Gated Linear Networks #topics
	- local plasticity/learning
- [ ] Representation Learning #topics 

# #Questions


