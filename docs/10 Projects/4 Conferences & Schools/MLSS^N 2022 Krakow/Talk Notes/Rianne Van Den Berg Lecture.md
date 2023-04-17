---
title:
type: lecture
status: open
priority: p1
project: "MLSS^N 2022 Krakow"
creationtag: 2022-08-03 16:28
infotags: [VAE, ELBO, information]
people: "Rianne Van Den Berg"
date:
---

# Materials
[MLSS^N Day 1 - 27.06.2022 - YouTube](https://youtu.be/N447XbErsGE?t=16033)
![[Deep Generative Models_compression_krakow_27_6-2022.pdf]]

# Lecture Notes
Notes were taken on my boox due to issues with laptop
This is transcribed from there


## Variational Autoencoders
- Desired Objective 
	- uses log and is thus biased in MC
	- as well as difficult
- Uses Surrogate Objective 
	- [ ] ELBO #p4 #tp
- [ ] Amortized Variational Inference #tp #tp 
- [ ] VAE Objective: Kingma ¥ Welling 2019 #rd #p4 
- z ~ q : Z sampled from q
- SO far this seems similar to Nicola’s stuff
- [ ] Cholesky Decomposition #tp #p4 
- [ ] “invertible normalizing flow” #tp #p2 
	- Øearning the “density” via the inverse
- [ ] Density Estimation using Real NVP- Dinh, Sohl-Dickstein, Bengio 2016 #rd #p1 

- DOes this give us multi-modal distribution?
	- Yes
	- Looks like several layers of it somehow

- [ ] Marginal log-likelihoods #tp #p3 
- Diffusion v. flow models?

## Compression
- ok so for the $C_0$ v. $C_2$ 
- the probability of the long codes getting used affects the “length over time” of the encoding system
- [ ] Bit probability code #tp #p4 
- Shannon entropy is how much information is in a message
	- Higher probability → less info
- Shannon Source Coding theorem #p4#tp
- Keep KL small:
$$\sum\limits_{x}P_{data}(x) \\  \log_{2} \frac{1}{P_\theta(x)}$$
$$= \sum\limits_{x}P_{data}(x) \\  \log \frac{1}{P_\theta(x)} + \sum\limits ...unfinished$$
- [ ] Entropy Coders #p4 #tp
- Enumerate 
	- What does this mean?
- [ ] Bits-Back Coding #tp
	- [ ]  Townsend et al. 2019 #rd 
	