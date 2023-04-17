---
aliases: ["R. Lent (2018)",]
type: citation
status: open
project: [Present on SNN MAB]
priority: P5
creationtag: 2022-09-05 11:14
people: ["R. Lent"]
title: "Resource Selection in Cognitive Networks With Spiking Neural Networks"
dateadd: 2022-09-05T09:10:48Z
citetype: Journal Article
year: 2018
journal: IEEE transactions on cognitive communications and networking
URL: "NA"
DOI: "10.1109/TCCN.2018.2865387"
citekey: lentResourceSelectionCognitive2018
collection: SNN MAB ANIS
infotags: [Networks, learning systems, neural networks, simulation, space vehicle communication]
---

# Resource Selection in Cognitive Networks With Spiking Neural Networks
Read:: 
- [ ] Resource Selection in Cognitive Networks With Spiking Neural Networks R. Lent 2018 🛫 NA #reading #citation
Print::  ❌
Zotero Link:: NA
PDF:: NA
Files:: [Lent_2018_Resource Selection in Cognitive Networks With Spiking Neural Networks.pdf](file:////home/michaelt/Insync/m@tarlton.info/Google%20Drive/06.%20Zotero/storage/CGDKYE2U/Lent_2018_Resource%20Selection%20in%20Cognitive%20Networks%20With%20Spiking%20Neural%20Networks.pdf); [PubMed entry](file:///)
Reading Note:: [[R. Lent (2018)]]
Web Rip:: 

```dataview
TABLE without id
file.link as "Related Files",
title as "Title",
type as "type"
FROM "" AND -"ZZ. planning"
WHERE citekey = "lentResourceSelectionCognitive2018" 
SORT file.cday DESC
```

# Abstract
This paper explores the feasibility of a spiking neural network-based approach to cognitive networking, that is potentially suitable for low-power neuromorphic chips. We discuss the design of a **cognitive network controller (CNC**), 

which can dynamically optimize the selection of resources for recurrent network tasks, based on both its assigned objectives and observations of the actual performance achieved by each resource. We present a coding strategy for the action decisions based on the time-to-fire of spikes, a learning algorithm, and a regulation method to keep synapse strengths within an adequate range. 

To evaluate the proposed method, we apply the CNC to a challenged network environment using simulation. In this scenario, the CNC requires to optimize the average file transfer time over a multichannel space communication link, which is available only for a time window because of orbital dynamics. Compared to conventional methods, we show that the CNC achieves its objective for a broad range of offered loads. We examine the impact of key system factors that include learning and space protocol parameters. The proposed CNC potentially fosters the development of new cognitive networking applications.

# Quick Reference


# Top Comments
Learning method in section 3B

Strange they have to apply artificial bounds to prevent runaway (section 2C)

# Topics
##  Cognitive Network Controller (CNC)
> The goal of the Cognitive Network Controller (CNC) is to learn how to recurrently select network resources (actions) while optimizing a given objective when multiple redundant options are available for the same task, possibly operating at a different state and with different performance and efficiency levels. In general terms, the basic problem consists in the optimal selection of action a from a finite candidate set A for a cognitive networking task. The choice of the candidate set is application specific and to give a concrete example, in our evaluation scenario, the candidate set consists of radio frequency (RF) channels of different characteristics. 
> 
> The task of the CNC is to dynamically choose a channel for different file transfers (see Section IV). Other applications are certainly possible. The CNC relies on learning, which implies that it dynamically improves decisions based on its prior experience as it becomes aware of the environment. To support the operation of the CNC, we introduce a recurrent Spiking Neural Network (SNN) where neurons and synaptic connections behave according to (1) and (2). 

## Vertex (Graph Theory)
Nodes

## Round Robin (selection strategy)
 > **Round robin** is commonly used by various types of communication applications (e.g., time-division multiple access-TDMA). It deterministically rotates the output channel for each new packet transmission.
> A similar situation occurs with random walk, but with a selection that follows a uniform probability distribution function. Both round robin and random walk attempt to distribute equally the incoming traffic among the available resources, without consideration of the actual channel performance, and have constant time complexity. 

# Tasks

# Glossary
## $n$: a problem of A possible actions, with n corresponding nodes

## $G = (V, W)$ :
graph $G = (V, W)$, 
	where 
$V = {c_1 , . . . , c_n , \> g, \> e_1 , . . . , e_n ,\> i_1 , . . . , i_n }$ 
	and 
$W$ is the set of synapses. 

$i$ is the core neurons

Lol I think they reuse G for “average global objective”
## $c_1, \ldots, c_n$ 
	Vertices form a core network of $n$ recurrently connected excitatory neurons. 
 
 ## $w\left(c_i, c_j\right) \in W, i, j=1, \ldots, n$ .
	 non-negative weights connecting the core neurons, excluding self connections 

## $e_1, \ldots, e_n$ 
External inputs to each node.
Optional neurons $e_1-e_8$ and $i_1-i_8$ provide further control over the spike generation dynamics
## $i_1, \ldots, i_n$ 
Inhibitory? Optional, as opposed to the global and simple $I_{ref}$
Optional neurons $e_1-e_8$ and $i_1-i_8$ provide further control over the spike generation dynamics

Inhibitory neurons provide the regulation required to maintain the network within a suitable operational range. 
For efficiency purposes, this is achieved by introducing $g$ see below
## $g$
A single inhibitory neuron $g$ with multi-terminal postsynaptic connections to all core neurons with weights **$w^k\left(g, c_i\right),$ where $i, k=1, \ldots, n$**.

## $I_{r e f}$
constant stimuli $I_{r e f}$ that is applied to all core neurons and neuron $g$, which serves to start the analog dynamics of the SNN.

## $\theta$ : threshold  
threshold  (with typical value $-50 \mathrm{mV}$ ). 
After reaching $\theta$, the neuron fires a spike
**spikes occur at firing times $t^{(f)}: u\left(t^{(f)}\right)=\theta$**.

## $K = i_e(t)$ constant external current 
The first spike helps to "bootstrap" the SNN dynamics as follows. 
At time $t=0$, all core neurons receive an initial stimulus in the form of a constant external current $i_e(t)=K$. 

The value of $K$ is set sufficiently high to make each core neuron emit a spike at about the same time according to equation (1), unless an external inhibition signal $i_i(t)$ or external excitation signal is also applied.

##  $a=i^*$ Action Decision 
the next action decision $a=i^*$ is provided by the earliest neuron firing for the second time: $$
 c_{i^*}=\underset{c_i}{\operatorname{argmin}} t^{(2)}\left(c_i\right) \quad ; i=1, \ldots, n
 $$where $t^{(f)}(x)$ is the $f$-th time to fire of neuron $x$.

## $\eta$ : learning rate 
##  $\alpha$ : learning control parameter
parameter $\alpha$ controls the short-term memory of the CNC. Higher values of $\alpha$ applies higher importance to the most recent performance observations, whereas lower values of $\alpha$ improve the importance of the feedback history

The selection of $\eta$ and $\alpha$ is scenario specific and they would normally be determined by trial and error. As with $P_{r w}$, we evaluate the impact of selecting $\eta$ and $\alpha$ in our evaluation scenario in Section IV.

## $\lambda$ : Offered load
user demand
Rate of user demand?
## Nodes (vertices)

The reason for constructing the SNN based on the size of the candidate set is to be able to associate each core neuron to each of the available actions. 

## $C$ : Capacitor
Leaky-Integrate-and-Fire (LIF), model which explains the electrical properties of a neuron as consisting of a **capacitor $C$ connected in pvarallel with a resistor $R$**. 
## $R$ : Resistor
Leaky-Integrate-and-Fire (LIF), model which explains the electrical properties of a neuron as consisting of a **capacitor $C$ connected in pvarallel with a resistor $R$**. 

## Licklider Transmission Protocol (LTP)
not defined?
> The number of sessions of LTP in the Ku-band channels was also set to 10, but with transmission rates of 512 Kbps and 2 Mbps respectively. 
> The distance between the stations was used to find the timeout intervals for each new LTP session and the BER value that determines the maximum number of LTP rounds allowed by the protocol before aborting a block transmission. 
> BP, LTP, and channel parameters are usually fixed by mission control and the role of the CNC in this scenario is to exploit the existing resources, as they are provided, to achieve its assigned objective.
## Bundle Protocol (BP)
??

## **Equation 1**  : $u(t)$ membrane potential at time $t$
The circuit is driven by a current $I(t)$ and the voltage across these components gives the estimation of the neural membrane potential $u(t)$ :
$$
 \tau \frac{d}{d t} u(t)=-u(t)+R I(t)
 $$
where $\tau$ is the time constant of the circuit $(\tau=R C)$. The membrane potential gives the state of the neuron at time $t$ (see right-hand side of Fig. 1).

a neuron as consisting of a capacitor $C$ connected in parallel with a resistor $R$. 

## Equation 2 : $I(t)$ Driver Current
$$
 I(t)=i_e(t)+\sum_f \sum_j \sum_k w_{j k} i_{j k}^{(f)}(t)
 $$
Driver current $I(t)$ that stimulates a neuron is the aggregated effect 
of external stimuli, $i_e(t)$, 
and the trains of spikes generated at other neurons $j$ that reach neuron $i$. 

We note that multiple synapses may connect any two neurons, possibly with different strengths and delays due to length differences in the connections. This observation leads to the above expression for the driver current.

# Notes
## How do they learn?
In section 3b. The first neuron to fire in the second timestep (post-stimuli) is regarded as the next action

----
# Extracted Annotations and Comments
The key contributions of this paper are:
1) Introduces a recurrent neural network of spiking neurons that is suitable for the cognitive selection of network resources (actions). The SNN codes action decisions in the timing of spikes. Prior works have explored the use of different neural network types, but not SNNs.

