

---
type: topics
status: open
priority: p4
creationtag: 2022-05-08 15:58
infotags:
---

## LSTM
*[[Long Short-Term Memory (LSTM)]]* I think
> [18] Sepp Hochreiter and Jürgen Schmidhuber. Long short-term memory. Neural computation, 9(8):1735–1780, 1997.
![[50 Reading/citations/@voelkerLegendreMemoryUnits2019.md#^msenuo]]




## Exploding/Vanishing Gradients #topic  
	- Yoshua Bengio, Patrice Simard, Paolo Frasconi, et al. Learning long-term dependencies with gradient descent is difficult. IEEE Transactions on Neural Networks, 5(2):157–166, 1994.

 ## Saturating Units #topics 

## Delay Network #topics 
- [38] Aaron R. Voelker and Chris Eliasmith. Improving spiking dynamical networks: Accurate delays, higher-order synapses, and time cells. Neural computation, 30(3):569–609, 2018.

 ## [[Padé approximants]] #p2 #topics 
 - [37] Aaron R. Voelker. Dynamical Systems in Spiking Neuromorphic Hardware. Phd thesis, University of Waterloo, 2019. URL http://hdl.handle.net/10012/14625.
		- Added to zotero

## Discretization methods
- Tian Qi Chen, Yulia Rubanova, Jesse Bettencourt, and David K Duvenaud. Neural ordinary differential equations. In Advances in Neural Information Processing Systems, pages 6571–6583, 2018.
 
 ### zero-order hold (ZOH)
 - Some sort of discretization method which they do not expand on
 - But I believe the reference above will explain it

## Shifted Legendre polynomial
- Wtf is this 
- Looks like just means the phase is doubled for each degree 
- 
- Yeah so if going off Fig 1 
	- d = 1, means one rotation (full $2 \pi$) within the window (size of window demonstrated as from 0 to 1, but essentially it’s dimensionless)
	- And this continues where the phase is increased at $d \times 2 \pi$
	- So then the shifted polynomial  $\mathcal{P}_{i}(r)$ 
		- the $i^{\text {th }}$ shifted Legendre polynomial
		- I don’t know what r is here but I assume it’s just some real number
		- Appears to be found anywhere between -1 to +1
	- **I’m not certain what this means still**
	- 
>
! [[Pasted image 20220508172847.png]]

## NRU
[7] Sarath Chandar, Chinnadhurai Sankar, Eugene Vorontsov, Samira Ebrahimi Kahou, and Yoshua Ben-gio. Towards non-saturating recurrent units for modelling long-term dependencies. arXiv preprint
arXiv:1902.06704, 2019.

## Hidden state

##  Learned kernels
[[Kernel]]
the kernels (W) learn to compute nonlinear functions across the memory, while the encoders (e) learn to project the relevant information into the memory. 

## Xavier normal
- [15] Xavier Glorot and Yoshua Bengio. Understanding the difficulty of training deep feedforward neural networks. In Proceedings of the Thirteenth International Conference on Artificial Intelligence andStatistics, pages 249–256, 2010
## LeCun uniform 
- [23] Yann A LeCun, Léon Bottou, Genevieve B Orr, and Klaus-Robert Müller. Efficient backprop. In Neural networks: Tricks of the trade, pages 9–48. Springer, 2012.
## [[ADAM Optimizer]]
- Diederik P Kingma and Jimmy Ba. Adam: A method for stochastic optimization. arXiv preprint arXiv:1412.6980, 2014.
## Poisson neurons
- pretty sure just neurons that fire with a poison distribution
	- In time or in voltage?
	- I guess if at every time step you took Poisson probability of some voltage, then most of the time it would be 0 and then depending on how you distribute it, it would be “spiking” when it did hit the probability mass
	- They mention them as “stateless”
		- So I presume this means they don’t...huh I don’t think that’s it
		- 
		- 