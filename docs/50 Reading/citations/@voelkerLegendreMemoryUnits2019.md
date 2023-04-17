---
title: Legendre Memory Units: Continuous-Time Representation in Recurrent Neural Networks
authors: Aaron Voelker, Ivana Kajić, Chris Eliasmith
infotags: LMU, SNN, RNN
year: 2019
https://proceedings.neurips.cc/paper/2019/hash/952285b9b7e7a1be5aa7849f32ffff05-Abstract.html
citekey: voelkerLegendreMemoryUnits2019
MDnotes: [[@voelkerLegendreMemoryUnits2019-notes]]
---
# Legendre Memory Units: Continuous-Time Representation in Recurrent Neural Networks
# Abstract
We propose a novel memory cell for recurrent neural networks that dynamically maintains information across long windows of time using relatively few resources. The Legendre Memory Unit (LMU) is mathematically derived to orthogonalize its continuous-time history - doing so by solving $d$ coupled ordinary differential equations (ODEs), 
whose phase space linearly maps onto sliding windows of time via the Legendre polynomials up to degree $d-1$. 

Backpropagation across LMUs outperforms equivalently-sized LSTMs on a chaotic time-series prediction task, improves memory capacity by two orders of magnitude, and significantly reduces training and inference times.

LMUs can efficiently handle temporal dependencies spanning 100,000 time-steps, converge rapidly, and use few internal state-variables to learn complex functions spanning long windows of time - exceeding state-of-the-art performance among RNNs on permuted sequential MNIST. 

These results are due to the network's disposition to learn scale-invariant features independently of step size. Backpropagation through the ODE solver allows each layer to adapt its internal time-step, enabling the network to learn task-relevant time-scales. 

We demonstrate that LMU memory cells can be implemented using $m$ recurrently-connected Poisson spiking neurons, $\mathcal{O}(m)$ time and memory, with error scaling as $\mathcal{O}(d / \sqrt{m})$. We discuss implementations of LMUs on analog and digital neuromorphic hardware.


# Personal Summary
This may be a little too beyond me at the moment as everything refers to some module or topic which I am unfamiliar with.
I think I’m also missing how they actually structure a network with these things. See the section in the paper on the LMU model under 3.2. I may just need to better follow the methods section

# Notes

# Tasks
- [ ] Print out this paper #p3
- [ ] Relearn Legendre Polynomials you fucking idiot #p3 🔽


# Extracts

LTSM owes its superior performance to a combination of memory cells and gating mechanisms that maintain and nonlinearly mix information over time. ^msenuo

LSTMs are designed to help alleviate the issue of vanishing and exploding gradients commonly associated with training RNNs [5]. However, they are still prone to unstable gradients and saturation effects for sequences of length T > 100 [2, 22]. To combat this problem, extensive hyperparameter searches, gradient clipping strategies, layer normalization, and many other RNN training “tricks” are commonly employed [21]

Although standard LSTMs with saturating units have recently been found to have a memory of about T = 500–1,000 time-steps [25], non-saturating units in RNNs can improve gradient flow and scale to 2,000–5,000 time-steps before encountering instabilities [7, 25]. However, signals in realistic natural environments are continuous in time, and it is unclear how existing RNNs can cope with conditions as T → ∞. This is particularly relevant for models that must leverage long-range dependencies within an ongoing stream of continuous-time data, and run in real time given limited memory.

A spiking neural network called the Delay Network [38] embraces these mechanisms to approximate an ideal delay line by converting it into a finite number of ODEs integrated over time. This model reproduces properties of “time cells” observed in the hippocampus, striatum, and cortex [13, 38], and has been deployed on ultra low-power [6] analog and digital neuromorphic hardware including Braindrop [28] and Loihi [12, 37].

A spiking neural network called the Delay Network [38] embraces these mechanisms to approximate an ideal delay line by converting it into a finite number of ODEs integrated over time. This model reproduces properties of “time cells” observed in the hippocampus, striatum, and cortex [13, 38], and has been deployed on ultra low-power [6] analog and digital neuromorphic hardware including Braindrop [28] and Loihi [12, 37]

This paper applies the memory model from [38] to the domain of deep learning. In particular, we propose the Legendre Memory Unit (LMU), a new recurrent architecture and method of weight initialization that provides theoretical guarantees for learning long-range dependencies, even as the discrete time-step, ∆t, approaches zero. This enables the gradient to flow across the continuous history of internal feature representations. We compare the efficiency and accuracy of this approach to state-of-the-art results on a number of benchmarks designed to stress-test the ability of recurrent architectures to learn temporal relationships spanning long intervals of time.

## 2 Legendre Memory Unit
### Memory Cell Dynamics 

The main component of the Legendre Memory Unit (LMU) is a memory cell that orthogonalizes the continuous-time history of its input signal, $u(t) \in \mathbb{R}$, across a sliding window of length $\theta \in \mathbb{R}_{>0}$. 