2) Presents a learning algorithm for this SNN, which modifies presynapse strengths according to observed network performance and with respect to a given objective func- tion. We discuss how to find a suitable range for synaptic strengths and how to keep them within that range. 

3) Shows the feasibility of the SNN approach using a realistic simulation of a multi-channel space communi- cation scenario where the stations can only communicate directly for a short time window. We evaluate the impact of communication protocol parameters and learning parameters to give indication of the best values. 

The key idea is to link the activity of selected neurons (“core” neurons) to a cognitive action selection. 


## **II. SPIKING NEURON MODEL**
> We give a brief explanation of the spiking neuron model that we use to define our cognitive controller. For further details, we refer the reader to the specialized literature on the subject [4]. The model describes the neural dynamics with reasonable accuracy and at low complexity, which makes it attractive for our purposes. Biological neurons communicate through signals in the form of spikes. The spike generation and transfer from the emitting neuron (presynapse) to the receiving neuron (postsynapse) can be described by phenomenological models. 
> 
> One such model is the Leaky-Integrate-and-Fire (LIF), which explains the electrical properties of a neuron as consisting of a **capacitor $C$ connected in pvarallel with a resistor $R$**. 
> 
> Fig. 1 depicts the LIF model. The circuit is driven by a current $I(t)$ and the voltage across these components gives the estimation of the neural membrane potential $u(t)$ :
> 
> **Equation 1**
> $$
 \tau \frac{d}{d t} u(t)=-u(t)+R I(t)
 $$
