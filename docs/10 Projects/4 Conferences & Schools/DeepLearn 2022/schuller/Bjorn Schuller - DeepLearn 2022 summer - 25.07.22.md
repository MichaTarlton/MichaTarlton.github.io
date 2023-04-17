---
type: lecture
status: open
priority: p4
project: deeplearn2022
creationtag: 2022-07-25 11:47
infotags:
people: [bjorn schuller]
date:
---

# Motivations
- To create God and bring about the end of the world 
- Autism recognition in rats is apparently a thing


# Previous Works
- combining RNN and CNNs
- Deep Recurrent Music Writer 2017
	- I need to learn how LSTMs work
- Emotional Intensity control for emotional voice conversation 2022


# Network topology
![[image-20220725121956832.png]]

# Optimizers
## Adam Adaptive Moment Estimation
- [ ] Adam Adaptive Moment Estimation #p3 #topics 
	- Calculates adaptive learning rate from first and second moments of the gradient
	- ADAM-W
	- See [[ADAM Optimizer]]
## 

# RNNs

![[image-20220725122958670.png]]


![[image-20220725123144623.png]]

- Same fnc and same parameters are used at every step

![[image-20220725123250830.png]]

- Hopfield networks are synonymous with a fully connected network

![[image-20220725123514893.png]]

![[image-20220725123538916.png]]


![[image-20220725123608065.png]]

- Two hidden layers 
- one forward one backward

![[image-20220725123940441.png]]


![[image-20220725124014496.png]]

![[image-20220725124106402.png]]


![[image-20220725124231081.png]]


![[image-20220725124314531.png]]

![[image-20220725124350571.png]]


![[image-20220725124406655.png]]

## LTSM
![[image-20220725124438455.png]]

![[image-20220725124551592.png]]
- Cross is forgetting?
	- stated briefly it is cross product
	
	- ![[image-20220725124841191.png|200]]


- plus is the adding of current input
- 

[**==Missing multiple slides on different types of gates==**]

![[image-20220725125111393.png]]


[missing slide Deep LTSM]
Q. How does dropout effect these 
	A. The same way it regularly does
Q. Where is the dropout layer
	A. Didn’t catch the answer
Q. Can we swap out transformers with more complex LTSMs
	A. 

![[image-20220725125736822.png]]

![[image-20220725125837183.png]]

![[image-20220725125933873.png]]


![[image-20220725130027956.png]]

## GRU
![[image-20220725130108748.png]]

- More lean and efficient

![[image-20220725130213762.png]]

- Wait he just said we have the slides…

## RNN with Attention


## Connectionist Temporal Classification (p186)
Using the provided slides now [[Schuller.pdf]]
Picking back up at p186

### Forward-Backward computation
Why are we doing this logic game
Looks like we plug in the probability of the forward pass $\alpha$ and the backward pass $\beta$ into the CTC loss function (looks like a Bayesian likelihood fnc)

## CTC decoding (p.200)
Where are we pulling these probabilities from?
Assuming some sort of NLP model
So we are saying the probabilities of these “chunks” of language (that’s the word they use in the transformer paper)

# Regularization
Skipped attention

## Mini-Batch Learning – Key Terminology
– Batch size
	• The number of training data points in each mini batch
		– Large enough to give good estimate of gradient
		– Small enough to provide suitable noise into updates
– Number of batches
	• The total number of mini-batches in the training data
– Epoch
	• One epoch consists of one full pass of training over the dataset.
	• One epoch would consist of $n$ number of (forward pass + backpropagation) where $n$ denotes the number of batches.


## Weight Penalties

## Augmentation

## Training with noise

## Dropout 
- [ ] Dropout #tp
- Method for training a ensemble of slightly different networks and averaging them
- Underlying concept:
	• Although it’s likely that large, unregularized neural networks will overfit to noise, it’s unlikely they will overfit to the same noise
		– I.e. they will make slightly different mistakes
	• Averaging will cancel out the differing mistakes revealing what they all learned in common: the signal properties
- The ensemble of subnetworks is formed by randomly removing nonoutput units during training
![[image-20220725182427321.png|300]]

![[image-20220725182507166.png|300]]

Q. RNN block drop outs for time blocks?
	A. from audience: tensorflow offers some sort of dropout for RNNs

# End-to-End (p.228)
Putting the different steps together
## Noise
Doing noise extraction in audio
Inspired [[Desire feauture extraction  - 25.07.22]]
- [ ] ConcealNet: An End-to-end Neural Network for Packet Loss Concealment in Deep Speech Emotion Recognition”, arXiv, 2020. #reading #p5
- [ ] Affect Recognition by Bridging the Gap between End-2-End Deep Learning and Conventional Features”, ICASSP, 2018. #reading #p5 
- [ ] “Multi-task Deep Neural Network with Shared Hidden Layers: Breaking down the Wall between Emotion Representations”, ICASSP, 2017. #reading #p5 #multi-task

