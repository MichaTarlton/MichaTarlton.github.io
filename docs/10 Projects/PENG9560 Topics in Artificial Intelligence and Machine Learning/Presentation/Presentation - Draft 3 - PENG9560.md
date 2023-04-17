---
type: presentation
status: active
priority: p4
project: PENG9560/presentation
creationtag: 2023-02-06 16:55
infotags:
people:
date:
---
Note: To use navigate to http://localhost:3001/#/ , you can press ‘S’ to bring up the speaker view in the browser

---

##### **Deep Reinforcement Learning with Spiking Q-Learning**
**[[@chenDeepReinforcementLearning2022|Chen et al. 2022]]**

Presented by Mike

---
#### Reinforcement Learning (RL)
![[image-20230206213649621.png]]

- Reinforcement Learning is a type of Machine Learning which assumes some agent in an environment
- This agent has at its disposal, a set of actions it can take
- The actions the agent takes in response to its environment, in turn elicits a reward
- The goal of the system is to maximize the reward gained from the environment by optimal mapping of environment to action
- A typical example is a mouse as an agent navigating a two-dimensional grid to navigate towards some cheese
	- The action set is to move left, right, up, down
	- The optimal combination of those actions will lead him to a reward
- We call this mapping of state space to action space a Q-policy
- 

---

#### Q-Learning
- There are multiple methods of how this policy can be trained for
- The training function seeks to balance a trade-off between reward-maximization and exploration
	- Where an $\epsilon$-greedy policy, will choose an action offering the highest reward
- After training we have an optimal Q-function, and **an optimal policy** since we **know for each state what is the best action to take.**
- This is  a “tabular method”
- For a _Q-Function_, there is internally is a **Q-table that contains all the state-action pair values.**
- Given a state and action, our Q-Function **will search into its Q-table the corresponding value.**
- This comes with it the curse of dimensionality, where as our environment or set of action options increase, our solution space of Q-policies increase exponentially expensive
- This problem expands in continuous environmental and action spaces where there is no discrete mappings
 
 An example SARSA $Q(S_t, A_t)$ **learning formula for time displacement:**
 ![[image-20221216173046858.png]]

---
#### Deep RL (DRL)
![[image-20230110165707092.png]]
- We can sidestep the shallowness of our RL model space by turning to a Deep neural network to approximate our Q-policies 
- Instead of a lookup table we have the mappings embedded in high dimensional network state
- In the example here we can see an architecture where Space Invaders is preprocessed through a series of convolutional layers to compress the environment input space
	- Before being put through fully connected layers which eventually map to the outputs
	- The output with the highest output (corresponding to the Q-values) is chosen as the next action
- These are trained in two phases, 
	- through a sampling step, where actions and resulting environment
	- And training, where a gradient descent update step is performed on the samples

---
#### Spiking DRL
![[image-20230206180252880.png|500]]


- Spiking neural networks are models which utilize the neurological means of communication, spikes
- SNNs have their own benefits, namely their study contributes to neuromorphics and computational neuroscience
- Neurological models, which are necessarily deep and reinforcement trained, can possibly have their properties exploited for better DRL models
- However, training a Deep SNN comes with the problem of *Credit Assignment*
	- We can’t use Back-Propagation Through Time in RL
	- Typically because it is “Online”
- Instead surrogate methods such as [[Surrogate Gradient Learning]] and [[e-prop]] are used


---
#### Deep Reinforcement Learning with Spiking Q-Learning - Chen et al. 2022
- This bring us to Chen et al. 2022
- This paper implements spiking neurons in a DQN


---

#### DSQN Network Architecture
![[image-20230206180358619.png|500]]
- Like the Deep Q-Network, DSQN relies on a series of layers of convolutional layers before passing to a series of fully connected layers
- The architecture of DSQN consists of synaptic layers and neuronal layers
- The synaptic layers include the convolutional and fully-connected (FC) layers
- each of which is followed by a neuronal layer

- As before, the Atari game is fed into the input layer, and actions are read out from the output layer
- This comes with the added constraint of needing to convert the inputs to spikes and then on the output, convert back to a readable output