> where $\tau$ is the time constant of the circuit $(\tau=R C)$. The membrane potential gives the state of the neuron at time $t$ (see right-hand side of Fig. 1).
> 
> A neuron may receive signals from other neurons or from an external source. The driver current $I(t)$ that stimulates a neuron is therefore, the aggregated effect of external stimuli, $i_e(t)$, and the trains of spikes generated at other neurons $j$ that reach neuron $i$. 
> 
> We note that multiple synapses may connect any two neurons, possibly with different strengths and delays due to length differences in the connections. This observation leads to the following expression for the driver current:
> 
> **Equation 2**
> $$
 I(t)=i_e(t)+\sum_f \sum_j \sum_k w_{j k} i_{j k}^{(f)}(t)
 $$
> Each synapse is characterized by parameter $w_{j k}, w_{j k}>=0$, which gives the strength of the $k$-th synapse originated at neuron $j$. The spikes generated by the presynaptic neuron $j$ produce a current $i_{j k}^{(f)}(t)$ on the postsynaptic neuron:
> 
> $$i_{j k}^{(f)}(t)=\delta\left(t-t_j^{(f)}-d_{j k}\right)$$, that is, it produces unit impulses that occur at the firing times $f$ of the presynaptic neuron, but delayed by a time $d_{j k}$. 
> 
> A spike produces either an excitatory or inhibitory effect on the postsynapse, that is, it either increments or decrements the driver current $I(t)$. 
> 
> The kind of effect is determined by the type of presynapse neuron-either excitatory or inhibitory. 
> 
> In terms of postsynaptic potential change, the $f$-th spike produces the change $$\epsilon\left(t-t_j^{(f)}-d_{j k}\right)$$, where $\epsilon(t)=\frac{t}{\tau} e^{1-t / \tau}$ with a preceding sign that depends on the kind of presynaptic neuron generating the spike. 

> The circuit on the left-hand side of Fig. 1 represents a synapse. A spike generated at the presynapse neuron arrives at the postsynapse after traversing a low-pass filter.
> 
> The analog description of the dynamics of a LIF unit changes drastically after its membrane potential reaches a certain threshold $\theta$ (with typical value $-50 \mathrm{mV}$ ). 
> 
> After reaching $\theta$, the neuron fires a spike that travels along its axon and then to other neurons through the synapses producing the analog-digital process on the other neurons. 
> 
> These spikes occur at firing times $t^{(f)}: u\left(t^{(f)}\right)=\theta$. After each spike, the membrane potential is reset to the value $u_r<\theta$ and remains at that value for a refractory period $\Delta$ before resuming the analog dynamics. 
> 
> We observe that for any neuron, the next time-to fire a spike depends on the aggregated current $I(t)$ and the current membrane potential $u(t)$. By adjusting the stimulus, it is possible to either accelerate, defer, or inhibit the next spike firing time. We use this observation to associate specific cognitive network actions to the neurons' time-to-fire.

---

##   **III. SNN Controller**

> The goal of the Cognitive Network Controller $(\mathrm{CNC})$ is to learn how to recurrently select network resources (actions) while optimizing a given objective when multiple redundant options are available for the same task, possibly operating at a different state and with different performance and efficiency levels. 
> 
> In general terms, the basic problem consists in the optimal selection of action a from a finite candidate set $A$ for a cognitive networking task. The choice of the candidate set is application specific and to give a concrete example, in our evaluation scenario, the candidate set consists of radio frequency (RF) channels of different characteristics. 
> 
> The task of the $\mathrm{CNC}$ is to dynamically choose a channel for different file transfers (see Section IV). Other applications are certainly possible. The CNC relies on learning, which implies that it dynamically improves decisions based on its prior experience as it becomes aware of the environment. 
> 
> To support the operation of the $\mathrm{CNC}$, we introduce a recurrent Spiking Neural Network (SNN) where neurons and synaptic connections behave according to (1) and (2).

