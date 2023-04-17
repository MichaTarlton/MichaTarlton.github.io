---
aliases:
type: [project, presentation]
project: Present on SNN MAB
status: closed
priority: p4
creationtag: 2022-09-06 12:00
infotags: [SNN, MAB]
---

```dataview
table rows.file.link AS "Related",
file.ctime as "Created",
infotags as "Tags"
FROM ""
WHERE contains(project,"Present on SNN MAB")
GROUP BY type
SORT file.ctime asc 
```
# Papers Provided by Anis
So far I’ve read the imported ones.
---
# So the main Paper [[@lentResourceSelectionCognitive2018|R. Lent (2018)]]
Discusses the design of a cognitive network controller (CNC)

Which like a **[[Multi-Armed Bandit Problem|MAB]]**  problem involves allocation of resources, or allocation of actions based on feedback of effectiveness from the interacting system.

The example they give is that of using a CNC to control packet communication with the ISS

---
## The Evaluation Problem
 > in our evaluation scenario, the action candidate set consists of radio frequency (RF) channels of different characteristics
 > 
 > The task of the $\mathrm{CNC}$ is to dynamically choose a channel for different file transfers 

> the CNC selects a channel for each bundle transmission attempting to achieve the service level objective (SLO) of average response times to be less than a second.

> The results indicate that the CNC achieves lower response times than common methods without impacting throughput. We observed up to 10 times lower delays than the reflex (greedy) method and many more times lower than the random and round robin methods.

> We revealed deficiencies of the CNC to achieve low delays under very high traffic. In those cases, packet congestion caused extreme delays in the feedback flow for the CNC, which impacted its learning ability and produced detrimental channel selection performance.

Larger data segments are more prone to errors with the model

> The CNC produced lower average response times overall than the other methods except under the heaviest load near the 1-second response time mark. Compared to the reflex method, the CNC was able to deliver files with lower delay at low and mid load levels than all of the other methods. Beyond the usable range depicted in Fig. 5, the reflex method tends to perform better than the CNC. 

> A likely explanation for this effect is that the extended buffering times that occur under high demand create excessive delay to the provision of up to-date information for $\mathrm{CNC}$ learning. This causes the $\mathrm{CNC}$ to learn stale information and as a result, to produce suboptimal actions. Our future work explores solutions to this issue, possibly by replacing the feedback with a mechanism that is not sensitive to congestion, or by switching methods for the high demand region. Both random walk and round robin, which do not consider channel performance, produced the worst performance as anticipated. We observed that congestion builds up quickly with these two methods and reduce the usable range to less than half compared to reflex or $\mathrm{CNC}$.

---
### Fig. 7
|![[image-20220907124333041.png]]

### Fig. 8
![[image-20220907124401863.png]]



## The Node Type
Very basic LIF with threshold firing value of theta

### Fig. 1
![[image-20220905140935112.png]]



## The architecture
Seems more like a ESN

recurrently connected excitatory neurons

The “core” neurons are full connected with non-negative weights between them $w\left(c_i, c_j\right) \in W, i, j=1, \ldots, n$
which are modified by “some rule” (not clear on it yet). These nodes $n$ correspond to the space of possible actions $A$.

These are modulated with inhibitory neurons to maintain network stability. In this example they use a single global inhibitory input $g$. Though, optionally they 



### Fig. 2
![[image-20220905135559874.png]]


## The dynamics
> ***We define the CNC decision as the action that is associated to the core neuron emitting the earliest second spike***.

I’m still not super certain what this means, but presumably it is the first spike to happen after the initial input step, and a “solving” time step of the network

> Assuming that the synapse strengths were previously customized to reflect a desired action-selection performance goal, the core neurons will emit their second spike following a time order that reflects their relevance to the given performance goal. 
>
>Specifically, the next action decision $a=i^*$ is provided by the earliest neuron firing for the second time: $$
 c_{i^*}=\underset{c_i}{\operatorname{argmin}} t^{(2)}\left(c_i\right) \quad ; i=1, \ldots, n
 $$

Network is also initialized with a “bootstrap” current sent to all spikes at $t=0$

## Training
Training is somewhat ill-defined (unless I’m missing something), with 

> Each performance feedback from the system (for action $i$ ) can be associated to a certain cost $C$. 
> Potentially, $C$ can be a multivariate function of metrics of interest. 
- I have no idea what this defines C as

> The new average objective $G$ is calculated from the current cost and the prior average: $G \leftarrow \alpha C+(1-\alpha) G$, for $0 \leq \alpha \leq 1$. 
- so some sort of moving average 

> **The learning rule changes the weights by an amount that is proportional to $\delta=G-C$:**
>$$
 \begin{aligned}
 &w\left(c_j, c_i\right) \leftarrow w\left(c_j, c_i\right)+\eta \delta ; j=1, \ldots, n ; i \neq j \\
 &w^k\left(g, c_i\right) \leftarrow w^k\left(g, c_i\right)-\eta \delta ; k=1, \ldots, n
 \end{aligned}
 $$
 
 If I’m reading this correctly, it doesn’t make any negative changes to the weights, and only applies those to the inhibitory neuron?
 
## Initial calibration
The initial values of the model parameters required calibration to ensure the network’s stability.
This included setting an upper and lower bound on the network weights.
While the network weight calibrations were obtainable through a provided algorithm, I believe the rest of the model parameters were arrived at by trial-and-error, it’s not exactly clear.

Like they mention a refractory period and then never bring it up again.

Things like the learning rate, and the short term memory control parameter $\alpha$  (aka exponential avg param) are explicitly chosen by trial and error.
> The selection of ηand α is scenario specific and they would normally be determined by trial and error.
> 
> Parameter $a$ determines the short-term memory of the controller. It provides a weight for the most recent sample in the calculation of the average response time of the system. Parameter $\eta$ is the learning speed factor, which amplifies or reduces the impact of the performance difference between the selected action and the anticipated performance when updating the SNN weights. To enable exploration and prevent getting the system stuck in local minima, random walk actions are selected with probability $P_{F W}$.

The $\alpha$ parameter is set manually depending on how much we want the system to focus on recent versus long-term changes. And the learning factor controls how fast the weights change.
Learning factor has a range of 1-2000 lol


### Table 1.
![[image-20220905171053526.png]]




### Algo. 1
![[image-20220905170826788.png]]


# The other paper I partly read [[@vasilakiSpikeBasedReinforcementLearning2009a|E. Vasilaki, N. Frémaux, R. Urbanczik, W. Senn, W. Gerstner (2009)]]

Hebbian (STDP sorta) vs standard gradient descent in a RL problem

Using three factor hebbian learning

Most interestingly they are using the Morris water maze, which is a memory / optimization task for animals


# Python implementation of MAB
## $\epsilon$-greedy,  $\epsilon$-decay, Optimistic Initial Value


### [[Epsilon Decay]]

### OIV
OIV outperforms both but I’m not exactly sure why.
How does it work exactly?
How does it estimate the reward?

> This approach differs significantly from the previous examples we explored because it does not introduce random noise to find the best action, _A*_n_. Instead, we over estimate the rewards of all the actions and continuously select the maximum. 
> 
> In this case, the algorithm explores early on as it seeks to maximize its returns while additional information allows the values to converge to their true means. This approach does require some additional background knowledge to be included in the set up because we need at least some idea of what the rewards are so that we can over estimate them.

## Implementing in SNN
I have not implemented it in an SNN yet.

It would likely be possible to implement it in the model used by Lent 2018, but I’m not entirely sure if that’s the most beneficial method.