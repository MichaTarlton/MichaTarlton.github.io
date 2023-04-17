---
type: [development, results]
status: open
priority: p1
project: SBF-automata
creationtag: 2023-01-30 12:10
infotags: [code, dev, sbf, automata]
people:
date:
---
Moved off of [[SBF - Automata - Design 1]]


# Application of python implementation
- See [[Pseudocode for SBF Automata]] for a rough outline of the programmatic algorithm.
- The code has been implemented in a google colab notebook which can be viewed here: [SBF Temp Automata.ipynb - Colaboratory](https://colab.research.google.com/drive/1mC19lGwOrCA8cdEzlYdsuVc5lNUt6z8L?usp=sharing)
## Brief Description
- Code was bootstrapped so that only time-steps where reward was issued were counted
	- No negative reinforcement or time decay, so “dead” time-steps were skipped
- Used primes for elemental automata phases
	- First round used the first 25 primes
	- Second round used first 40 primes
- Reward phase was initially set to a low non-prime (33), and then to a larger prime number (173)
- The $\alpha$ and $\beta$ controlled the learning rate and decay rate, respectively
	- Alpha was initially set to $\alpha = 0.005$ and $\beta = 0.002$
- **Figures**
	- Legends show oscillator phases, sorted by weight
	- Y-axis is the weights
	- X-axis is the time-steps

## Outcomes

### Initial Batch (wrong probability)
I accidentally did these with an inverted probability. Such that $P = \frac{1}{\sum weights}$.
Actually when I do it correctly ($P = \sum w_{active}$) the outcomes look really weird. Took me a moment but I get why.
See below.
#### Round 1
- The algorithm quickly arrived at the lowest common prime (11)
##### Bootstrapped
![[image-20221128195251264.png|500]]


##### Non-Bootstrapped
![[image-20221128195053784.png|500]]


#### Round 2
- The algorithm quickly arrived at the exact oscillator 
- We can see the divergence with the non-bootstrapped figure below
##### Bootstrapped
![[image-20221128192103908.png|500]]
##### Non-Bootstrapped
![[image-20221128192448341.png|500]]


### Correct Probabilities Batch
These have a much more linear trajectory. Though they also appear to take longer to arrive a solution.
Probably because I set the probability of initials pulls too low.
Also, these are extremely zoomed out dingus. Your algorithm is not normalized.
#### Round 1 conditions
- We see a much more linear increase
- Here I have added the probabilities of the pull in the bottom half
- There also appears to be a bug where the purple ‘7’ line draws over the ‘11’ line
##### Bootstrapped
![[image-20221128202356319.png|400]]
###### Zoomed in
- We can see it exponentially takes off > 1500 time-steps
- Still learns slower than the inverted probability
	
![[image-20221128203316206.png|400]]



##### non-bootstrapped
![[image-20221128201400985.png|400]]

###### Zoomed in
![[image-20221128203722913.png|400]]









# Application of python implementation
The above model was implemented in python and tested according to the parameters outlined below. Please see the attached [[Pseudocode for SBF Automata]] for a rough outline of the programmatic algorithm. The code has been implemented in a google colab notebook which can be viewed here: [SBF Temp Automata.ipynb - Colaboratory](https://colab.research.google.com/drive/1mC19lGwOrCA8cdEzlYdsuVc5lNUt6z8L?usp=sharing)

## Brief Description
The model was bootstrapped so that only time-steps where reward was issued were counted. The basic model utilizes no negative reinforcement or time decay, so “dead” time-steps were skipped.

For the phases of the elemental automata, we used prime numbers. In the first round we used the first 25 primes and in the second round we used the first 40 primes. 

The reward phase was set to a low non-prime (33) in the first round, and then to a larger prime number (173) in the second round. The learning and decay rates, were initiaized  to $\alpha = 0.005$ and $\beta = 0.002$.

The were run in two batches as the first batch used an inverted probability ( $P = \frac{1}{\sum weights}$) for the master node, which nonetheless proved more effective at initial learning rate. 

The second batch used the correct pull probability ($P = \sum w_{active}$), however, this was slower to learn initially but exploded exponentially once it reached a particular threshold.

**Figures**
	- Legends show oscillator phases, sorted by weight
	- Y-axis is the weights
	- X-axis is the time-steps

## Outcomes
### Initial Batch (inverted probability)
#### Round 1
for the first twenty-five primes as the elementary automata cycles.
##### Bootstrapped
![[image-20221128195251264.png|500]]

##### Non-Bootstrapped
![[image-20221128195053784.png|500]]


#### Round 2
##### Bootstrapped
![[image-20221128192103908.png|500]]
##### Non-Bootstrapped
![[image-20221128192448341.png|500]]


### Correct Probabilities Batch
#### Round 1 conditions
- We see a much more linear increase
- Here I have added the probabilities of the pull in the bottom half
- There also appears to be a bug where the purple ‘7’ line draws over the ‘11’ line
##### Bootstrapped
![[image-20221128202356319.png|400]]
###### Zoomed in
- We can see it exponentially takes off > 1500 time-steps
- Still learns slower than the inverted probability
	
![[image-20221128203316206.png|400]]



##### non-bootstrapped
![[image-20221128201400985.png|400]]

###### Zoomed in
![[image-20221128203722913.png|400]]