> The key idea is to link the activity of selected neurons ("core" neurons) to a cognitive action selection. The size of the action candidate set determines the size of the SNN. Specifically, for a problem of $n$ possible actions, the SNN consists of the graph $G=(V, W)$, where $V=$ $\left\{c_1, \ldots, c_n, g, e_1, \ldots, e_n, i_1, \ldots, i_n\right\}$ and $W$ is the set of synapses. Vertices $c_1, \ldots, c_n$ form a core network of $n$ recurrently connected excitatory neurons. Excluding self-connections, these core neurons are connected with non-negative weights $w\left(c_i, c_j\right) \in W, i, j=1, \ldots, n$.
> 
> Inhibitory neurons provide the regulation required to maintain the network within a suitable operational range. 
> 
> For efficiency purposes, this is achieved by introducing a single inhibitory neuron $g$ with multi-terminal postsynaptic connections to all core neurons with weights $W^k$ $\left(g, c_i\right), i, k=1, \ldots, n$. 
> 
> Optionally, each core neuron $i$ has additional multi-terminal postsynaptic connections from one presynaptic excitatory neuron $e_i$ and one presynaptic inhibitory neuron $i_i: w^k\left(e_i, c_i\right), w^k\left(i_i, c_i\right), i, k=1, \ldots, n$. These neurons can be excited only by an external signal, $E_i$ and $I_i$ respectively, to either "encourage" or "discourage" specific actions. For example, as dictated by a schedule or by knowledge of the exclusion of a given asset, the corresponding action can be temporarily removed by inhibiting the related core neuron $c_i$ through the generation of spikes from $i_i$.

> In this SNN learning occurs by modifying according to some rule the weights $w\left(c_i, c_j\right) \in W, i, j=1, \ldots, n$, that is, the core neuron-to-core neuron synapses, and $w^k\left(g, c_i\right)$, $i, k=1, \ldots, n$-the synapses from inhibitory neuron $g$. 
> 
> The rest of the synapses remain fixed. Also, we define a constant stimuli $i_{r e f}$ that is applied to all core neurons and neuron $g$, which serves to start the analog dynamics of the SNN.
> 
> We note that the number of vertices of the proposed $\mathrm{SNN}$ design including the optional connections is $|V|=3 n+1$ and the number of edges is $|W|=n(n+2)$. 
> 
> For example, Fig. 2 depicts the SNN for an 8-action CNC. The core excitatory neurons $c 1-c 8$ are recurrently connected, with separate synapses each way, and neuron $g$ introduces inhibitory regulation to the core neurons. 
> 
> The neurons receive a constant stimulus *$I_{ref}$*, which makes them emit at least the first spike. 
> 
> Optional neurons $e_1-e_8$ and $i_1-i_8$ provide further control over the spike generation dynamics. In addition to the SNN topology, we need to define two mechanisms to make this design suitable for a cognitive networking task: an action encoding and a learning rule.
**P. 3**

### A. Time-Based Decision Coding
> The reason for constructing the SNN based on the size of the candidate set is to be able to associate each core neuron to each of the available actions. 
> 
> ***We define the CNC decision as the action that is associated to the core neuron emitting the earliest second spike***.
- **==So like, the next spike emitted by the core neuron after receiving input==**?

> The first spike helps to "bootstrap" the SNN dynamics as follows. 
> At time $t=0$, all core neurons receive an initial stimulus in the form of a constant external current $i_e(t)=K$. 
> 
> The value of $K$ is set sufficiently high to make each core neuron emit a spike at about the same time according to equation (1), unless an external inhibition signal $i_i(t)$ or external excitation signal is also applied.
> 
> Because of the recurrent structure of the SNN, emitted spikes will reach other core neurons after being modulated by the synaptic strengths as described by equation (2). 
> 
>This will cause neurons to continue firing at different times. 
>
>Assuming that the synapse strengths were previously customized to reflect a desired action-selection performance goal, the core neurons will emit their second spike following a time order that reflects their relevance to the given performance goal. 
>
>Specifically, the next action decision $a=i^*$ is provided by the earliest neuron firing for the second time: $$
 c_{i^*}=\underset{c_i}{\operatorname{argmin}} t^{(2)}\left(c_i\right) \quad ; i=1, \ldots, n
 $$
> where $t^{(f)}(x)$ is the $f$-th time to fire of neuron $x$. 
> 
> As with other learning algorithms, it is possible to reach local minima. 
> 
> To prevent the issue, we superpose a random walk to this decision process, which occurs with probability $P_w$, that is, with probability $P_w$ an action is selected randomly rather than by (3). 
> 
> Higher values of $P_w$ allow better exploration of the network state, but may also lead to the selection of suboptimal actions. 
> 
> In contrast, lower values of $P_w$ favors action optimally, but may lead to local minima. The value of $P_w$, therefore, controls the exploration and exploitation tradeoff of the learning process of the controller. 
> 
> In general, the value of $P_w$ should be small (e.g., less than $0.2$ ), but it is difficult to define a specific value for $P_w$ that works well for all cases. We later explore the impact of $P_w$ to network performance in our evaluation scenario (Section IV).