- DSQN employs a similar network structure to ( DQN from Mnih et al. 2015)  (i.e., Input-32C8S4-LIF-64C4S2-LIF-64C3S1-LIF-Flatten-512-LIF-NA-LI), where NA is the number of actions used in the task). 
- For Atari games, the ANN used in DQN [14] contains 3 convolutional layers and 2 FC layers (i.e., Input-32C8S4ReLU-64C4S2-ReLU-64C3S1-ReLU-Flatten-512-ReLU-NA

---
#### I/O Conversion

![[image-20230206180428674.png]]

- Except that the Leaky Integrate layer is used after the last FC layer
- The other synaptic layers are followed by LIF layers

- The first layer acts as a learnable spike encoder to convert the static state into the corresponding spike-train
- According to the definition of SNN, the output is a spiketrain, but the results of value estimation used in RL are continuous values.
- To bridge the difference between these two data forms, we need a spike decoder to complete the data conversion, that is non-spiking neurons. 

- To do this a layer of non-spiking neurons (Leaky-Integrate) reads the input current of upstream neurons
- The membrane voltage of this layer of non-spiking neurons is read-out as the probability of taking the corresponding action, corresponding to the Q-value 
	- In the whole simulation time T , the non-spiking neurons take the spike-train as the input sequence, and then the membrane voltage Vt at each time-step t can be obtained. 
- To represent the output of value function, we need to choose an optimal statistic according to the membrane voltage at all times.
---
#### Measurable Statistics
- The paper addresses what measurement of the voltage on the readout layer should correspond to Q-value
- They offer three (see below)
- They find that the “Max-Mem” is best performing

##### Last membrane voltage (last-mem):
 It is a natural idea to use the last membrane voltage after the simulation time as the characterization of the Q-value $\left(Q=V_T\right)$.

##### Maximum membrane voltage (max-mem):
 By recording the membrane voltage of non-spiking neurons at each time-step in the whole simulation time, we can get the maximum membrane voltage $(Q=$ $\max _{1 \leq t \leq T} V_t$ ).

##### Mean membrane voltage (mean-mem):
 Similar to the maximum membrane voltage, we can obtain the mean value by collecting the membrane voltage data, which is also a meaningful statistic $\left(Q=\frac{1}{T} \sum_{t=1}^T V_t\right)$.

![[image-20230207095844015.png]]


---
####  Neuron Models (LIF & LI)
![[image-20230206180332067.png|500]]


##### Leaky Integrate and Fire (LIF) (Spiking)
The function $f(\cdot)$ of the LIF neuron is defined as:
$$
f\left(V_{t-1}, X_t\right)=V_{t-1}+\frac{1}{\tau}\left(-\left(V_{t-1}-V_{\text {reset }}\right)+X_t\right),
$$
where
- $\tau$ is the [[Membrane Time Constant]]. 
- $\Theta(x)$ is the Heaviside step function,
	- The spike generative function 
		- which is defined by 
		- $\Theta(x)=1$ for $x \geq 0$
		- and $\Theta(x)=0$ for $x<0$. 
		- Note that $V_0=V_{\text {reset }}$


##### Leaky Integrate (LI) (Non-Spiking)
The dynamics of LI neurons is described as the following equation:
$$
V_t=V_{t-1}+\frac{1}{\tau}\left(-\left(V_{t-1}-V_{\text {reset }}\right)+X_t\right) .
$$



---
#### Testing
##### Atari games
- DSQN v. DQN
	- DQN is a non-spiking model
- Tested 17 Atari games against the DQN model from Mnih et al. 2015
- Appears to perform better, learning with fewer timesteps
- But what is more important than that is that the results are comparable, in a lower cost SNN

![[image-20230207091726162.png]]


---



#### Questions
- This doesn’t seem like it would be able to perform well in an “online” setting
- They appear to calculate the gradients recursively
	- If so this can not be optimal in a live environment
- This network is also composed of normal ANN nodes in the inter-layers, and is not fully spiking
- It would be more interesting to see what a network composed of fully spiking nodes would entail