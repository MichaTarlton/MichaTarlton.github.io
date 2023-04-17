---
type: reading
citetype: video
status: open
infotags: [video, lecture, neuromorphic, SNN]
people: Chris Eliasmith  
date: 31.01.2020
---
# https://www.youtube.com/watch?v=PeW-TN3P1hk
Description:
>Spiking neural networks (SNNs) have received little attention from the AI community, although they compute in a fundamentally different -- and more biologically inspired -- manner than standard artificial neural networks (ANNs). This can be partially explained by the lack of hardware that natively supports SNNs. However, several groups have recently released neuromorphic hardware that supports SNNs. 
>
>I will describe example SNN applications that my group has built that demonstrates superior performance on neuromorphic hardware, compared to ANNs on ANN accelerators. I will also discuss new algorithms that outperform standard RNNs (including GRUs, LSTMs, etc.) in both spiking and non-spiking applications. 
>
>**Speaker Bio:** 
>Professor Chris Eliasmith is currently Director of the Centre for Theoretical Neuroscience at the University of Waterloo and holds a Canada Research Chair in Theoretical Neuroscience. He has authored or co-authored two books and over 90 publications in philosophy, psychology, neuroscience, computer science, and engineering. His book, 'How to build a brain' (Oxford, 2013), describes the Semantic Pointer Architecture for constructing large-scale brain models. His team built what is currently the world's largest functional brain model, 'Spaun,' for which he received the coveted NSERC Polanyi Prize. In addition, he is an expert on neuromorphic computation, writing algorithms for, and designing, brain-like hardware. His team has shown state-of-the-art efficiency on neuromorphic platforms for deep learning, adaptive control, and a variety of other applications.



# Comments
## Neuromorphic advantages:
- Sparsification over time
- Less computation
	- memory lookups only when spikes recieved
- Cheaper computation
	- Sum not multiply

## Neuromorphic Development Environment (NDE)
### Nengo 
- #software
- Designed to allow deisgin of spiking networks

Used to build World’s largest brain model
- 6.6 million
- not sure where to find this, or what the name of it is,but sounds super interesting
- apparently incorporates multiple networks into one
- Shows the tool is useful for scalability

## Neuromorphic Hardware
- #hardware
- Asynch comms for speed and scaling
- Spikes for power efficiency
- Extremely Parallel, hundreds to millions of cores

###  Intel Loihi
- Research chip
- Not availiable as of date of video
- Most advanced available (Gustavo)
### Spinnaker
- Gustavo Mentioned

### Asynchronous Communication
- Neuromorphic Hardware tends to rely on async comms
- Using a global clock is expensive
- Event-Driven processing
	- computation is done when inputs arrive
- Timing information is encoded in when spike arrives


## Applications
- Adaptive Control in Robotics
	- Reacts to error on the fly
	- In this case adding a weight to a reactive arm
- Reactive, real-time applications
	- In some examples was fasterthan a cpu/gpu hardware

## LSTMs
- **Long shor-term memory**
- https://en.wikipedia.org/wiki/Long_short-term_memory

# [[Legendre Memory Unit (LMU)]]
- new RNN to optimally delay input
	- “designed from first principles”
- ideal continuous delay is infinite dimensional
- If you just want to store information over time, how do you do that?
- An optimal approximation to storing a memory, or introducng a delay to an input
- This method has performance optimizations over other LSTMs
- Also has robust spiking implementations

### [[Voelker & Eliasmith 2018]] #reading
- LTI: Linear Time Invariant system
- Pade approximants
- 

Not really catching what is going on around 30-34 min onward.


### Time Cells
- LMU appears to act similarly to time cells in the brain
- around the 36:10 mark
-  Really not understaing how they are similar other than they have a similar graph
- Not sure how they actually relatein terms on timing or data
-
### Legendre Basis
- “The legendre polynomials happento be the right way of interpreting the coefficients to reconstruct the window of time you’ve reconstructed or recorded”
- No idea what that means

### Memory capacity
- better than an LSTM
- Measured in the delay length (timesteps)

### psMNIST test
- Classify MNIST that has been randomly permutatedin a linear method
- Randomly revealed to input?

## LMU on three backends
- NengoLoihi
- NengoBraindrop
	- [[Neckar et al. 2019]] 
	- Harder to program for
- ???

# Questions
## Drawbacks
- another tool in the toolbox
- trade off is accuracy vs efficiency
	- However accuracy drop is very small
## Convolution SNN
- does exist
- spawn model
- no models he knows of that arenotimplementablein SNN
- also depends on hardware
- subtle differences
## Commercial application SNNhardware
- None in GenAI that he knows about
- However it’s been 4 years since then
- Mythos def existed back then (military)

## How to train SNNs?
- Use standard gradient descent
- some minordifferencessuch as accounting for noise
- Not doing the majority of the training on the chip itself 
- The online training is less… training?

## What do SNNs optimize for?
- optimizing for sommunication
- and event driven processing
- minimize the calculation of MACs
	- MAC : Multiply Accumulates
	- SNN just “accumulates”

## 