### B. Learning
> The general idea is to stimulate spike firing activity at the neurons associated to the actions that offer the best performance and to inhibit the rest. 
> 
> Therefore, learning occurs by modifying the core and global inhibition weights of the SNN according to the observed performance of prior actions. 
> 
> One difficulty to address is that no fixed performance reference can be safely assumed for all cases given that such value would depend not only on the type of application, but also on time-varying conditions. 
> 
> A simple solution is to assume that the performance reference is the average of prior outcomes. The advantage of this approach is that it can adapt to both improving or degrading environment performance.
> 
> Each performance feedback from the system (for action $i$ ) can be associated to a certain cost $C$. 
> 
> Potentially, $C$ can be a multivariate function of metrics of interest. 

> The new average objective $G$ is calculated from the current cost and the prior average: $G \leftarrow \alpha C+(1-\alpha) G$, for $0 \leq \alpha \leq 1$. 
- ==Not the same ***G*** as for the “graph==”
- ==What is alpha here?== 
	- See below
- ==Also pretty sure not the same **C**==

> **The learning rule changes the weights by an amount that is proportional to $\delta=G-C$**
> **==Equation 4==:**$$
 \begin{aligned}
 &w\left(c_j, c_i\right) \leftarrow w\left(c_j, c_i\right)+\eta \delta ; j=1, \ldots, n ; i \neq j \\
 &w^k\left(g, c_i\right) \leftarrow w^k\left(g, c_i\right)-\eta \delta ; k=1, \ldots, n
 \end{aligned}
 $$
> where $\eta>0$ is the learning rate. 
> 
> The value of $\eta$ can have a significant impact to network performance given that it controls how fast SNN weights change with respect to the new network state. 
> 
> Similarly, parameter $\alpha$ controls the short-term memory of the CNC. Higher values of $\alpha$ applies higher importance to the most recent performance observations, whereas lower values of $\alpha$ improve the importance of the feedback history. 
> 
> The selection of $\eta$ and $\alpha$ is scenario specific and they would normally be determined by trial and error. As with $P_{r w}$, we evaluate the impact of selecting $\eta$ and $\alpha$ in our evaluation scenario in Section IV.
> 
> We note that the complexity of the learning algorithm is $O(n)$, where $n$ is the SNN size (number of actions). Because no dependencies exist between weight updates, it is possible to implement learning in parallel with a time complexity $O(1)$.

### C. Synapse Strength Re-Scaling
> By adapting the weights of the SNN according to **(4)**, it is possible to either defer or accelerate the spike firings of any of the core neurons. 
> 
> However, this learning rule may also reduce or amplify certain weights to unsuitable levels. 
> 
> Weights that are too small may prevent some core neurons from firing. Likewise, neurons can saturate, and very large weights may produce no modification in the spike firings. 
> 
> The case is illustrated in Fig. 3 for a 2-neuron SNN connected through a single-terminal synapse. 
> 
> The presynaptic neuron was excited with a constant current of $2.1 \> \mathrm{nA}$ and the synaptic weight was varied, at a 1-unit resolution, to observe the firing times of the postsynaptic unit.
> 
> The postsynaptic neuron did not fire for weights below $96 .$ Weights above 600 produced no appreciable reduction of the time-to-fire. To prevent unsuitable weights, we suggest forcing the values to be in the range $\left[W_{\min }, W_{\max }\right]$ after applying the learning rule with:
> **==Equation 5==:**$$
 \begin{aligned}
 &w\left(c_i, c_j\right) \leftarrow \gamma\left(w\left(c_i, c_j\right)-W_{\min }\right)+W_{\min } \\
 &w^k\left(g, c_i\right) \leftarrow \gamma\left(w^k\left(g, c_i\right)-W_{\min }\right)+W_{\min }
 \end{aligned}
 $$
> where $W_{\text {min }}$ is the minimum allowable weight for any synapse of the SNN and $0<<\gamma<1(\gamma=0.8$ in our tests). The maximum weight is denoted $W_{\max }$. 
> The values of $W_{\min }$ and $W_{\max }$ need to be determined beforehand. 
> 
> A very simple procedure to find the minimum and maximum weight values is given by Algorithm 1. Note that this process is only needed once for any SNN. 
> 
> Approximated values for $W_{\text {min }}$ and $W_{\max }$ are enough. 
> 
> Algorithm 1 needs an initial estimation of a mid-level weight (within the bounds of the maximum and minimum weights) that needs to be experimentally determined. 
> 
> A value of 100 worked well with networks of size 2-100 in our tests. To minimize the processing overhead, the re-scaling process **(5)** should be restricted to the case when $$\left(w_{\max }-w_{\min }\right) \geq \gamma\left(W_{\max }-W_{\min }\right)$$, where $w_{\max }$ and $w_{\min }$ are the largest and smallest weights in the current SNN. 
> 
> After the calibration, it is straightforward to fix initial weights to the SNN (e.g., random in $\left[W_{\min }, W_{\max }\right]$ ). 
> 
> Note that as a result of the calibration and learning process, synapses' weights may be set to levels that may be biologically unrealistic. 
> 
> Also, spikes from a single presynapse could be sufficiently strong to cause an action potential on the postsynapse. 
- ==Less than ideal== 
> 
>It is possible to increase the biological realism of the design to address these observations. It will imply increasing the number of neurons and reducing the range of synaptic strengths. However, we could not identify evident benefits of improving the realism to the effectiveness of the $\mathrm{CNC}$, which remains biologically-inspired rather than biologically accurate.
- ==Ok so they adress it==
- ==Not getting bio-real for another few million n anyways==


