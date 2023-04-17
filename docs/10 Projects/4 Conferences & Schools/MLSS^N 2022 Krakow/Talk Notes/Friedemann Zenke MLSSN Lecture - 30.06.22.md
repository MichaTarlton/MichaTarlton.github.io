---
type: lecture
status: open
priority: p4
project: MLSSN
creationtag: 2022-06-30 13:12
infotags: [MLSS, snn]
people: "Friedemann Zenke"
date:
---

# Lecture Material
[MLSS^N Day 4 - 30.06.2022 - YouTube](https://youtu.be/ZV362uRi67o?t=15077)
![[spiking_nets_MLSS_web_v1.pdf]]
# Notes

![[image-20220630131919137.png]]

# Combinatorial
![[image-20220630132104184.png]]


# Fncl configs
![[image-20220630132259422.png]]

# end to end opt
![[image-20220630132435375.png]]

![[image-20220630132605327.png]]


- IT sites rely on multiple neurons
- HMO layers correspond to multiple variations

# Deep nets
![[image-20220630132851473.png]]


# SNN
![[image-20220630133001791.png]]


# Today
![[image-20220630133026229.png]]

# LIF
![[image-20220630133305281.png]]


# APs

![[image-20220630133418348.png]]



# Bio to reduced models
![[image-20220630133603952.png]]



# Linear integration 
![[image-20220630133652672.png]]


# LIF

![[image-20220630133737958.png]]

![[image-20220630133811397.png]]

![[image-20220630133843774.png]]


- What are the time constants
- subseconds

# Spike response
![[image-20220630134131634.png]]


- not an integral there as it  is ….unintelligible
- something about the pspkernel
- easier to do 


# Toward task opt plausible models
- So taking the approach we are doing like we were doing for ML

#  Input
- cell encoding feel of different structures
- recorded output of retina ganglion cells
- [ ] Cramer et al 2020 #reading #snn

# realistic input extractions
- art cochlear model

# spatiotemp spike patt
## input
- feeling with whiskers


## out
- two cells, lif, 

![[image-20220630135003867.png]]

# Reaing snn end to end
![[image-20220630135159832.png]]
![[image-20220630135220870.png]]



- [ ] Neftci, Mostafa, zenke 2019 #reading #snn 

- implicit

# Example
![[image-20220630135410009.png]]


- spike is basically heaviside
- So derivative is 0 most of the time, infinite at spike
- want to smooth out
- Several possible solutions

Surrogate gradients are known by many names in lit
![[image-20220630135539795.png]]

# loss landscape
![[image-20220630135636412.png]]


![[image-20220630135701737.png]]

![[image-20220630135732701.png]]

![[image-20220630140018650.png]]





- Whenever they encounter the heaviside 
- 

![[image-20220630140031978.png]]


Q: Why have two output neurons? Because you can’t really get a readable out put from that
A: He misdrew 10

![[image-20220630140207676.png]]

![[image-20220630140215545.png]]

# Initialization
![[image-20220630140302562.png]]



# Fluctuations in brain
- Using neural features for learning
- [ ] Firing Rate Homeostasis #topics #p2 #snn
![[image-20220630140928756.png]]


# Application and motivation
![[image-20220630141117653.png]]



#  Neuromorphic Engineering
## Problem of device mismatch
- Hardware module and software emulation can be problematic
![[image-20220630141436272.png]]

![[image-20220630141508825.png]]

## Fncl snn on analog HW
![[image-20220630141536896.png]]


# in the loop surr grad train
![[image-20220630141728135.png]]
 passing learning parameters back to pytorch
 
Cites [[@cramerSurrogateGradientsAnalog2022]]

learns mnist very fast, sub 12ms

![[image-20220630141908302.png]]



comparable accuracy to digital pc

![[image-20220630142112527.png]]

Q: using one device as a teaching  device for another
A: yeah totally possible

Q: Having a NN in a chip for single-task or for



# Surrogate gradient learning self-calibrates…
Decalibration : added noise
Smart negative feedback for a self correcting system in the hardware design


# Plasticity
Moving to local learning rules, avoiding BPTT
- [ ] Real time recurrent learning #topics #snn #p1 
	- Goes the other direction and not as accurate
![[image-20220630143352439.png]]


- [ ] Marschall, Cho, Savin 2019 #reading #snn #p1 
![[image-20220630143540988.png]]

Sparser, sparser jacobian, easier calc


![[image-20220630143611995.png]]


 elgibility traces
 feedback term

![[image-20220630143641138.png]]




# Question s
- [ ] PSP Kernel #topics #p1 
- Implicit v explicit recurrence?
