Q. avoiding forgetting in multi-task learning
	A.  We’ll get to that


# Transfer Learning (p.243)
- [ ] Autoencoder-based Unsupervised Domain Adaptation for Speech Emotion Recognition”, IEEE Signal Processing Letters, 2014. #rd #p5 

How is he “taking two trained networks and then ‘overlapping them on each other’ ?!”

## Audio to images
- [ ] “Snore sound classification using image-based deep spectrum features", Interspeech, 2017. #rd #p5 
- This is for spectograms though
- [ ] “LiRA: Learning Visual Speech Representations from Audio through Self-supervision”, submitted #rd #p5

Q. Can you convert the audio to an image with this
A.  They didn’t do that. Also he wanted this for nfts? - __ -

# Self-Supervision (p.255)
- [ ] “Audio Self-supervised Learning: A Survey”, arXiv.org, 2022. #rd #p5 
- [ ] “Dawn of the Transformer Era in Speech Emotion Recognition: Closing the Valence Gap”, arXiv.org, 2022 #rd #p5 

MSP-podcast dataset
- really want to know how this was built


Q. Ok so asking about how it was able to pick up things that wouldn’t be strictly conveyed in the lip movements. I.e. The same voice, accents, gender.

A. To my question about the accent he said that it had been trained on a dataset of BBC talking heads, these were also more accurate sounding than the other examples (imo) so I’m assuming it may have been slightly fitted to that set. Also someone else brought up gender, to which obviously the model is pulling more from the images than lip movements

# DRL (p.280)


---
# Day 2
# DRL (p.301)
## Situation Sets 
- [ ] Situation Sets #tp #p3 
• Situation Variables often handcrafted
	– Subjective selection of features
	– Only applicable to one task
• Situation Variables based on sensory input
– Pre-processing necessary (high dimensionality)
– Applicable to multiple tasks
– E.g. computer game: pixels of screen
– Often used in Deep Reinforcement Learning (DRL)

## Evolving Learning
![[image-20220726142305161.png]]

- [ ]  Zhang, Z., Han, J., Qian, K. and Schuller, B.W., 2018. Evolving Learning for Analysing Mood-Related Infant Vocalisation. In Interspeech (pp. 142-146). #rd #p3 🛫 2022-07-26 #vicente 
How is the child network defined here?
I’m not understanding what it is training on
“specified by hyper params”?
Does the child net already know “the answer”

Children network does not maintain knowledge between one task to the next

Yeah what does hyper-parameters mean here? #q 
Has to mean something about the meta

# Green (p.362)
Process and data parallelisation
![[image-20220726143417468.png]]


# Compressing DNNs [missing slides]
Apparently added into the green section? or somewhere inbt 363-364

## Quantization


## Teacher student networks
How is this different from the evolving learning?

Student has access to some of the layers of the main network

## Lottery Ticket Hypothesis [missing] #tp 
Does it in

## Semi- Supervised (SS)

## Assisted Learning (?) (AL?)

## Cooperative Learning

## Federated Data

# Fairness
- [ ] Related to my idea of anti-bias in a bias machine.🛫 2022-07-26 
- [ ] “Normalise for Fairness: A Simple Normalisation Technique for Fairness in Regression Machine Learning Problems”, arXiv, 2022.  #rd #p5 #vicente 
![[image-20220726150544209.png]]

Q. How to prevent over-representation of small classes
A. dunno

# Hacks
Attaching an autoencoder and then comparing a new dataset (take euclidean distance) from the output of the trained autoencoder (on first dataset). I think this is what he said anyway.
- [ ] “Reconstruction-error-based Learning for Continuous Emotion Recognition in Speech”, IEEE ICASSP, 2017 #rd #p5 #vicente 

# Multimodal Fusion
Mutiple datatypes? Combined features?

- [ ] “Personalized Machine Learning for Robot Perception of Affect and Engagement in Autism Therapy”, Science Robotics, 2019.🛫 2022-07-26 #rd #p5 #vicente

# GANs and VAE (p.328) [missing slides]

- [ ] Jing Han, et al., Adversarial Training in Affective Computing and Sentiment Analysis: Recent Advances and Perspectives, IEEE Computational Intelligence Magazine, 2018 #rd #p4 

## VAEs [missing]

VAE-GANs are a thing 
Hope he uploads these slides
[What The Heck Are VAE-GANs?. Yep, you read the title correctly… | by Enoch Kan | Towards Data Science](https://towardsdatascience.com/what-the-heck-are-vae-gans-17b86023588a)