## VI. Evaluation Scenario
> The International Space Station (ISS) is a low-orbit artificial satellite that travels at $7.57$ $\mathrm{km} / \mathrm{s}$ at an average distance of $400 \mathrm{~km}$ above the surface of the Earth. Its orbit is almost circular with a perigee of $401 \mathrm{~km}$ and apogee of $408 \mathrm{~km}$, but with a short period of revolution of $92.65$ minutes on a $51.64$-degree inclination. 
> 
> These orbital features limit direct communication opportunities between the ISS and a ground (Earth) station to 3 to 6 mins. Because of the short contact opportunity, the use of multiple links to concurrently transmit data between the ISS and a ground station can be of significant interest to move large data sets, in particular, for client-pull applications that involve certain level of interactivity. 
> 
> Such application is possible with low orbits because of the short propagation delays-of about $6 \mathrm{~ms}$ for the ISS. The assumption is therefore that the client (ground station) periodically requests data files (bundles) from the spacecraft while the link is available. In contrast, the use of one or more geostationary satellites acting as relays between a ground station and the ISS to extend the contact opportunity window can easily increase the total one-way propagation delay at least by a factor of 5 , which is undesirable for this application.

> We use the ground station-ISS communication context to define an application scenario for the proposed CNC. As service-level objective (SLO), the aim is to achieve response times that are less than a second on average. To evaluate the scenario, we have developed an event driven simulator that models the most relevant aspects of the real system to the communication, which include Earth-ISS orbital mechanics, radio propagation, bit transmission errors, packet buffering, and specific space protocols: the Licklider Transmission Protocol (LTP) and the Bundle Protocol (BP). 
> 
> **Packet buffering follows the common first-come-first-served policy with no priority queuing**. 
> 
> We further define that the ground station is located in Houston and that the ISS passes over that area offering a 5minute communication window. This is assuming a minimum elevation of about 40 degrees to remove the impact of ground-level obstacles and the atmospheric effects near the horizon. 
> 
> Fig. 4 (a) depicts the simulated ISS orbit with its true anomaly corresponding to 03/23/2018 at about $6 \mathrm{pm}$ central time and the location of the ground station. The distance of the ground station to the ISS for this contact period, as predicted by the simulator, is shown in Fig. 4 (b). The distance separating the stations during the ISS pass sets the signal propagation delay and the bit error rate for each packet transmission in the simulation.
---
> The CNC consists of a SNN of 13 neurons. A summary of the SNN model parameters appears in Table I. The interest is in evaluating the ability of the CNC to learn the best channel for each file transfer while exploiting their performance differences to achieve low response times. 
> 
> Because of the buffering and transmission delays, in addition to the time varying link quality, the best channel is likely different for every new file transmission. We consider four bi-directional channels that operate with carriers of $9,11,14$, and $16 \mathrm{GHz}$. The former two channels are in the X-band and the latter two in the Ku-band. We use phase-shift keying (PSK) in all channels with a common transmission power of $-3 \mathrm{~dB}$, total antenna gains of $70 \mathrm{~dB}$, and coding gain of $6 \mathrm{~dB}$. The transmission rate of the $X$-band channels was set to $256 \mathrm{Kbps}$ each. 
> 
> However, the LTP protocol of these channels was configured with a different number of sessions-set to 5 and 10 respectively. This parameter sets the maximum number of concurrent session transmissions, allowing the second channel to achieve twice as much throughput for the same load as long as it does not exceed the link capacity. 
> 
> The number of sessions of LTP in the Ku-band channels was also set to 10, but with transmission rates of $512 \mathrm{Kbps}$ and $2 \mathrm{Mbps}$ respectively. The distance between the stations was used to find the timeout intervals for each new LTP session and the BER value that determines the maximum number of LTP rounds allowed by the protocol before aborting a block transmission. BP, LTP, and channel parameters are usually fixed by mission control and the role of the $\mathrm{CNC}$ in this scenario is to exploit the existing resources, as they are provided, to achieve its assigned objective.
> 
> Each simulation run consists in the generation of random requests to the ISS from the ground station at rate $\lambda$ with an exponential interarrival distribution. Each request attempts to retrieve a file of average size $L$ from the ISS. The model for file sizes was also exponentially distributed. The choice of an exponential traffic model conveniently allows the verification of simulator outputs with well-known theoretical results, at least with static routing probabilities. We also verified the performance of the space protocols (BP and LTP) using theoretical models and experimental studies from the literature.

