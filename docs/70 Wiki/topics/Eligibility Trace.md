---
type: topics
status: open
priority: p4
creationtag: 2022-05-04 15:15
infotags: [SNN]
---
# Commentary
Ok so per below quote from
[[@vasilakiSpikeBasedReinforcementLearning2009|E. Vasilaki, N. Frémaux, R. Urbanczik, W. Senn, W. Gerstner (2009)]]
I’m thinking that Eligibility traces are just that, scoring the eligibility (or possible amount of influence) a presynapse can have to change a weight on the post-synapse

> The term $e_{i j}$, called eligibility trace, picks up the correlations between pre- and postsynaptic activity just as in a Hebbian learning rule and convolves these with a low-pass filter $\gamma$. 
> 
> However, the final weight change is implemented only in the presence of a reward signal $R-b$ which is delivered at the time $t_{\text {hit }}$ when the animal hits the target. 

> The eligibility trace of the synapse from $j$ to $i$ is updated by a finite positive amount whenever a postsynaptic action potential occurs within the time span of an [[Excitatory - Inhibitory postsynaptic potential (EPSP) - (IPSP)|EPSP]] at this synapse.
> 
> Hence the eligibility trace picks up (potentially causal) correlations between presynaptic spike arrival and postsynaptic spike firing. If an EPSP occurs without a postsynaptic spike, the eligibility trace decays smoothly at a rate proportional to $\rho_i /\left[1+\tau_c \rho_i\right]$. 

# Extracts
## [[@fremauxNeuromodulatedSpikeTimingDependentPlasticity2016|N. Frémaux, W. Gerstner (2016)]]
> Suppose a presynaptic neuron sends a spike train "pre" to a postsynaptic neuron with spike train "post." Similar to Hebbian learning the synapse will form a transient memory of coincidences between pre- and postsynaptic spikes. 
> 
> This transient memory, called the "eligibility trace" in the theoretical literature and "tag" in the experimental literature, decays over a time scale $\tau_e$. While the transient memory persists, the synapse is marked and therefore eligible for changes later on (Figure 4A). 
> 
> The actual change of the synapse, however, requires in addition a neuromodulatory signal $M$ (Crow, 1968). Conceptually, the neuromodulator could target a specific subset of synapses, or a large, but random fraction of synapses in the brain. We emphasize, that even if the anatomical branching patterns are unspecific, only the synapses which have been previously marked by the eligibility trace will be changed (Figure 4B).

## [[Gerstner et al. 2018]] ^6c80e6
> Gerstner, W., Lehmann, M., Liakoni, V., Corneil, D. & Brea, J. Eligibility traces and plasticity on behavioral time scales: experimental support of neoHebbian three-factor learning rules. Front. Neural Circuits 12, 53 (2018).

^17348b
## From [[Ponulak 2011]]:
Elgibility trace the collection of changes in weights as proposed by STDP.

## From [[@vasilakiSpikeBasedReinforcementLearning2009|E. Vasilaki, N. Frémaux, R. Urbanczik, W. Senn, W. Gerstner (2009)]]
See also [[Three-Factor Learning Rule]]

This doesn’t really define it broadly, and kinda defines there particular implementation of it. Actually, add their definition of the difference between two-factor and three-factor. 

This gives the the three factor definition below in pretty broad strokes
> ![[@vasilakiSpikeBasedReinforcementLearning2009#Introduction]]
### The weight update rule
The aim of learning is to change the synaptic weights $w_{i j}$ so that the probability of receiving a reward $R$ increases. We consider learning rules of the form
$$
\frac{d w_{i j}}{d t}(t)=\alpha(R-b) \delta\left(t-t_{h i t}\right) e_{i j}(t)
$$
where $\alpha$ is the learning rate (controlling the amplitude of weight updates), 
$t_{\text {hit }}$ the moment when the animal hits the target or the wall, 
$R=1$ is the positive reward for finding the target, 
$R=-1$ the (negative) reward for bumping into a wall 
and $b$ a reward baseline, for instance an estimate of the positive reward based on past experience.

### The eligibility trace $e_{i j}(t)$ 
The eligibility trace $e_{i j}(t)$ evolves according

$$
\frac{d e_{i j}}{d t}(t)=-\frac{e_{i j}}{\tau_e}+\frac{g^{\prime}}{g}\left[Y_i(t)-\frac{\rho_i(t)}{1+\tau_c \rho_i(t)}\right] \sum_{t_j^f \in x_{j, t}} \varepsilon\left(t-t_j^f\right)
$$
where $Y_i(t)=\sum_f \delta\left(t-t_i^f\right)$ is the spike train of the postsynaptic neuron, $\delta(t)$ the Dirac function, $\tau_e$ the eligibility trace time constant, $\tau_c$ a parameter with units of time, and $g^{\prime}=d g / d u$ the derivative of the function $g(u)$.

