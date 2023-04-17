---
type: glossary
status: open
priority: p4
project: 
creationtag: 2022-06-13 16:40
infotags:ESN
people:
date:
---
[[Sun 2020]]

$D$ : Size of input vector U 
$T$ : Length of time-series
$N$ : size of resevoir (number of individual nodes) 

$U$: Input vector
$Y$ : Output Vector


$u(t) \in R^{D \times 1}$ 
denotes the input value at time $t$ of the time series

$x(t) \in R^{N \times 1}$ 
denotes the state of the reservoir at time $t$

$y(t) \in R^{M \times 1}$ 
denotes the output value

$W_{i n} \in R^{N \times D}$ 
represents the connection weights between the input layer and the hidden layer

$W_{r e s} \in R^{N \times N}$ 
notes the connection weights in hidden layer. 


$w^{i n}$ 
	- is an input-scaling parameter, the elements in $W_{i n}$ are commonly randomly initialized from a uniform distribution in $\left[-w^{i n}, w^{i n}\right]$

$\alpha$ 
	- is the sparsity parameter of $W_{r e s}$, denoting the proportion of non-zero elements in matrix.

$\rho\left(W_{r e s}\right)$ 
	- is the spectral radius parameter (the largest eigenvalue in absolute value) of $W_{r e s} . W_{\text {res }}$ initialize from a matrix $W$, where the elements of $W$ are generated randomly in $[-1,1]$ and $\lambda_{\max }(W)$ is the largest eigenvalue.
$$
W_{r e s}=\rho\left(W_{r e s}\right) \cdot \frac{W}{\lambda_{\max }(W)}
$$

STM : Short-Term Memory (STM)

MC : Memory Capacity

$\hat{W}$ : updated W

 