> The size of the request is fixed (100 bytes). Requests travel in bundles as data files do. We removed the bundle aggregation threshold and time limit constraints so that small bundles (i.e., requests) can be sent out without a deferring time. Each file is carried by a separate bundle and each bundle fits within a single $100 \%$ red-block LTP block for reliable delivery. LTP blocks are then sent as a number of segments, whose value depends on the maximum segment size that is a factor in the experiments. Rejected segments are sent by LTP up to a predetermined number of times and if such number is exceeded, the block is discarded. These features realistically follow the behavior of the real space protocols.

## V. Results
> For performance reference, we have included results that we obtained using three basic, non-cognitive selection strategies: **round robin, random walk, and reflex (greedy action**).
> 
> Since our main goal is to introduce and demonstrate the feasibility of the CNC-SNN concept, we believe that these basic methods provide good reference performance as they are widely used either as such or as part of more elaborate methods. 
> 
> **Round robin** is commonly used by various types of communication applications (e.g., time-division multiple access-TDMA). It deterministically rotates the output channel for each new packet transmission. 
> 
> A similar situation occurs with random walk, but with a selection that follows a uniform probability distribution function. Both round robin and random walk attempt to distribute equally the incoming traffic among the available resources, without consideration of the actual channel performance, and have constant time complexity. 
> 
> In contrast, the **reflex action method** selects the channel of the best observed performance. This is achieved by maintaining the vector $\left\{d_i\right\}$, for $i=1, \ldots, n$, where $d_i$ is the metric of interest associated to channel $i$. The method has constant time complexity with hashing or linear if using a simple list search.
> 
> In this work, the metric of interest is the file transfer time, which is extracted from the file request-response times. 
> 
> After completing a file transfer over channel $i$, the vector is updated with: $d_i \leftarrow \alpha_0 r_k+\left(1-\alpha_0\right) d_i$, where $r_k$ is the response time of the $k$-th file. The reflex action is simply obtained by selecting $\operatorname{argmin}_i\left\{d_i\right\}$. 
> 
> We only consider the pure reflex method: $\alpha_0=1$ to avoid introducing an extra factor to the evaluation. The study focuses on observing the impact of the user demand (offered load $\lambda$ ), protocol configuration (LTP segment length $m$ ), and $\mathrm{CNC}$ learning parameters $\left(\alpha, \eta\right.$, and $P_{r w}$ ). 
> 
> When possible, we indicate the $95 \%$ confidence interval of the mean in the charts that follow. The number of samples (complete simulation runs) for each average value reported in the figures the follow varies between 300 and 8000 and were obtained with the aid of a high-performance computer cluster.
> 
### A. Impact of the Offered Load
> The response time of each file is the time elapsed between the request and the file arrivals both at the ground station. It includes buffering time, propagation delay, and the time spent on the transmission and all retransmissions. User demand intensity was modeled with exponential interarrival times with mean $\lambda^{-1}$. Fig. 5 depicts the response time with LTP segment lengths of 1000 or 2000 bytes vs. the offered load $\lambda$.

> We note that the packet loss ratio nearly duplicates moving from 1000-byte to 2000-byte segments as the packet loss probability is given by $p=1-\left(1-p_e\right)^L$, where $p_e$ is the channel's bit error rate and $L$ is the packet length (bits). 
> 
> The higher loss rates impact performance due to the extra retransmission attempts that LTP must handle. We observed a reduction of about $20 \%$ in the maximum effective load to maintain the average response time below one second.

> The CNC produced lower average response times overall than the other methods except under the heaviest load near the 1-second response time mark. Compared to the reflex method, the CNC was able to deliver files with lower delay at low and mid load levels than all of the other methods. Beyond the usable range depicted in Fig. 5, the reflex method tends to perform better than the CNC. 
> 
> A likely explanation for this effect is that the extended buffering times that occur under high demand create excessive delay to the provision of upto-date information for $\mathrm{CNC}$ learning. This causes the $\mathrm{CNC}$ to learn stale information and as a result, to produce suboptimal actions. Our future work explores solutions to this issue, possibly by replacing the feedback with a mechanism that is not sensitive to congestion, or by switching methods for the high demand region. Both random walk and round robin, which do not consider channel performance, produced the worst performance as anticipated. We observed that congestion builds up quickly with these two methods and reduce the usable range to less than half compared to reflex or $\mathrm{CNC}$.
> 
> In terms of throughput, the $\mathrm{CNC}$ and the reflex method yielded similar outcomes followed by round robin and random walk (see Fig. 6). Throughput was not directly formulated into the learning goal of the $\mathrm{CNC}$, but it is interesting to note that despite producing lower delay that the other methods, the $\mathrm{CNC}$ did not add any throughput penalty.