The cell is derived from the linear transfer function for a continuous-time delay, $F(s)=e^{-\theta s}$, which is best-approximated by $d$ coupled ordinary differential equations (ODEs):
$$
\theta \dot{\mathbf{m}}(t)=\mathbf{A m}(t)+\mathbf{B} u(t)
$$
where 
- $\mathbf{m}(t) \in \mathbb{R}^{d}$ is a state-vector with $d$ dimensions. 

The ideal state-space matrices, (A, B), are derived through the use of Padé [30] approximants [37]:
$$
\begin{gathered}
\mathbf{A}=[a]_{i j} \in \mathbb{R}^{d \times d}, \quad a_{i j}=(2 i+1) \begin{cases}-1 & i<j \\
(-1)^{i-j+1} & i \geq j\end{cases} \\
\mathbf{B}=[b]_{i} \in \mathbb{R}^{d \times 1}, \quad b_{i}=(2 i+1)(-1)^{i}, \quad i, j \in[0, d-1] .
\end{gathered}
$$
The key property of this dynamical system is that $\mathbf{m}$ represents sliding windows of $u$ via the Legendre [24] polynomials up to degree $d-1$ :
$$
u\left(t-\theta^{\prime}\right) \approx \sum_{i=0}^{d-1} \mathcal{P}_{i}\left(\frac{\theta^{\prime}}{\theta}\right) m_{i}(t), \quad 0 \leq \theta^{\prime} \leq \theta, \quad \mathcal{P}_{i}(r)=(-1)^{i} \sum_{j=0}^{i}\left(\begin{array}{c}
i \\
j
\end{array}\right)\left(\begin{array}{c}
i+j \\
j
\end{array}\right)(-r)^{j}
$$
where $\mathcal{P}_{i}(r)$ is the $i^{\text {th }}$ shifted Legendre polynomial [32]. This gives a unique and optimal decomposition, wherein functions of $\mathbf{m}$ correspond to computations across windows of length $\theta$, projected onto $d$ orthogonal basis functions.


### Discretization 
We map these equations onto the memory of a recurrent neural network, $\mathbf{m}_{t} \in$ $\mathbb{R}^{d}$, given some input $u_{t} \in \mathbb{R}$, indexed at discrete moments in time, $t \in \mathbb{N}$ :
$$
\mathbf{m}_{t}=\overline{\mathbf{A}} \mathbf{m}_{t-1}+\overline{\mathbf{B}} u_{t}
$$
where $(\overline{\mathbf{A}}, \overline{\mathbf{B}})$ are the discretized matrices provided by the ODE solver for some time-step $\Delta t$ relative to the window length $\theta$. For instance, Euler's method supposes $\Delta t$ is sufficiently small:
$$
\overline{\mathbf{A}}=(\Delta t / \theta) \mathbf{A}+\mathbf{I}, \quad \overline{\mathbf{B}}=(\Delta t / \theta) \mathbf{B} .
$$
We also consider discretization methods such as zero-order hold ( $\mathrm{ZOH})$ as well as those that can adapt their internal time-steps [9].

### Approximation Error 
When $d=1$, the memory is analogous to a single-unit LSTM without any gating mechanisms (i.e., a leaky integrator with time-constant $\theta$ ). 

As $d$ increases, so does its memory capacity relative to frequency content. In particular, the approximation error in equation 3 scales as $\mathcal{O}(\theta \omega / d)$, where $\omega$ is the frequency of the input $u$ that is to be committed to memory [38].

### Layer Design 
The LMU takes an input vector, $\mathbf{x}_{t}$, 
and generates a hidden state, $\mathbf{h}_{t} \in \mathbb{R}^{n}$. 
 

Each layer maintains its own hidden state and memory vector. 
The state mutually interacts with the memory, $\mathbf{m}_{t} \in \mathbb{R}^{d}$, in order to compute nonlinear functions across time, while dynamically writing to memory. 

Similar to the NRU [7], the state is a function of the input, previous state, and current memory:
$$
\mathbf{h}_{t}=f\left(\mathbf{W}_{\mathbf{x}} \mathbf{x}_{t}+\mathbf{W}_{\mathbf{h}} \mathbf{h}_{t-1}+\mathbf{W}_{\mathbf{m}} \mathbf{m}_{t}\right)
$$
where $f$ is some chosen nonlinearity (e.g., tanh) and $\mathbf{W}_{\mathbf{x}}, \mathbf{W}_{\mathbf{h}}, \mathbf{W}_{\mathbf{m}}$ are learned kernels. 

**Note** this decouples the size of the layer's hidden state $(n)$ from the size of the layer's memory $(d)$, and requires holding $n+d$ variables in memory between time-steps. 

The input signal that writes to the memory (via equation 4) is:
$$
u_{t}=\mathbf{e}_{\mathbf{x}}^{\top} \mathbf{x}_{t}+\mathbf{e}_{\mathbf{h}}^{\top} \mathbf{h}_{t-1}+\mathbf{e}_{\mathbf{m}}{ }^{\top} \mathbf{m}_{t-1}
$$
where $\mathbf{e}_{\mathbf{x}}, \mathbf{e}_{\mathbf{h}}, \mathbf{e}_{\mathbf{m}}$ are learned encoding vectors. 

