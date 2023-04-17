---
type: lecture
status: open
priority: p4
project: deeplearn2022
creationtag: 2022-07-25 09:56
infotags:
people: [sean meyn]
date:
---

- [ ] He has a book🛫 2022-07-25 #reading #p4 


# Part 1


![[image-20220725100119948.png]]


![[image-20220725100241376.png]]

- [ ] going to get into “actor only methods” #topics 

# Optimization
Trying to find an objective boils down to a “root finding problem"”
- [ ] root finding problem #topics #p4

Doesn’t like doing random descent

![[image-20220725100601000.png]]


![[image-20220725100805960.png]]

![[image-20220725100818945.png]]



# Root Finding
No one understands why Q-learning works so well

![[image-20220725101235317.png]]



# ODE method
- What is a stationary point but a root
- Euler approx is robust to measurement error
- Caveat, robust if f is globally lipschitz continuous

![[image-20220725101419646.png]]



- Take away here are that these methods are slow

![[image-20220725101720369.png]]
![[image-20220725101745825.png]]



![[image-20220725101858451.png]]


# Quasi-stochastic Exploration (exploration wout noise?)
**Ok so I think our goal / point to all this is to quickly arrive at some gradient with limited (filtered) exploration?**
- Control problems are deterministic in AI-gym

![[image-20220725102128862.png]]


![[image-20220725102231872.png]]




[[image-20220725102434458.png]]
![[image-20220725102701954.png]]
- $a_t$ is a gain?
- $\rho$ can be less than 1/2 but it doesn’t work?
	- What is rho? a bound?
- 

![[image-20220725102905390.png]]
![[image-20220725102926622.png]]

- [ ] Lipschitz continuous #topics #p3
- $\alpha$ is  a *lipschitz contant*




![[image-20220725103521472.png]]


- System is attenuated by gamma squared according to the differential?

## Conclusion (to above slide)
The difference between theta t and theta starred is almost computable

![[image-20220725103720079.png]]

- [ ]  Polyak-Ruppert Averaging #topics #p4

# Design in Action

![[image-20220725104047608.png]]


[**Missing Slide**]

- [ ] 1SPSA #topics
- [ ] 1qSGD #topics


![[image-20220725104457004.png]]


![[image-20220725104720186.png]]




![[image-20220725104940612.png]]


- [ ] Ackley Objective #topics 
	-  testing function
	- fucked up pitted surface to try getting tested algo stuck in local minima



[Missing Slide (?)]

![[image-20220725105156572.png]]



- [ ] Traveling Camel #topics
	- Another testing method 

[[image-20220725105519237.png]]
![[image-20220725105609567.png]]
- There was something here when he asked a question
- Probably something to do with the possible problems that arise (see the warning)


# Conclusions
![[image-20220725105827792.png]]


# QnA
- Q. Give an example
	- A. Going to give us exhaustive examples tomorrow
- Q. Reduce gain parameter when close to objective, but how do you know?
	- A. He’s filibustering
	- I didn’t catch what his actual answer 
	- Pedro added, that it may be because we are assuming the surface is globally stable
	- r. not claiming it is universally capable
- I should go back and see what influences the vanishing gain
- Q. Vanishing gain is polynomial, will it not be so good if an exponential function?
	- A. I didn’t catch the answer here
- Q. For Q-learning you always use ?? learning, amy reason you don’t use other learning (Ruger-kuta, ??)
	- A. Let me get back to the answer
	- the question is hard to answer because it starts out in discreet time and then… (I’m lost)
- Q. What kind of exploration can you do in a discreet space
	- A. 
- Q. Didn’t understand why emphasis on Lipschitz continuity