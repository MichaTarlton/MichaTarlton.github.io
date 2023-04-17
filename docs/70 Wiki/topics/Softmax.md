---
aliases: [softmax, Softmax Classification]
type: topics
status: open
priority: p4
creationtag: 2023-01-12 15:23
infotags:
---

Same as a Boltzmann-Gibbs Distribution (essentially). The probability distribution of a state of the system over the probability of all possible states.

From Wikipedia:
> The standard (unit) softmax function $\sigma: \mathbb{R}^K \rightarrow(0,1)^K$ is defined when $K \geq 1$ by the formula
>$$\sigma(\mathbf{z})_i=\frac{e^{z_i}}{\sum_{j=1}^K e^{z_j}} \text { for } i=1, \ldots, K \text { and } \mathbf{z}=\left(z_1, \ldots, z_K\right) \in \mathbb{R}^K$$
>  In simple words, it applies the standard exponential function to each element $z_i$ of the input vector $\mathbf{z}$ and normalizes these values by dividing by the sum of all these exponentials; this normalization ensures that the sum of the components of the output vector $\sigma(\mathbf{z})$ is 1 .



# Wikipedia
<iframe src="https://www.wikiwand.com/en/Softmax_function" allow="fullscreen" allowfullscreen="" style="height:100%;width:100%; aspect-ratio: 16 / 9; "></iframe>


```query 
line:("Softmax") OR  line:("softmax") 
```