Intuitively, the kernels (W) learn to compute nonlinear functions across the memory, while the encoders (e) learn to project the relevant information into the memory. 

The parameters of the memory $(\overline{\mathbf{A}}, \overline{\mathbf{B}}, \theta)$ may be trained to adapt their time-scales by backpropagating through the ODE solver [9], although we do not require this in our experiments.

This is the simplest design that we found to perform well across all tasks explored below, but variants in the form of gating $u_{t}$, forgetting $\mathbf{m}_{t}$, and bias terms may also be considered for more challenging tasks. Our focus here is to demonstrate the advantages of learning the coupling between an optimal linear dynamical memory and a nonlinear function.

## 3 Experiments

Tasks were selected with the goals of validating the LMU's derivation while succinctly highlighting its key advantages: it can learn temporal dependencies spanning $T=100,000$ time-steps, converge rapidly due to the use of non-saturating memory units, and use relatively few internal state-variables to compute nonlinear functions across long windows of time. 

**Proper weight initialization is central to the performance** of the LMU, as the architecture is indeed a specific way of configuring a more general RNN in order to learn across continuous-time representations. 

Equation 2 (the Pade approximants) and $\mathrm{ZOH}$ are used to initialize the weights of the memory cell $(\overline{\mathbf{A}}, \overline{\mathbf{B}})$. 

The time-scale $\theta$ is initialized based on prior knowledge of the task. 

We find that $\overline{\mathbf{A}}, \overline{\mathbf{B}}, \theta$ do not require training for these tasks since they can be appropriately initialized.  ^h713nh

We recommend equation 3 as an option to initialize $\mathbf{W}_{\mathbf{m}}$ that can improve training times. 

The memory's feedback encoders are initialized to $\mathbf{e}_{\mathbf{m}}=\mathbf{0}$ to ensure stability. 

Remaining kernels $\left(\mathbf{W}_{\mathbf{x}}, \mathbf{W}_{\mathbf{h}}\right)$ are initialized to Xavier normal [15] 

and the remaining encoders $\left(\mathbf{e}_{\mathbf{x}}, \mathbf{e}_{\mathbf{h}}\right)$ are initialized to LeCun uniform [23]. 

The activation function $f$ is set to tanh. 

We use the Adam optimizer [20] with default hyperparameters, monitor the validation loss to save the best model, and train until convergence or 500 epochs. 

We note that our method does not require layer normalization, gradient clipping, or other regularization techniques.

> Lol this figure is way less helpful than I thought
! [[Pasted image 20220508173818.png]]



> [!Bookmark]
> Stopped extracting here in interest of finishing the read

## 4 Characteristics of the LMU
### Linear-Nonlinear Processing 
Linear units maximize the information capacity of dynamical systems, while nonlinearities are required to compute useful functions across this information [19].

The LMU formalizes this linear-nonlinear trade-off by decoupling the functional role of $d$ linear memory units from that of $n$ nonlinear hidden units, and then using backpropagation to learn their coupling.

### Parameter-State Trade-offs 
One can increase $d$ to improve the linear memory $(\mathbf{m})$ capacity at the cost of a linear increase in the size of the encoding parameters, or, increase $n$ to improve the complexity of nonlinear interactions with the memory $(h)$ at the expense of a quadratic increase in the size of the recurrent kernels. Thus, $d$ and $n$ can be set independently to trade storage for parameters while balancing linear memory capacity with hidden nonlinear processing.

### Optimality and Uniqueness
The memory cell is optimal in the sense of being derived from the Padé [30] approximants of the delay line expanded about the zeroth frequency [38]. These approximants have been proven optimal for this purpose. 

Moreover, the phase space of the memory maps onto the unique set of orthogonal polynomials over $[0, \theta]$ (the shifted Legendre polynomials) up to a constant scaling factor [24]. Thus the LMU is provably optimal with respect to its continuous time memory capacity, which provides a nontrivial starting point for backpropagation. 

To validate this characteristic, we reran the psMNIST benchmark with the diagonals of $\overline{\mathbf{A}}$ perturbed by $\epsilon \in$ $\{-0.01,-0.001,0.001,0.01\}$. Despite retraining the network for each $\epsilon$, this achieved sub-optimal test performance in each case, and resulted in chance-level performance for larger $|\epsilon|$.

## 5 Spiking implementation 
Here we review these findings and their implications for neuromorphic deep learning. The challenge in this section pertains to the substitution of static nonlinearities that emit multi-bit activities every time-step (i.e., “rate” neurons) with spiking neurons that emit temporally sparse 1-bit events. 

We consider Poisson neurons since they are stateless, and thus serve as an inexpensive mechanism for sparsifying signals over time – but this is not a strict requirement. 

More generally, by reducing the amount of communication and converting weight multiplies into additions, spikes can trade precision for energy-efficiency on neuromorphic hardware [6, 12]. Moreover, this can be accomplished while preserving the optimizations afforded by deep learning [31].

