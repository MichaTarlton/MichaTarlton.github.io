---
aliases: [undefined,]
type: topics
status: open
priority: p4
creationtag: 2022-05-31 13:28
infotags:
---
[[Sun 2020]]
# Gated Recurrent Unit

# Ridge Regression

# Spectral Radius Parameter
> The largest eigenvalue in absolute value

# Least Squares Problem

# [[L2-Norm]]
 $\left\|W_{\text {res }}\right\|_{2}$ 
 Check your old notes on L2 regularization
# D-Norm
$\left\|W_{\text {res }}\right\|_{D}=\bar{\sigma}\left(D W_{r e s} D^{-1}\right)$. 
Not sure what the sigma is here



# Memory Capacity
See below. used to define STM

Memory capacity $(\mathrm{MC})$ is a quantitative measure of STM.
# Short-Term Memory
See [[Long Short-Term Memory (LSTM)]]
Short-Term Memory (STM)
- denotes the memory effects connected with the transient activation dynamics of networks
- Memory capacity $(\mathrm{MC})$ is a quantitative measure of STM.
- MC is calculated by the determination coefficient of $W_{o u t}^{k}$, $$d\left[W_{o u t}^{k}\right]\left(u(n-k), y_{k}(n)\right)=\frac{c o v^{2}\left(u(n-k), u_{k}(n)\right)}{\sigma^{2}(u(n)] \sigma^{2}\left(y_{k}(n)\right)}$$
-  when training the ESN to generate at its output units delayed versions $u(n-k)$. 
- The STM capacity of the network according to MC is described in Equation 10
$$
\begin{aligned}
M C &=\sum_{k=1}^{\infty} M C_{k} \\
M C_{k} &=\max _{W_{\text {out }}^{k}} d\left[W_{\text {out }}^{k}\right]\left(u(n-k), y_{k}(n)\right)
\end{aligned}
$$


# leaky-ESN
#esn
See ESN models in this paper [[Sun 2020#2 2 1 Basic models]]


# non-periodic dynamical system

# critical echo state networks (CESN)
# principle neuron reinforcement (PNR) algorithm

# Anti-Oja’s learning (AO)
