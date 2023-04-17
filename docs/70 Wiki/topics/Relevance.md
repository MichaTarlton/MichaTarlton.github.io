---
aliases: [Informational Relevance,]
type: topics
status: open
priority: p4
creationtag: 2023-01-19 20:49
infotags:
---

As defined in [[@marsiliQuantifyingRelevanceLearning2022]]


On page 14

![[image-20230119205159834.png]]

Relevance is defined as:
$$
H[E]=\mathbb{E}[-\log p(E)] 
$$
where:
$$
p(E)=\sum_{s \in \mathcal{S}} p(s) \delta(E+\log p(s))=W(E) e^{-E}
$$
is the distribution of the coding cost, and $W(E)$ is the number of states with coding cost $E_{\boldsymbol{S}}=E$, that we shall call the density of states. Since $E_{\boldsymbol{S}}$ is the coding cost, the relevance $H[E]$ coincides with the entropy of the coding cost. Given that $E_S$ is a function of $s$, we have that [23]
$$
H[s]=H[E]+H[s \mid E],
$$
where $H[s \mid E]=\mathbb{E}\left[\log W\left(E_S\right)\right]$ quantifies the level of noise in the representation ${ }^{13}$.

13: For ease of exposition, we focus on the case where both $E$ and $s$ are discrete variables. When $E$ is a continuous variable, Eq. (5) yields the differential entropy of $E[23]$. Since $p(E \mid s)=\delta\left(E-E_S\right)$ is a delta function, the differential entropy of $E$ conditional on $s$ diverges to $-\infty$. This divergence can be removed if the entropy is defined with respect to a finite precision $\Delta$, as explained e.g. in [23]]. We refer to Ref. [9] for a discussion of the general case.
```query 
line:("Relevance") OR  line:("Informational Relevance") 
```