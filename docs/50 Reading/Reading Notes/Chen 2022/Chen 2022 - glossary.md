---
type: glossary
status: open
priority: p4
project:
creationtag: 2023-02-01 17:45
infotags:
people:
date:
---

# Formulae
## Loss function (pg. 3)
### Equation 1:
$$
\begin{aligned}
L(\theta) & =\mathbb{E}_{s, a, r}\left[\left(\mathbb{E}_{s^{\prime}}[y \mid s, a]-Q(s, a ; \theta)\right)^2\right] \\
& =\mathbb{E}_{s, a, r, s^{\prime}}\left[(y-Q(s, a ; \theta))^2\right]+\mathbb{E}_{s, a, r}\left[\mathbb{V}_{s^{\prime}}[y]\right]
\end{aligned}
$$
where 
- $y=r+\gamma \max _{a^{\prime}} Q\left(s^{\prime}, a^{\prime} ; \theta^{-}\right)$. 
- $s^{\prime}$ and $a^{\prime}$ represent the observation and the action at the next time-step, 
- $\gamma$ is a discount factor and $\theta^{-}$are the weights of the target network. 
- $\mathbb{E}$ and $\mathbb{V}$ represent the expectation and the variance. 

For more details of Eq. (1) refer to DQN [14].

Differentiating the loss function with respect to the weights, we obtain the following gradient:
### Equation 2:
$$
\nabla_\theta L(\theta)=\mathbb{E}_{s, a, r, s^{\prime}}\left[(y-Q(s, a ; \theta)) \nabla_\theta Q(s, a ; \theta)\right] .
$$
==How do we set a target network if we are operating on reward?==

## Spiking Neural Model
The basic computing unit of SNN is the spiking neuron. 
### Basics (Equations 3,4,5)
The dynamics of all kinds of spiking neurons can be described as:

$$
\begin{aligned}
H_t & =f\left(V_{t-1}, X_t\right), \\
S_t & =\Theta\left(H_t-V_{t h}\right) \\
V_t & =H_t\left(1-S_t\right)+V_{\text {reset }} S_t
\end{aligned}
$$
where: 
- $H_t$ and $V_t$ denote the membrane voltage after neural dynamics and the trigger of a spike at time-step $t$, respectively. 
	- ==this doesn’t make any sense==
	- OH, like Voltage after “dynamics” and voltage after the trigger of a spike at t?
	- It’s confusingly worded
	- Wait it’s below again too
- $X_t$ denotes the external input, and 
- $S_t$ means the output spike at time-step $t$, 
	- which equals 1 if there is a spike and 0 otherwise. 
- $V_{t h}$ denotes the threshold voltage and 
- $V_{\text {reset }}$ denotes the membrane rest voltage. 

As shown in Figure 2, Eq. (3) - (5) establish a general mathematical model to describe the discrete dynamics of spiking neurons, which include charging, firing and resetting. 

Specifically, Eq. (3) describes the subthreshold dynamics, which vary with the type of neuron model
### LIF Neuron
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

### Non-spiking Neurons (equations 7 and 8)
$$
V_t=f\left(V_{t-1}, X_t\right)
$$
Here we consider the non-spiking LIF model, which can also be called Leaky Integrate (LI) model. 
The dynamics of LI neurons is described as the following equation:
$$
V_t=V_{t-1}+\frac{1}{\tau}\left(-\left(V_{t-1}-V_{\text {reset }}\right)+X_t\right) .
$$

### Statistic Candidates 

 #### Last membrane voltage (last-mem):
 It is a natural idea to use the last membrane voltage after the simulation time as the characterization of the Q-value $\left(Q=V_T\right)$.

 #### Maximum membrane voltage (max-mem):
 By recording the membrane voltage of non-spiking neurons at each time-step in the whole simulation time, we can get the maximum membrane voltage $(Q=$ $\max _{1 \leq t \leq T} V_t$ ).

 #### Mean membrane voltage (mean-mem):
 Similar to the maximum membrane voltage, we can obtain the mean value by collecting the membrane voltage data, which is also a meaningful statistic $\left(Q=\frac{1}{T} \sum_{t=1}^T V_t\right)$.


To have an intuitive understanding of the neuronal dynamics of non-spiking neurons decoded with different statistics, we conduct a case study to choose the decoder used in our methods. 

As illustrated in Figure 3, we consider a simple network as an example, which consists of a LIF neuron and a LI neuron. 

The LIF neuron receives the weighted input $X(t)=w_1 I(t)$, 
and then transmits the weighted spike signal $w_2 S(t)$ to the LI neuron. 

In this case, the input $I(t)$ is constant, and the simulation time $T$ is set to 8 . 

Furthermore, the membrane rest voltage $V_{\text {reset }}$ is set to 0 , 
and the membrane time constant $\tau$ is set to $2.0$. 

For simplification, the weights $w_1$ and $w_2$ are set to 1.0. 

In Figure 4 , we plot the functional relationship between the input current and different statistics of membrane voltage.