### B. Impact of the Segment Length
> The choice of the segment length directly impacts the probability of packet loss as mentioned in the previous section. For each packet transmission, the simulator determines the distance between the stations to calculate the carrier-to-noise and the energy per bit to noise power spectral density ratio $\left(E_b / N_o\right)$ to then find the bit error rate for the transmission
> 
> $p_e$ using well known results for PSK modulation: $p_e=\operatorname{erfc}\left(0.5 E_b / N_o\right) / 2$. A direct implication of changing the segment length is that larger segments become more prone to errors, but LTP sessions also become smaller. In LTP, the transmission of each data block proceeds as the transmission of a sequence of segments. LTP uses a negative acknowledgment strategy to retransmit the segments lost in transit. During the first transmission round, LTP transmits the entire block and labels the last segment as the checkpoint segment (CS). 
> 
> On reception of the $\mathrm{CS}$, the receiver generates a report to the sender that serves as a request for the retransmission of the lost segments during the round. The process repeats for a number of rounds until all of the segments from the block are delivered, or after reaching the certain maximum number of attempts. In the latter case, the block is discarded. 
> 
> Block transmissions can occur in parallel with a user configuration limit. The segment length is also user configurable. Both parameters, the number of sessions (maximum parallel block transmissions) and the maximum segment size can be set by the user in the Interplanetary Overlay Network reference implementation of LTP [5]. 
> 
> These values can have a large impact on performance. We explore the impact by varying the segment length for values of the offered load of 1,3 , and $5 \mathrm{req} / \mathrm{s}$ and fixing a different number of sessions for each channel. The values for the offered load cover most of the usable range that produces acceptable response times (less than a second) for this application.
> 
> Fig. 7 depicts the results obtained with the $\mathrm{CNC}$ and the three reference methods: (a)-(c) show the response time for offered loads of 1,4 and $7 \mathrm{req} / \mathrm{s}$ respectively, and (d) depicts the observed throughput. 
> 
> As expected, random walk and round robin yielded the longest response times. We observed that the performance of the reflex method was quite sensitive to the choice of segment length and the corresponding packet loss ratio across all values of $\lambda$. 
> 
> Similar sensitivity was observed for the $\mathrm{CNC}$, but only for the highest workload level. We note that at this level, the outcome of round robin and random walk was well above 1 second, so those results are not visible in Fig. 7(c). In terms of throughput, the best performing methods, $\mathrm{CNC}$ and reflex, produced about the same outputs under different segment lengths.


### C. Impact of the Learning Parameters
> The three most relevant parameters that yield the learning behavior of the $\mathrm{CNC}$ are $a, \eta$, and $P_{I W}$. Parameter $a$ determines the short-term memory of the controller. It provides a weight for the most recent sample in the calculation of the average response time of the system. Parameter $\eta$ is the learning speed factor, which amplifies or reduces the impact of the performance difference between the selected action and the anticipated performance when updating the SNN weights. To enable exploration and prevent getting the system stuck in local minima, random walk actions are selected with probability $P_{F W}$.

> As shown in Fig. 8 (a)-(c) the value of $\eta$ produces significant variation in the expected response time of the system across the offered load range (at 3,5 and $7 \mathrm{req} / \mathrm{s}$ ). A larger $\eta$ reduces the average response time because it allows the $\mathrm{CNC}$ to quickly learn the actual channels' state. Giving low importance to the most recent samples (low $a$ ) tends to produce better results. However, the performance differences for different values of $a$ were not too high, except for the highest traffic load. No major performance differences were observed

> with different values of $a$ for the low and mid traffic cases, unlike the high traffic case. Throughput performance was almost indistinguishable with different values of $a$ or $\eta$ as shown in Fig. $8(\mathrm{~d})$.
> 
> Fig. 9 depicts the impact of the exploration vs. exploitation tradeoff, in terms of the probability $P_{r W}$ of selecting a random channel rather than the SNN decision for a file transfer. Fig. 9 (a)-(c) show the response time for $\lambda=3,5$, or 7 . Fig. 9 (d) shows the corresponding throughput, which we observed to be invariant across different choices of $\boldsymbol{a}$. For the selected scenario, a larger exploration (higher value of $P_{\Gamma W}$ ) produced detrimental performance except for small values of $P_{r W}$ (in the $0-0.05$ range) where we observed a small improvement with better exploration for the mid-to-high traffic intensity. In general, we observed that a value in the range $0.05-0.2$ produced a reasonable balance and the best results for this scenario.

---
# Figures (and Algorithms)
## Fig. 1
![[image-20220905140935112.png]]


## Fig. 2
![[image-20220905135559874.png]]

## Fig. 3
![[image-20220905164809154.png]]

## Fig. 5
![[image-20220907122016676.png]]

## Fig. 6
![[image-20220907124302836.png]]

## Fig. 7
![[image-20220907124333041.png]]

## Fig. 8
![[image-20220907124401863.png]]


## Fig. 9
![[image-20220907124435303.png]]





## Algo. 1
![[image-20220905170826788.png]]

## Table 1.
![[image-20220905171053526.png]]

