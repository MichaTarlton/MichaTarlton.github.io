---
aliases:
type: topics
status: open
priority: p4
creationtag: 2022-10-19 15:24
infotags:
---
As mentioned in [[Neuromatch Tutorials]] for [[Wilson-Cowan rate model]]
> An important concept in the phase plane analysis is the "nullcline" which is defined as the set of points in the phase plane where the activity of one population (but not necessarily the other) does not change.

> In other words, the $E$ and $I$ nullclines of Equation $(1)$ are defined as the points where $\displaystyle{\frac{dr_E}{dt}}=0$, for the excitatory nullcline, or $\displaystyle\frac{dr_I}{dt}=0$ for the inhibitory nullcline. That is:
> $$
\begin{align}
-r_E + F_E(w_{EE}r_E -w_{EI}r_I + I^{\text{ext}}_E;a_E,\theta_E) &= 0 \qquad (2)\\[1mm]

-r_I + F_I(w_{IE}r_E -w_{II}r_I + I^{\text{ext}}_I;a_I,\theta_I) &= 0 \qquad (3)
\end{align} $$

Rate increases with excitatory conditions
And decreases for inhibitory conditions

How the activity in the phase plane will flow?





```query 
line:("Nullcline")
```