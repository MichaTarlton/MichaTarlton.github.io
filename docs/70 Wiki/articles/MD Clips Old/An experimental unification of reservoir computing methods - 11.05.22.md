---
created: 2022-05-11T12:26:47 (UTC +02:00)
tags: []
source: https://www.sciencedirect.com/science/article/pii/S089360800700038X
author: Herbert Jaeger, Wolfgang Maass, Jose Principe
---

# An experimental unification of reservoir computing methods - ScienceDirect



> ## Excerpt
> Three different uses of a recurrent neural network (RNN) as a reservoir that is not trained but instead read out by a simple external classification l…

---
[![Elsevier](https://sdfestaticassets-eu-west-1.sciencedirectassets.com/prod/14ae1d96d11fc29cfae0a45bff4a1ec56ae7a56a/image/elsevier-non-solus.png)](https://www.sciencedirect.com/journal/neural-networks "Go to Neural Networks on ScienceDirect")

[![Neural Networks](https://ars.els-cdn.com/content/image/1-s2.0-S0893608007X01394-cov150h.gif)](https://www.sciencedirect.com/journal/neural-networks/vol/20/issue/3)

## 

2007 Special Issue

An experimental unification of reservoir computing methods

## Abstract

Three different uses of a recurrent neural network (RNN) as a reservoir that is not trained but instead read out by a simple external classification layer have been described in the literature: Liquid State Machines (LSMs), Echo State Networks (ESNs) and the Backpropagation Decorrelation (BPDC) learning rule. Individual descriptions of these techniques exist, but a overview is still lacking. Here, we present a series of experimental results that compares all three implementations, and draw conclusions about the relation between a broad range of reservoir parameters and network dynamics, memory, node complexity and performance on a variety of benchmark tests with different characteristics. Next, we introduce a new measure for the reservoir dynamics based on Lyapunov exponents. Unlike previous measures in the literature, this measure is dependent on the dynamics of the reservoir in response to the inputs, and in the cases we tried, it indicates an optimal value for the global scaling of the weight matrix, irrespective of the standard measures. We also describe the Reservoir Computing Toolbox that was used for these experiments, which implements all the types of Reservoir Computing and allows the easy simulation of a wide range of reservoir topologies for a number of benchmarks.

-   [**Previous**](https://www.sciencedirect.com/science/article/pii/S0893608007000329)
-   [**Next**](https://www.sciencedirect.com/science/article/pii/S0893608007000500)

## Keywords

Reservoir computing

Memory capability

Chaos

Lyapunov exponent

## 1\. Introduction

Recurrent neural networks (RNNs) seem to offer an attractive method for solving complicated engineering tasks. They have the advantages of feedforward networks, which include robustness, learning by example and the ability to model highly nonlinear systems, and add to that an inherent temporal processing capability. Possible–and actual–applications are manifold and include the learning of context free and context sensitive languages ([Gers and Schmidhuber, 2001](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b9), [Rodriguez, 2001](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b36)), control and modeling of complex dynamical systems ([Suykens, Vandewalle, & De Moor, 1996](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b43)) and speech recognition ([Graves et al., 2004](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b11), [Robinson, 1994](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b35)).

RNNs have been shown to be Turing equivalent ([Kilian & Siegelmann, 1996](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b20)) for common activation functions and can approximate arbitrary finite state automata ([Omlin & Giles, 1994](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b34)). So, theoretically, RNNs are very powerful tools for solving complex temporal machine learning tasks. Nonetheless, several factors still hinder the large scale deployment of RNNs in practical applications. So far, not many learning rules exist ([Haykin, 1999](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b12), [Jaeger, 2002](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b15), [Suykens and Vandewalle, 1998](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b44)) and most suffer from slow convergence rates, thus limiting their applicability. Recently, however, three similar solutions for this problem have been proposed independently.

Maass et al. ([Maass, Natschläger, & Markram, 2002](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b26)), [Jaeger (2001a)](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b13) and [Steil (2004)](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b42) all describe the possibility of using an RNN without adapting the weights of the internal connections. In principle, the output can be generated using any type of classifier or regressor, ranging from a perceptron ([Minsky & Papert, 1969](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b31)) to a Support Vector Machine ([Vapnik, 1995](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b46)). In almost all applications, however, a simple linear discriminant or regression algorithm ([Duda, Hart, & Stork, 2001](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b8)) is used to compute the desired output. This type of readout function offers some quite convincing advantages–such as its ease of training and guaranteed optimality in a least squares sense–and yields very good results. From this viewpoint, the function of the reservoir is similar to that of a kernel in the case of kernel-based methods, by projecting the inputs into a high-dimensional space which enhances the separability. For traditional methods, the projection into the high-dimensional space does not need to be computed because of a convenient mathematical construction (the so-called *kernel trick*), while for reservoir methods the projection is explicit. A significant advantage of the reservoir approach, however, is the fact that the kernel is able to incorporate temporal information present in the inputs.

### 1.1. Using RNNs as reservoirs

The *Liquid State Machine* (LSM) by [Maass et al. (2002)](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b26) proposes a generic framework, where the reservoir can consist of a broad range of node types, and needs to obey a quite unrestrictive property (the *point-wise separation* property) ([Maass et al., 2002](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b26)) in order to be computationally useful. In practice, most descriptions of the LSM use reservoirs built from a relatively simple spiking neuron model called the Leaky Integrate and Fire (LIF) neuron ([Maass & Bishop, 2001](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b24)) with a dynamic synapse model ([Gerstner & Kistler, 2002](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b10)), but the use of threshold logic gates (TLGs) has also been described ([Natschläger, Bertschinger, & Legenstein, 2004](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b32)). Spiking neuron models are more complex than sigmoidal neurons but they have been shown to be computationally more powerful ([Maass, 1997](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b23)). The readout layer, on the other hand, is also very broadly specified: it needs to be able to approximate any continuous function over a compact set $<math><mi is="true">X</mi><mo is="true">⊆</mo><msup is="true"><mrow is="true"><mi mathvariant="double-struck" is="true">R</mi></mrow><mrow is="true"><mi is="true">N</mi></mrow></msup></math>$ of input values. When both conditions are fulfilled, the resulting LSM is guaranteed to be able to approximate any time-invariant function with fading memory[1](https://www.sciencedirect.com/science/article/pii/S089360800700038X#fn1) operating on timeseries. However, these sufficient conditions are too broad to offer a practical guideline for constructing reservoirs, and quite probably universal approximation of temporal functions is not needed to solve real world problems. So, while this result is very convincing from a theoretical point of view, the transition to practical applications is still unclear.

Jaeger independently proposed a very similar computational idea which he calls *Echo State Networks* ([Jaeger, 2001a](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b13)). The main difference with LSMs lies in the type of nodes that constitute the reservoir: where LSMs are usually built from spiking LIF neurons, these reservoirs are built from analog sigmoidal neurons. Here too, a theoretical property is defined for potentially interesting reservoirs called the *echo state* property ([Jaeger, 2001a](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b13)), which expresses–informally stated–the fact that the influence of inputs on reservoir states fades away gradually. Further, an upper and lower bound are defined for the echo state property that are very easy to compute and depend only on the weight matrix of the reservoirs. However, this property alone is not sufficient to guarantee optimal performance for a given problem, and the search for a good reservoir requires experience and can take some time. In [Jaeger (2002)](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b15), some guidelines are offered, but a structured method is still lacking.

Thirdly, Steil proposes an O(N) learning rule for RNNs called *Backpropagation Decorrelation* (BPDC) ([Steil, 2004](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b42)). The BPDC rule is an extension of a state-of-the-art learning algorithm for RNNs (Atiya–Parlos recurrent learning ([Atiya & Parlos, 2000](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b2))). It appears that this APRL learning rule restricts the adaptation of the weights to the output layer, effectively splitting the RNN into a reservoir and a readout layer. Only the weights to the output layer and the recurrent connections inside the output layer are trained. Thus, the use of an RNN as a reservoir was attained here from an entirely different angle than the previous two approaches. Here too, sigmoidal neurons are used, but a significant difference between BPDC reservoirs and ESNs is the fact that feedback connections from the readout layer into the reservoir and into the readout layer itself are used, whereas in practice this is hardly ever the case for ESNs.

### 1.2. Applications of reservoir computing

Several successful applications of reservoir computing to both ‘abstract’ and real world engineering applications have been reported in the literature. Abstract applications include dynamic pattern classification ([Jaeger, 2001b](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b14)), autonomous sine generation ([Jaeger, 2001a](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b13), [Verstraeten et al., 2005](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b47)) or the computation of highly nonlinear functions on the instantaneous rates of spike trains ([Maass, Natschlger, & Markram, 2004](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b28)). In robotics, LSMs have been used to control a simulated robot arm ([Joshi & Maass, 2004](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b19)), to model an existing robot controller ([Burgsteiner, 2005b](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b5)), to perform object tracking and motion prediction ([Burgsteiner, 2005a](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b4), [Maass et al., in press](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b25)) or event detection ([Jaeger, 2005](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b17)). ESNs have been used in the context of reinforcement learning ([Bush & Anderson, 2005](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b6)). Also, applications in the field of Digital Signal Processing (DSP) have been quite successful, such as speech recognition ([Maass et al., 2003](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b27), [Skowronski and Harris, 2006](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b38), [Verstraeten et al., 2005](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b48)) or noise modeling ([Jaeger & Haas, 2004](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b18)). Finally, the use of reservoirs for chaotic timeseries generation and prediction has been reported in [Jaeger, 2001b](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b14), [Jaeger, 2003](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b16), [Steil, 2005](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b40), [Steil, 2006](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b41).

### 1.3. Comparing reservoir computing methods

In this contribution, we offer an experimental overview of the different implementations of reservoir computing described in the literature. In Section [2](https://www.sciencedirect.com/science/article/pii/S089360800700038X#sec2), we present experimental results for benchmarks with different characteristics. Section [2.1](https://www.sciencedirect.com/science/article/pii/S089360800700038X#sec2.1) shows the relation between the complexity of the reservoir nodes and the performance on three tasks. Section [2.2](https://www.sciencedirect.com/science/article/pii/S089360800700038X#sec2.2) investigates the effects of memory on the node level and the reservoir level. Thirdly, Section [2.3](https://www.sciencedirect.com/science/article/pii/S089360800700038X#sec2.3) links three existing bounds for the echo state property to the actual dynamics in the network, quantified using a Lyapunov-inspired method as a measure of the network dynamics. In Section [3](https://www.sciencedirect.com/science/article/pii/S089360800700038X#sec3), we present a novel toolbox we developed to do this work, that incorporates all reservoir implementations currently described and some novel ones. We outline its modular structure and describe which components are present. In Section [4](https://www.sciencedirect.com/science/article/pii/S089360800700038X#sec4), finally, we conclude and outline future work.

Contributions on reservoir computing methods often focus on a specific type of reservoir interconnection and node type. LSMs focus on a specific, small world interconnectivity pattern with reservoirs built from spiking neurons. ESNs, on the other hand, have been described with several different interconnection structures and analog neurons. What is still lacking from the literature, however, is a thorough overview of the performance of different reservoir node types.

When one wants to solve a task using reservoir computing, one has to choose not only the node type but also the interconnection topology and weight distribution. Several metrics have been described in the literature that are supposed to offer an a priori indication of how the reservoir will perform without explicitly having to apply it to a task. However, a clear indication of which metric values are optimal for which task is not yet available, and the values of these metrics have not yet been linked to the actual reservoir dynamics.

In this section, we present experimental work that gives a broad overview of the influence of certain reservoir parameters on the performance and the network dynamics. To account for the variability of the performance due to the stochastic construction of the reservoirs, we simulated every parameter setting 30 times. We used three tasks with very different characteristics to evaluate the performance of reservoirs, which we will briefly describe here. See [Appendix A](https://www.sciencedirect.com/science/article/pii/S089360800700038X#appA) for a thorough description of the experiments described in this contribution.

The first task is a rather complex classification problem, namely the isolated spoken digit recognition task discussed in [Verstraeten et al. (2005)](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b48). The task is to recognize ten isolated digits spoken by five different female speakers. Performance is expressed as the word error rate (WER) and is measured using ten-fold cross-validation over the dataset containing 500 samples. The speech was preprocessed using a biological model of the human cochlea by [Lyon (1982)](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b22) resulting in a 77-channel cochleagram. For spiking reservoirs, this cochleagram was converted into spike trains using a filter-coding method called BSA ([Schrauwen & Van Campenhout, 2003](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b37)).

The second task is an evaluation of the memory capacity of the reservoir, where the task is to reproduce delayed versions of a random uniform noise signal. This task is described in [Jaeger (2001b)](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b14). The delays range from 1 to 100 timesteps. The memory capacity is measured as the total amount of variability in the output of the classifiers that was caused by the input to the reservoir (see [Appendix A](https://www.sciencedirect.com/science/article/pii/S089360800700038X#appA) and [Jaeger (2001b)](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b14) for a precise definition), and is therefore an indication of the amount of information contained in the input that is still present inside the reservoir after a certain delay.

The third task is the NARMA task described in [Jaeger (2003)](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b16), [Steil (2005)](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b40) and others, where the following tenth-order system needs to be modeled: $<math><mi is="true">y</mi><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">+</mo><mn is="true">1</mn><mo is="true">)</mo></mrow><mo is="true">=</mo><mn is="true">0.3</mn><mi is="true">y</mi><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">)</mo></mrow><mo is="true">+</mo><mn is="true">0.05</mn><mi is="true">y</mi><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">)</mo></mrow><mrow is="true"><mo is="true">[</mo><msubsup is="true"><mrow is="true"><mo is="true">∑</mo></mrow><mrow is="true"><mi is="true">i</mi><mo is="true">=</mo><mn is="true">0</mn></mrow><mrow is="true"><mn is="true">9</mn></mrow></msubsup><mi is="true">y</mi><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">−</mo><mi is="true">i</mi><mo is="true">)</mo></mrow><mo is="true">]</mo></mrow><mo is="true">+</mo><mn is="true">1.5</mn><mi is="true">u</mi><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">−</mo><mn is="true">9</mn><mo is="true">)</mo></mrow><mi is="true">u</mi><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">)</mo></mrow><mo is="true">+</mo><mn is="true">0.1</mn></math>$. Here, the input to the reservoir $<math><mstyle mathvariant="bold" is="true"><mi is="true">u</mi></mstyle><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">)</mo></mrow></math>$ is uniform random noise, and a single linear regression function is trained to reproduce $<math><mi is="true">y</mi><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">+</mo><mn is="true">1</mn><mo is="true">)</mo></mrow></math>$.

### 2.1. Node complexity

When solving an engineering task using Reservoir Computing, one of the choices that needs to be made is the neuron model with which to build the reservoir. In the case of analog signals (as opposed to spike trains), reservoirs can be built from linear nodes without an activation function that are very fast to simulate but offer inferior computational power or sigmoidal neurons. In the case of the sigmoidal neurons, the choice exists between a linear classifier as readout function (as for ESNs) or a recurrent layer of sigmoidal neurons (as for the BPDC learning rule). One can also implement sigmoidal neurons that have a form of internal memory, in which case they are called analog integrator neurons ([Jaeger, 2002](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b15)). The reservoir dynamics are described in this case by (1)$<math><mstyle mathvariant="bold" is="true"><mi is="true">s</mi></mstyle><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">+</mo><mn is="true">1</mn><mo is="true">)</mo></mrow><mo is="true">=</mo><mrow is="true"><mo is="true">(</mo><mn is="true">1</mn><mo is="true">−</mo><mfrac is="true"><mrow is="true"><mi is="true">δ</mi></mrow><mrow is="true"><msub is="true"><mrow is="true"><mi is="true">τ</mi></mrow><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">int</mi></mstyle></mrow></msub></mrow></mfrac><mo is="true">)</mo></mrow><mo is="true">⋅</mo><mstyle mathvariant="bold" is="true"><mi is="true">s</mi></mstyle><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">)</mo></mrow><mo is="true">+</mo><mfrac is="true"><mrow is="true"><mi is="true">δ</mi></mrow><mrow is="true"><msub is="true"><mrow is="true"><mi is="true">τ</mi></mrow><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">int</mi></mstyle></mrow></msub></mrow></mfrac><mo is="true">⋅</mo><mo is="true">tanh</mo><mrow is="true"><mo is="true">(</mo><mstyle mathvariant="bold" is="true"><mi is="true">u</mi></mstyle><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">)</mo></mrow><mo is="true">⋅</mo><msub is="true"><mrow is="true"><mstyle mathvariant="bold" is="true"><mi is="true">W</mi></mstyle></mrow><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">in</mi></mstyle></mrow></msub><mo is="true">+</mo><mstyle mathvariant="bold" is="true"><mi is="true">s</mi></mstyle><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">)</mo></mrow><mo is="true">⋅</mo><mstyle mathvariant="bold" is="true"><mi is="true">W</mi></mstyle><mo is="true">)</mo></mrow><mtext is="true">,</mtext></math>$ where $<math><mstyle mathvariant="bold" is="true"><mi is="true">s</mi></mstyle></math>$ is a vector containing the activation of the neurons in the reservoir, $<math><msub is="true"><mrow is="true"><mstyle mathvariant="bold" is="true"><mi is="true">W</mi></mstyle></mrow><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">in</mi></mstyle></mrow></msub></math>$ and $<math><mstyle mathvariant="bold" is="true"><mi is="true">W</mi></mstyle></math>$ are the input and reservoir weight matrices and $<math><mstyle mathvariant="bold" is="true"><mi is="true">u</mi></mstyle></math>$ the input to the reservoir. Note that here the integration factor of $<math><mn is="true">1</mn><mo is="true">/</mo><msub is="true"><mrow is="true"><mi is="true">τ</mi></mrow><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">int</mi></mstyle></mrow></msub></math>$ is applied outside of the nonlinearity, in contrast to the reservoirs used by the BPDC learning rule. For the remainder of this contribution, we set the timestep $<math><mi is="true">δ</mi></math>$ to one for reasons of simplicity. The factor $<math><mn is="true">1</mn><mo is="true">/</mo><msub is="true"><mrow is="true"><mi is="true">τ</mi></mrow><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">int</mi></mstyle></mrow></msub></math>$ is a measure for the amount of internal memory of the neurons: if $<math><msub is="true"><mrow is="true"><mi is="true">τ</mi></mrow><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">int</mi></mstyle></mrow></msub></math>$ is equal to one, the nodes have no internal memory and behave as classic sigmoid neurons. For integration timeconstants $<math><msub is="true"><mrow is="true"><mi is="true">τ</mi></mrow><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">int</mi></mstyle></mrow></msub></math>$ larger than one, the self-feedback is enhanced. For clarity, we will refer to this parameter in the form of the retainment rate $<math><mi is="true">r</mi><mo is="true">=</mo><mn is="true">1</mn><mo is="true">−</mo><mn is="true">1</mn><mo is="true">/</mo><msub is="true"><mrow is="true"><mi is="true">τ</mi></mrow><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">int</mi></mstyle></mrow></msub></math>$, which can range between $<math><mrow is="true"><mo is="true">[</mo><mn is="true">0</mn><mo is="true">,</mo><mn is="true">1</mn><mo is="true">]</mo></mrow></math>$ and is set to 0.2 for the experiments in this subsection. For a more elaborate discussion of this parameter, see Section [2.2](https://www.sciencedirect.com/science/article/pii/S089360800700038X#sec2.2).

When we move into the domain of the spiking neurons, one of the simplest models is the LIF neuron which consists of a leaky membrane whose potential is increased by incoming spikes and that emits a spike itself once the potential reaches a threshold. This model can be extended by modeling the function of exponentially decaying synapses. For this contribution, we used a simplified synapse model called the Booij model that allows fast and accurate simulation. However, to make the comparison with LIF neurons without a synapse model correct, we needed to rescale the weight matrix (this is further detailed in [Appendix B](https://www.sciencedirect.com/science/article/pii/S089360800700038X#appB)).

Besides the nodetype, two major parameters that determine the reservoir dynamics and performance are its size and its spectral radius. The spectral radius is the largest absolute value of the eigenvalues of the weight matrix and for discrete linear time-invariant systems, a spectral radius smaller than one guarantees asymptotic stability, [2](https://www.sciencedirect.com/science/article/pii/S089360800700038X#fn2) which means that the dynamics caused by an input pulse eventually die out. It is introduced in [Jaeger (2001a)](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b13) as a loose bound for the echo state property of sigmoidal reservoirs. The idea of the echo state property is–informally–that the reservoir needs to exhibit dynamics between unstable behaviour (where the network dynamics drown out the information contained in the inputs) and too stable dynamics that retain no information about the inputs. The extension of this measure to spiking neural networks loses some of its relevance, but it does offer a comparison between reservoirs built from analog and spiking neurons that use weight matrices with the same global scaling. Also, note that for the following discussion the spiking reservoirs were built in the same way as the analog neurons in order to allow a fair comparison — meaning that the reservoirs were built using a random connectivity with a connection fraction of 0.5. This method of building reservoirs should be contrasted with the ‘LSM’ topology, where typically three-dimensional (3D) neural microcolumns are built where the probability of two neurons being connected is related to the Euclidian distance between them. The latter reservoir topology is far more sparse than the former.

[Fig. 1](https://www.sciencedirect.com/science/article/pii/S089360800700038X#fig1) shows the errors attained for the three benchmark problems described above as a function of reservoir size and spectral radius. For the figures on the left-hand side, reservoirs were created with a fixed spectral radius of 0.9 as per the guideline for ESNs, and for the figures on the right-hand side a reservoir size of 100 neurons was chosen. For the NARMA and memory capacity task, results for spiking reservoirs were omitted since these reservoirs are not suited for this problem because of the high-frequency nature of the signals, which cannot accurately be captured in spike trains using the filter-based coding scheme we used, and because the memory capacity measure cannot trivially be extended to spiking reservoirs, since it measures correlation between two continuous temporal signals. Also, results for BPDC-trained reservoirs are shown only for the NARMA task since the literature only describes timeseries prediction results and we were unable to get satisfactory results for the other problems.

![](https://ars.els-cdn.com/content/image/1-s2.0-S089360800700038X-gr1.jpg)

1.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S089360800700038X-gr1.jpg "Download full-size image")

Fig. 1. These figures show the influence of the node complexity on the performance for the speech recognition task, for linear, tanh, analog integrator, LIF and Booij nodes, on the left as a function of reservoir size, and on the right as a function of the spectral radius of the connection matrix.

For the speech task ([Fig. 1](https://www.sciencedirect.com/science/article/pii/S089360800700038X#fig1)), performance increases for larger reservoirs for all node types except linear, and memory limitations were reached before an optimum was found[3](https://www.sciencedirect.com/science/article/pii/S089360800700038X#fn3) — though we expect performance to eventually level out. Also, the temporal processing capabilities of spiking neurons offer a clear advantage, but the use of a synapse model does not offer any further improvement — perhaps this is because the timeconstants of the membrane and synapse are too similar to each other; see [Appendix B](https://www.sciencedirect.com/science/article/pii/S089360800700038X#appB). The figure on the right shows that, for sigmoidal neurons, the spectral radius is a significant parameter and the optimum is achieved for a spectral radius higher than one (around 1.1) (which is contrary to the claims in [Jaeger (2002)](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b15) that an optimal spectral radius lies close to one) but for spiking neurons it has no influence at all. This is probably due to the fact that the reservoir dynamics for spiking nodes are more controlled by the nonlinear effects and temporal integration properties of the spiking neurons, rather than the global scaling of the weight matrix.

For the memory capacity task ([Fig. 2](https://www.sciencedirect.com/science/article/pii/S089360800700038X#fig2)), the linear nodes show the highest memory capacity, which is an experimental confirmation of the theoretical result proved in [Jaeger (2001b)](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b14). Also, our results show that the memory capacity of analog integrator neurons is lower than that of sigmoidal neurons. This is caused by the fact that the integrating property of these reservoirs slows the dynamics down and thus the information on a very fast timescale contained in the input is lost. Thus, information on a slow timescale will be better preserved by analog integrator neurons, but quickly varying signals become muddled. Finally, the memory capacity of the reservoirs increases with size, since larger reservoirs will be able to store more information for a longer time due to the larger recurrent loops and higher dimensionality of the reservoir state. See Section [2.2](https://www.sciencedirect.com/science/article/pii/S089360800700038X#sec2.2) for more results on this.

![](https://ars.els-cdn.com/content/image/1-s2.0-S089360800700038X-gr2.jpg)

1.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S089360800700038X-gr2.jpg "Download full-size image")

Fig. 2. These figures show the influence of the node complexity on the performance for the memory capacity task, for linear, tanh and analog integrator nodes, on the left as a function of reservoir size, and on the right as a function of the spectral radius of the connection matrix.

Finally, the figures for the NARMA task ([Fig. 3](https://www.sciencedirect.com/science/article/pii/S089360800700038X#fig3)) indicate that reservoir size is not a very significant parameter for this task for any node type except for the tanh and integrator neurons where we see a slight increase in performance for larger reservoirs. Probably, the memory needed to accurately model the tenth-order system is already present in very small reservoirs, and the only thing that causes the difference in performance between the nodetypes is the type of the nonlinear mapping. The significance of the spectral radius as an indicator for performance is quite obvious for this task (lower plot). For this task, we see that the guideline of an optimal spectral radius close to one is not optimal for all the nodes. We find that the BPDC rule performs worse overall than ESNs, but this could be due to the sensitivity of the learning rule to parameter settings and our limited experience with it. Note also that this figure shows that the spectral radius is only an approximate measure of stability for sigmoidal reservoirs: the performance of the linear nodes falls dramatically when the spectral radius is larger than one–indicating a drastic change in the reservoir dynamics–whereas for sigmoidal and analog integrator neurons this decrease is far more gradual.

![](https://ars.els-cdn.com/content/image/1-s2.0-S089360800700038X-gr3.jpg)

1.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S089360800700038X-gr3.jpg "Download full-size image")

Fig. 3. These figures show the influence of the node complexity on the performance for the NARMA task, for linear, tanh, analog integrator nodes, and for the BPDC learning rule, on the left as a function of reservoir size, and on the right as a function of the spectral radius of the connection matrix.

### 2.2. Node memory versus reservoir memory

One of the key properties of reservoirs that sets them apart from more traditional approaches to classification or regression is their ability to retain information about the inputs for a certain time. This property is called the fading memory or echo state property in the context of LSMs and ESNs respectively, and is caused by the presence of recurrent connections inside the reservoir. Certain node types, however, possess some form of *internal* memory capability: the analog integrator neuron and both spiking neuron models (the LIF and Booij model).

When solving a task using reservoir computing techniques, the optimal value for the memory capability on both the node and the network level are determined by the timescales inherent to the problem. This means that a tradeoff needs to be made: one wants to have a reservoir that memorizes just enough information from the inputs, and this memory capability can be caused by the network size (larger networks have more memory) or the node memory. The NARMA task needs a memory of at least ten past timesteps (since the output is determined by input and outputs from up to ten timesteps ago), while the memory task needs more memory (up to 100 timesteps). Due to the complexity of the task, it is not easy to indicate the appropriate timescales for the speech recognition task (quite probably several timescales are at play there). In this section, we investigate the relation between both types of memory for the three benchmarks by using reservoirs built from analog integrator neurons and varying both reservoir size and the node memory.

[Fig. 4](https://www.sciencedirect.com/science/article/pii/S089360800700038X#fig4) shows the results for the NARMA benchmark as a function of both reservoir size and the retainment rate $<math><mi is="true">r</mi></math>$. These figures confirm the statement made earlier that the retainment rate has a negative effect on the performance of larger reservoirs for this task since it slows down the inherent timescale of the reservoir, and for this task–especially since the input is a random signal–rather fast dynamics are optimal. We also see the same independence of performance in relation to the reservoir size for retainment rates larger than zero, but for $<math><mi is="true">r</mi></math>$ approaching zero, there appears a decrease in performance for very small networks — a phenomenon that is not present for larger retainment rates (close to one). The lower plot of [Fig. 4](https://www.sciencedirect.com/science/article/pii/S089360800700038X#fig4) shows the variance on the performance for the reservoirs with a retainment rate of zero. Here we see that the variance is far larger for small reservoirs — this means that, for larger reservoirs, the readout is far more likely to be able to extract the relevant information from the reservoir dynamics, whereas for small reservoirs good candidates exist but many more perform badly. Thus, we conclude that for very small reservoirs and no node integration the memory caused by the reservoir size becomes insufficient to retain enough information about past inputs. However, this effect cannot be detected for higher retainment rates since the reservoir states are mainly driven by the internal network dynamics instead of the external input.

![](https://ars.els-cdn.com/content/image/1-s2.0-S089360800700038X-gr4.jpg)

1.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S089360800700038X-gr4.jpg "Download full-size image")

Fig. 4. Top plots show the reservoir size versus retainment rate $<math><mi is="true">r</mi></math>$ for the NARMA task. The bottom plot shows the variance of the performance for retainment rate $<math><mi is="true">r</mi><mo is="true">=</mo><mn is="true">0</mn></math>$ for the NARMA task.

The figure for the memory capacity as a function of reservoir size and retainment rate ([Fig. 5](https://www.sciencedirect.com/science/article/pii/S089360800700038X#fig5)) indicates as expected that larger reservoirs have a larger memory capacity. Also, as for the NARMA task, the information timescale present in the input signal that is relevant for the output is very quick since larger retainment rates cause a decrease of the memory capacity. Also, even though the landscape is more monotonic than for the NARMA task, one can see the same ‘attenuating’ effect of large retainment rates on the curves for reservoir size: the increase in memory capacity for larger reservoirs is far steeper for a retainment rate of zero than for $<math><mi is="true">r</mi></math>$ close to one.

![](https://ars.els-cdn.com/content/image/1-s2.0-S089360800700038X-gr5.jpg)

1.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S089360800700038X-gr5.jpg "Download full-size image")

Fig. 5. Reservoir size versus retainment rate $<math><mi is="true">r</mi></math>$ for the memorization task.

Finally, [Fig. 6](https://www.sciencedirect.com/science/article/pii/S089360800700038X#fig6) shows the results for the speech recognition task. Here, the influence of the reservoir size is more prominent than in the previous cases (note the different orientation of the error surface compared to the NARMA task). Also, the influence of the retainment rate is quite different compared to the previous two tasks. Here we see that quite large retainment rates are optimal — indicating the fact that as expected far slower input timescales are relevant for the performance of the classifier. These figures indicate that a very ‘slow’ or inert reservoir is beneficial for the performance, which might be expected considering the rather slow rate at which speech features change in relation to the sampling frequency.

![](https://ars.els-cdn.com/content/image/1-s2.0-S089360800700038X-gr6.jpg)

1.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S089360800700038X-gr6.jpg "Download full-size image")

Fig. 6. Reservoir size versus retainment rate $<math><mi is="true">r</mi></math>$ for the speech task.

### 2.3. Linking different bounds for the echo state property to network dynamics

In [Jaeger (2002)](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b15), two bounds are described for a reservoir built from sigmoidal neurons to have the echo state property. The first bound is based on the spectral radius $<math><mi is="true">ρ</mi></math>$ of the connection matrix and offers a necessary condition for the echo state property, namely that $<math><mi is="true">ρ</mi><mo is="true">&lt;</mo><mn is="true">1</mn></math>$, meaning that all eigenvalues lie within the unit circle on the complex plane. This condition expresses that the reservoir is locally asymptotically stable around the origin. The second bound uses the largest singular value $<math><mover accent="false" is="true"><mrow is="true"><mi is="true">σ</mi></mrow><mo accent="true" is="true">¯</mo></mover></math>$, and expresses a the sufficient condition for the echo state property as $<math><mover accent="false" is="true"><mrow is="true"><mi is="true">σ</mi></mrow><mo accent="true" is="true">¯</mo></mover><mo is="true">&lt;</mo><mn is="true">1</mn></math>$. The spectral radius $<math><mi is="true">ρ</mi></math>$ is used in [Jaeger (2002)](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b15) to suggest a heuristic method of constructing reservoirs: the idea is to start with a randomly connected network and to rescale the weights so that $<math><mi is="true">ρ</mi></math>$ is close to, but smaller than, one. Later, in [Buehner and Young (2006)](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b3) a tighter bound was proposed for constructing reservoirs, which is inspired by ideas from robust control theory. This condition uses the *structured singular value* $<math><mi is="true">μ</mi></math>$, and expresses the fact that, if $<math><mi is="true">μ</mi><mo is="true">&lt;</mo><mn is="true">1</mn></math>$, the reservoir is globally asymptotically stable. This bound for the echo state property is tighter than the spectral radius, and for some specific weight matrices it is even an exact bound (i.e. the condition is both necessary and sufficient).

The bounds described above supply a measure for the computational quality of a reservoir and can all be deduced from the weight matrix of the reservoir, i.e. without simulating it explicitly on some input signals. However, it is not clear how these stability bounds relate to the actual network dynamics. In this context, the idea of ‘*computation at the edge of chaos*’ is a recurring topic in literature on Reservoir Computing. Results from LSMs seem to indicate an optimal computational performance for reservoirs operating in a regime that lies between stable and chaotic behaviour ([Legenstein & Maass, 2005](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b21)), while Jaeger suggests that ESNs operate optimally in the stable regime but close to the border of instability ([Jaeger, 2002](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b15)), which is linked to the echo state property in the sense that a reservoir should exhibit sufficiently rich dynamics without drowning the information in chaotic behaviour.

One possible way of measuring the stability (or chaoticity) of an orbit through state space of a dynamic system is the Lyapunov exponent. The Lyapunov exponent is a measure for the exponential deviation in a certain direction of a trajectory, resulting from an infinitesimal disturbance in the state of the system. If the orbit is near an attractor, the effect of the disturbance will disappear and the Lyapunov exponent will be smaller than zero. In case the system drifts away from the orbit exponentially, the Lyapunov exponent is larger than zero and the orbit is unstable. Note that the Lyapunov exponent can be positive in one direction and negative in another.

A common definition of a *chaotic orbit* is then that if (i) the orbit is not asymptotically periodic, (ii) no Lyapunov exponent is exactly zero and (iii) the largest Lyapunov exponent is larger than zero, the orbit is chaotic, meaning that the orbit deviates exponentially in at least one dimension.

The $<math><mi is="true">k</mi></math>$th Lyapunov *number* $<math><msub is="true"><mrow is="true"><mi is="true">L</mi></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub></math>$ is related to the $<math><mi is="true">k</mi></math>$th Lyapunov exponent $<math><msub is="true"><mrow is="true"><mi is="true">h</mi></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub></math>$ through $<math><msub is="true"><mrow is="true"><mi is="true">L</mi></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub><mo is="true">=</mo><mo is="true">exp</mo><mrow is="true"><mo is="true">(</mo><msub is="true"><mrow is="true"><mi is="true">h</mi></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub><mo is="true">)</mo></mrow></math>$. Thus, if a trajectory is chaotic, at least one Lyapunov number will be greater than one. For every trajectory $<math><mstyle mathvariant="bold" is="true"><mi is="true">s</mi></mstyle><mrow is="true"><mo is="true">(</mo><mi is="true">t</mi><mo is="true">)</mo></mrow><mo is="true">,</mo><mi is="true">t</mi><mo is="true">=</mo><mn is="true">1</mn><mo is="true">,</mo><mo is="true">…</mo><mo is="true">,</mo><mi is="true">n</mi></math>$ of a dynamical system in state space, we can calculate $<math><mi is="true">k</mi><mo is="true">=</mo><mn is="true">1</mn><mo is="true">,</mo><mo is="true">…</mo><mo is="true">,</mo><mi is="true">m</mi></math>$ Lyapunov numbers (one for every dimension of the state) by considering a hypersphere in state space whose center follows the trajectory $<math><mstyle mathvariant="bold" is="true"><mi is="true">s</mi></mstyle><mrow is="true"><mo is="true">(</mo><mi is="true">t</mi><mo is="true">)</mo></mrow></math>$, and considering how it is transformed by the update function of the system. The hypersphere will evolve to a hyper-ellipsoid as it travels through state space. The Lyapunov numbers for the trajectory are then given by $<math><msub is="true"><mrow is="true"><mi is="true">L</mi></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub><mo is="true">=</mo><munder is="true"><mrow is="true"><mo is="true">lim</mo></mrow><mrow is="true"><mi is="true">n</mi><mo is="true">→</mo><mi is="true">∞</mi></mrow></munder><msup is="true"><mrow is="true"><mrow is="true"><mo is="true">(</mo><munderover accentunder="false" accent="false" is="true"><mrow is="true"><mi is="true">r</mi></mrow><mrow is="true"><mi is="true">k</mi></mrow><mrow is="true"><mi is="true">n</mi></mrow></munderover><mo is="true">)</mo></mrow></mrow><mrow is="true"><mn is="true">1</mn><mo is="true">/</mo><mi is="true">n</mi></mrow></msup><mtext is="true">,</mtext></math>$ where $<math><msubsup is="true"><mrow is="true"><mi is="true">r</mi></mrow><mrow is="true"><mi is="true">k</mi></mrow><mrow is="true"><mi is="true">n</mi></mrow></msubsup></math>$ is the length of $<math><mi is="true">k</mi></math>$th longest orthogonal axis of the hyper-ellipsoid at discrete timestep $<math><mi is="true">n</mi></math>$. The value of these lengths can be calculated as follows. Let $<math><msub is="true"><mrow is="true"><mi is="true">J</mi></mrow><mrow is="true"><mi is="true">n</mi></mrow></msub></math>$ denote the Jacobian of the $<math><mi is="true">n</mi></math>$th iterative application of the map $<math><mstyle mathvariant="bold" is="true"><mi is="true">f</mi></mstyle></math>$. The length of the axes of the hyper-ellipsoid is then given by the square root of the eigenvalues of $<math><msub is="true"><mrow is="true"><mi is="true">J</mi></mrow><mrow is="true"><mi is="true">n</mi></mrow></msub><msubsup is="true"><mrow is="true"><mi is="true">J</mi></mrow><mrow is="true"><mi is="true">n</mi></mrow><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">T</mi></mstyle></mrow></msubsup></math>$ (see [Alligood, Sauer, and Yorke (1996)](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b1) for a more elaborate discussion). Thus, the Lyapunov number $<math><msub is="true"><mrow is="true"><mi is="true">L</mi></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub></math>$ expresses the exponential expansion ($<math><msub is="true"><mrow is="true"><mi is="true">L</mi></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub><mo is="true">&gt;</mo><mn is="true">1</mn></math>$) or contraction ($<math><msub is="true"><mrow is="true"><mi is="true">L</mi></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub><mo is="true">&lt;</mo><mn is="true">1</mn></math>$) of a unit sphere under the map $<math><mstyle mathvariant="bold" is="true"><mi is="true">f</mi></mstyle></math>$. Note that this method assumes that the limit above converges.

The Lyapunov definition given above is only suited for autonomous systems (or driven systems where the driving force can also be modeled as state variables, rendering the system autonomous). But in the case of reservoir computing we have systems that are constantly driven by complex, even random, input. The standard definition of a Lyapunov exponent as the existence of a limit will therefore not be applicable because no steady state is reached due to the continuously changing input and state trajectory.

In [Legenstein and Maass (2005)](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b21), the Lyapunov exponent is measured empirically for a spiking reservoir by calculating the average Euclidian distance of the reservoir states resulting from time-shifting a single input spike over 0.5 ms. To our knowledge, this is the only investigation of the reservoir dynamics using the Lyapunov criterion, and for spiking neurons this experimental approach is the only way to formulate any conclusions about the stability of the system due to the complexity and time-dependence of the model. This method can be seen as the disturbance of an autonomous system where the exponential state deviation is an approximation of the Lyapunov exponent. A considerable disadvantage of this method is that it is very time-consuming.

In the case of sigmoidal neurons, however, we can calculate a measure analytically that is closely related to the Lyapunov exponent, due to the simpler neuron model. The Jacobian matrix of $<math><mstyle mathvariant="bold" is="true"><mi is="true">f(s)</mi></mstyle></math>$ at a point $<math><mstyle mathvariant="bold" is="true"><mi is="true">s</mi></mstyle><mo is="true">∈</mo><msup is="true"><mrow is="true"><mi mathvariant="double-struck" is="true">R</mi></mrow><mrow is="true"><mi is="true">n</mi></mrow></msup></math>$ is given by $<math><mstyle mathvariant="bold" is="true"><mi is="true">Df(s)</mi></mstyle><mo is="true">=</mo><mrow is="true"><mo is="true">(</mo><mtable is="true"><mtr is="true"><mtd columnalign="center" is="true"><mfrac is="true"><mrow is="true"><mi is="true">∂</mi><msub is="true"><mrow is="true"><mi is="true">f</mi></mrow><mrow is="true"><mn is="true">1</mn></mrow></msub></mrow><mrow is="true"><mi is="true">∂</mi><msub is="true"><mrow is="true"><mi is="true">s</mi></mrow><mrow is="true"><mn is="true">1</mn></mrow></msub></mrow></mfrac><mrow is="true"><mo is="true">(</mo><mstyle mathvariant="bold" is="true"><mi is="true">s</mi></mstyle><mo is="true">)</mo></mrow></mtd><mtd columnalign="center" is="true"><mo is="true">⋯</mo></mtd><mtd columnalign="center" is="true"><mfrac is="true"><mrow is="true"><mi is="true">∂</mi><msub is="true"><mrow is="true"><mi is="true">f</mi></mrow><mrow is="true"><mn is="true">1</mn></mrow></msub></mrow><mrow is="true"><mi is="true">∂</mi><msub is="true"><mrow is="true"><mi is="true">s</mi></mrow><mrow is="true"><mi is="true">n</mi></mrow></msub></mrow></mfrac><mrow is="true"><mo is="true">(</mo><mstyle mathvariant="bold" is="true"><mi is="true">s</mi></mstyle><mo is="true">)</mo></mrow></mtd></mtr><mtr is="true"><mtd columnalign="center" is="true"><mfrac is="true"><mrow is="true"><mi is="true">∂</mi><msub is="true"><mrow is="true"><mi is="true">f</mi></mrow><mrow is="true"><mi is="true">n</mi></mrow></msub></mrow><mrow is="true"><mi is="true">∂</mi><msub is="true"><mrow is="true"><mi is="true">s</mi></mrow><mrow is="true"><mn is="true">1</mn></mrow></msub></mrow></mfrac><mrow is="true"><mo is="true">(</mo><mstyle mathvariant="bold" is="true"><mi is="true">s</mi></mstyle><mo is="true">)</mo></mrow></mtd><mtd columnalign="center" is="true"><mo is="true">⋯</mo></mtd><mtd columnalign="center" is="true"><mfrac is="true"><mrow is="true"><mi is="true">∂</mi><msub is="true"><mrow is="true"><mi is="true">f</mi></mrow><mrow is="true"><mi is="true">n</mi></mrow></msub></mrow><mrow is="true"><mi is="true">∂</mi><msub is="true"><mrow is="true"><mi is="true">s</mi></mrow><mrow is="true"><mi is="true">n</mi></mrow></msub></mrow></mfrac><mrow is="true"><mo is="true">(</mo><mstyle mathvariant="bold" is="true"><mi is="true">s</mi></mstyle><mo is="true">)</mo></mrow><mtext is="true">.</mtext></mtd></mtr></mtable><mo is="true">)</mo></mrow></math>$ A generic sigmoidal reservoir is described by the following map: $<math><mstyle mathvariant="bold" is="true"><mi is="true">s</mi></mstyle><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">+</mo><mn is="true">1</mn><mo is="true">)</mo></mrow><mo is="true">=</mo><mstyle mathvariant="bold" is="true"><mi is="true">f</mi></mstyle><mrow is="true"><mo is="true">(</mo><mstyle mathvariant="bold" is="true"><mi is="true">s</mi></mstyle><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">)</mo></mrow><mo is="true">)</mo></mrow><mo is="true">=</mo><mo is="true">tanh</mo><mrow is="true"><mo is="true">(</mo><mstyle mathvariant="bold" is="true"><mi is="true">s</mi></mstyle><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">)</mo></mrow><mo is="true">∗</mo><mstyle mathvariant="bold" is="true"><mi is="true">W</mi></mstyle><mo is="true">)</mo></mrow><mo is="true">=</mo><mrow is="true"><mo is="true">[</mo><mtable is="true"><mtr is="true"><mtd columnalign="center" is="true"><mo is="true">tanh</mo><mrow is="true"><mo is="true">(</mo><munderover accentunder="false" accent="false" is="true"><mrow is="true"><mo is="true">∑</mo></mrow><mrow is="true"><mi is="true">i</mi><mo is="true">=</mo><mn is="true">1</mn></mrow><mrow is="true"><mi is="true">n</mi></mrow></munderover><msub is="true"><mrow is="true"><mi is="true">w</mi></mrow><mrow is="true"><mn is="true">1</mn><mi is="true">i</mi></mrow></msub><msub is="true"><mrow is="true"><mstyle mathvariant="bold" is="true"><mi is="true">s</mi></mstyle></mrow><mrow is="true"><mn is="true">1</mn></mrow></msub><mo is="true">)</mo></mrow></mtd><mtd columnalign="center" is="true"><mo is="true">⋯</mo></mtd><mtd columnalign="center" is="true"><mo is="true">tanh</mo><mrow is="true"><mo is="true">(</mo><munderover accentunder="false" accent="false" is="true"><mrow is="true"><mo is="true">∑</mo></mrow><mrow is="true"><mi is="true">i</mi><mo is="true">=</mo><mn is="true">1</mn></mrow><mrow is="true"><mi is="true">n</mi></mrow></munderover><msub is="true"><mrow is="true"><mi is="true">w</mi></mrow><mrow is="true"><mi is="true">n</mi><mi is="true">i</mi></mrow></msub><msub is="true"><mrow is="true"><mstyle mathvariant="bold" is="true"><mi is="true">s</mi></mstyle></mrow><mrow is="true"><mi is="true">n</mi></mrow></msub><mo is="true">)</mo></mrow></mtd></mtr></mtable><mo is="true">]</mo></mrow><mtext is="true">.</mtext></math>$ When we compute the Jacobian of the above map $<math><mstyle mathvariant="bold" is="true"><mi is="true">f</mi></mstyle><mrow is="true"><mo is="true">(</mo><mstyle mathvariant="bold" is="true"><mi is="true">s</mi></mstyle><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">)</mo></mrow><mo is="true">)</mo></mrow></math>$, this gives (2)$<math><mstyle mathvariant="bold" is="true"><mi is="true">Df</mi></mstyle><mrow is="true"><mo is="true">(</mo><mstyle mathvariant="bold" is="true"><mi is="true">s</mi></mstyle><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">)</mo></mrow><mo is="true">)</mo></mrow><mo is="true">=</mo><mrow is="true"><mo is="true">[</mo><mtable is="true"><mtr is="true"><mtd columnalign="center" is="true"><mrow is="true"><mo is="true">[</mo><mn is="true">1</mn><mo is="true">−</mo><msup is="true"><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">tanh</mi></mstyle></mrow><mrow is="true"><mn is="true">2</mn></mrow></msup><mrow is="true"><mo is="true">(</mo><munderover accentunder="false" accent="false" is="true"><mrow is="true"><mo is="true">∑</mo></mrow><mrow is="true"><mi is="true">i</mi><mo is="true">=</mo><mn is="true">1</mn></mrow><mrow is="true"><mi is="true">n</mi></mrow></munderover><msub is="true"><mrow is="true"><mi is="true">w</mi></mrow><mrow is="true"><mn is="true">1</mn><mi is="true">i</mi></mrow></msub><msub is="true"><mrow is="true"><mi is="true">s</mi></mrow><mrow is="true"><mn is="true">1</mn></mrow></msub><mo is="true">)</mo></mrow><mo is="true">]</mo></mrow><msub is="true"><mrow is="true"><mi is="true">w</mi></mrow><mrow is="true"><mn is="true">11</mn></mrow></msub></mtd><mtd columnalign="center" is="true"><mo is="true">⋯</mo></mtd><mtd columnalign="center" is="true"><mrow is="true"><mo is="true">[</mo><mn is="true">1</mn><mo is="true">−</mo><msup is="true"><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">tanh</mi></mstyle></mrow><mrow is="true"><mn is="true">2</mn></mrow></msup><mrow is="true"><mo is="true">(</mo><munderover accentunder="false" accent="false" is="true"><mrow is="true"><mo is="true">∑</mo></mrow><mrow is="true"><mi is="true">i</mi><mo is="true">=</mo><mn is="true">1</mn></mrow><mrow is="true"><mi is="true">n</mi></mrow></munderover><msub is="true"><mrow is="true"><mi is="true">w</mi></mrow><mrow is="true"><mn is="true">1</mn><mi is="true">i</mi></mrow></msub><msub is="true"><mrow is="true"><mi is="true">s</mi></mrow><mrow is="true"><mn is="true">1</mn></mrow></msub><mo is="true">)</mo></mrow><mo is="true">]</mo></mrow><msub is="true"><mrow is="true"><mi is="true">w</mi></mrow><mrow is="true"><mn is="true">1</mn><mi is="true">n</mi></mrow></msub></mtd></mtr><mtr is="true"><mtd columnalign="center" is="true"><mo is="true">⋮</mo></mtd><mtd columnalign="center" is="true"></mtd><mtd columnalign="center" is="true"><mo is="true">⋮</mo></mtd></mtr><mtr is="true"><mtd columnalign="center" is="true"><mrow is="true"><mo is="true">[</mo><mn is="true">1</mn><mo is="true">−</mo><msup is="true"><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">tanh</mi></mstyle></mrow><mrow is="true"><mn is="true">2</mn></mrow></msup><mrow is="true"><mo is="true">(</mo><munderover accentunder="false" accent="false" is="true"><mrow is="true"><mo is="true">∑</mo></mrow><mrow is="true"><mi is="true">i</mi><mo is="true">=</mo><mn is="true">1</mn></mrow><mrow is="true"><mi is="true">n</mi></mrow></munderover><msub is="true"><mrow is="true"><mi is="true">w</mi></mrow><mrow is="true"><mi is="true">n</mi><mi is="true">i</mi></mrow></msub><msub is="true"><mrow is="true"><mi is="true">s</mi></mrow><mrow is="true"><mi is="true">n</mi></mrow></msub><mo is="true">)</mo></mrow><mo is="true">]</mo></mrow><msub is="true"><mrow is="true"><mi is="true">w</mi></mrow><mrow is="true"><mi is="true">n</mi><mn is="true">1</mn></mrow></msub></mtd><mtd columnalign="center" is="true"><mo is="true">⋯</mo></mtd><mtd columnalign="center" is="true"><mrow is="true"><mo is="true">[</mo><mn is="true">1</mn><mo is="true">−</mo><msup is="true"><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">tanh</mi></mstyle></mrow><mrow is="true"><mn is="true">2</mn></mrow></msup><mrow is="true"><mo is="true">(</mo><munderover accentunder="false" accent="false" is="true"><mrow is="true"><mo is="true">∑</mo></mrow><mrow is="true"><mi is="true">i</mi><mo is="true">=</mo><mn is="true">1</mn></mrow><mrow is="true"><mi is="true">n</mi></mrow></munderover><msub is="true"><mrow is="true"><mi is="true">w</mi></mrow><mrow is="true"><mi is="true">n</mi><mi is="true">i</mi></mrow></msub><msub is="true"><mrow is="true"><mi is="true">s</mi></mrow><mrow is="true"><mi is="true">n</mi></mrow></msub><mo is="true">)</mo></mrow><mo is="true">]</mo></mrow><msub is="true"><mrow is="true"><mi is="true">w</mi></mrow><mrow is="true"><mi is="true">n</mi><mi is="true">n</mi></mrow></msub></mtd></mtr></mtable><mo is="true">]</mo></mrow></math>$(3)$<math><mo is="true">=</mo><mrow is="true"><mo is="true">[</mo><mtable is="true"><mtr is="true"><mtd columnalign="center" is="true"><mrow is="true"><mo is="true">[</mo><mn is="true">1</mn><mo is="true">−</mo><msubsup is="true"><mrow is="true"><mi is="true">s</mi></mrow><mrow is="true"><mn is="true">1</mn></mrow><mrow is="true"><mn is="true">2</mn></mrow></msubsup><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">)</mo></mrow><mo is="true">]</mo></mrow><msub is="true"><mrow is="true"><mi is="true">w</mi></mrow><mrow is="true"><mn is="true">11</mn></mrow></msub></mtd><mtd columnalign="center" is="true"><mo is="true">⋯</mo></mtd><mtd columnalign="center" is="true"><mrow is="true"><mo is="true">[</mo><mn is="true">1</mn><mo is="true">−</mo><msubsup is="true"><mrow is="true"><mi is="true">s</mi></mrow><mrow is="true"><mn is="true">1</mn></mrow><mrow is="true"><mn is="true">2</mn></mrow></msubsup><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">)</mo></mrow><mo is="true">]</mo></mrow><msub is="true"><mrow is="true"><mi is="true">w</mi></mrow><mrow is="true"><mn is="true">1</mn><mi is="true">n</mi></mrow></msub></mtd></mtr><mtr is="true"><mtd columnalign="center" is="true"><mo is="true">⋮</mo></mtd><mtd columnalign="center" is="true"></mtd><mtd columnalign="center" is="true"><mo is="true">⋮</mo></mtd></mtr><mtr is="true"><mtd columnalign="center" is="true"><mrow is="true"><mo is="true">[</mo><mn is="true">1</mn><mo is="true">−</mo><msubsup is="true"><mrow is="true"><mi is="true">s</mi></mrow><mrow is="true"><mi is="true">n</mi></mrow><mrow is="true"><mn is="true">2</mn></mrow></msubsup><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">)</mo></mrow><mo is="true">]</mo></mrow><msub is="true"><mrow is="true"><mi is="true">w</mi></mrow><mrow is="true"><mi is="true">n</mi><mn is="true">1</mn></mrow></msub></mtd><mtd columnalign="center" is="true"><mo is="true">⋯</mo></mtd><mtd columnalign="center" is="true"><mrow is="true"><mo is="true">[</mo><mn is="true">1</mn><mo is="true">−</mo><msubsup is="true"><mrow is="true"><mi is="true">s</mi></mrow><mrow is="true"><mi is="true">n</mi></mrow><mrow is="true"><mn is="true">2</mn></mrow></msubsup><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">)</mo></mrow><mo is="true">]</mo></mrow><msub is="true"><mrow is="true"><mi is="true">w</mi></mrow><mrow is="true"><mi is="true">n</mi><mi is="true">n</mi></mrow></msub><mtext is="true">.</mtext></mtd></mtr></mtable><mo is="true">]</mo></mrow><mtext is="true">.</mtext></math>$ The above matrix offers an analytical expression for the Jacobian matrix $<math><mi is="true">J</mi></math>$, which in turn allows us to approximate the Lyapunov numbers. It is indeed an approximation, because in this case we are dealing with an input driven system and we cannot compute the limit for $<math><mi is="true">k</mi><mo is="true">→</mo><mi is="true">∞</mi></math>$. We will therefore refer to this measure as the pseudo-Lyapunov exponent $<math><msub is="true"><mrow is="true"><mover accent="true" is="true"><mrow is="true"><mi is="true">h</mi></mrow><mrow is="true"><mo is="true">̃</mo></mrow></mover></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub></math>$. We calculate the largest pseudo-Lyapunov exponent of a trajectory of $<math><mi is="true">N</mi></math>$ timesteps as (4)$<math><msub is="true"><mrow is="true"><mover accent="true" is="true"><mrow is="true"><mi is="true">h</mi></mrow><mrow is="true"><mo is="true">̃</mo></mrow></mover></mrow><mrow is="true"><mo is="true">max</mo></mrow></msub><mo is="true">=</mo><munder is="true"><mrow is="true"><mo is="true">max</mo></mrow><mrow is="true"><mi is="true">k</mi></mrow></munder><munderover accentunder="false" accent="false" is="true"><mrow is="true"><mo is="true">∏</mo></mrow><mrow is="true"><mi is="true">n</mi><mo is="true">=</mo><mn is="true">1</mn></mrow><mrow is="true"><mi is="true">N</mi></mrow></munderover><msup is="true"><mrow is="true"><mrow is="true"><mo is="true">(</mo><msub is="true"><mrow is="true"><mi is="true">r</mi></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub><mo is="true">)</mo></mrow></mrow><mrow is="true"><mn is="true">1</mn><mo is="true">/</mo><mi is="true">n</mi></mrow></msup><mtext is="true">,</mtext></math>$ where $<math><msub is="true"><mrow is="true"><mi is="true">r</mi></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub><mo is="true">=</mo><msqrt is="true"><mrow is="true"><mrow is="true"><mo is="true">|</mo><msub is="true"><mrow is="true"><mi is="true">λ</mi></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub><mo is="true">|</mo></mrow></mrow></msqrt></math>$, $<math><msub is="true"><mrow is="true"><mi is="true">λ</mi></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub></math>$ being the $<math><mi is="true">k</mi></math>$th eigenvalue of $<math><msub is="true"><mrow is="true"><mi is="true">J</mi></mrow><mrow is="true"><mi is="true">n</mi></mrow></msub><msubsup is="true"><mrow is="true"><mi is="true">J</mi></mrow><mrow is="true"><mi is="true">n</mi></mrow><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">T</mi></mstyle></mrow></msubsup></math>$.

Due to the analytical derivation of this rule, it can easily be calculated, and is exact. An extra speed-up can be attained by calculating the pseudo-exponents in a sampled manner, in our case every ten timesteps. This proved to be an accurate approximation. We will demonstrate that this measure is an accurate indicator of reservoir dynamics and performance. Also, to our knowledge, this is the only analytically computed measure of reservoir *and* task-dependent dynamics.

To illustrate the relationship between these different bounds and reservoir performance for certain tasks, we evaluated the performance of different reservoirs on the NARMA ([Fig. 7](https://www.sciencedirect.com/science/article/pii/S089360800700038X#fig7)), memory ([Fig. 8](https://www.sciencedirect.com/science/article/pii/S089360800700038X#fig8)) and speech recognition benchmark ([Fig. 9](https://www.sciencedirect.com/science/article/pii/S089360800700038X#fig9)) by constructing the weight matrix of the reservoirs and then rescaling it so that either the spectral radius, LSV or $<math><mi is="true">μ</mi></math>$ has a specified value. [4](https://www.sciencedirect.com/science/article/pii/S089360800700038X#fn4) For each of these reservoirs, the largest pseudo-Lyapunov exponent $<math><msub is="true"><mrow is="true"><mover accent="true" is="true"><mrow is="true"><mi is="true">h</mi></mrow><mrow is="true"><mo is="true">̃</mo></mrow></mover></mrow><mrow is="true"><mo is="true">max</mo></mrow></msub></math>$ was also measured for every orbit and averaged across all input timeseries.

![](https://ars.els-cdn.com/content/image/1-s2.0-S089360800700038X-gr7.jpg)

1.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S089360800700038X-gr7.jpg "Download full-size image")

Fig. 7. The top figure shows the performance on the NARMA task as a function of different reservoir metrics. The bottom figure shows the corresponding pseudo-Lyapunov exponents.

![](https://ars.els-cdn.com/content/image/1-s2.0-S089360800700038X-gr8.jpg)

1.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S089360800700038X-gr8.jpg "Download full-size image")

Fig. 8. The top figure shows the performance on the memory capacity task as a function of different reservoir metrics. The bottom figure shows the corresponding pseudo-Lyapunov exponents.

![](https://ars.els-cdn.com/content/image/1-s2.0-S089360800700038X-gr9.jpg)

1.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S089360800700038X-gr9.jpg "Download full-size image")

Fig. 9. The top figure shows the performance on the speech recognition task as a function of different reservoir metrics. The bottom figure shows the corresponding pseudo-Lyapunov exponents.

In all three cases, the optimal value for the $<math><mi is="true">μ</mi></math>$ parameter lies between that of the spectral radius and of the LSV (which was expected since the spectral radius and LSV are a lower and upper bound for the echo state property), but it is significantly higher than one — which indicates that the reservoir is not globally asymptotically stable. This is also confirmed when the corresponding pseudo-Lyapunov exponent is measured, indicated by the dashed lines on the figure; it appears that the system is on average state-expanding for the orbits caused by the inputs for this task and the pseudo-Lyapunov exponent for the optimal values of the different metrics is very similar for both benchmarks and lies around 0.7, which indicates a dynamic regime: on average the trajectory locally shows exponential deviation in at least one direction. Note that the $<math><msub is="true"><mrow is="true"><mover accent="true" is="true"><mrow is="true"><mi is="true">h</mi></mrow><mrow is="true"><mo is="true">̃</mo></mrow></mover></mrow><mrow is="true"><mo is="true">max</mo></mrow></msub></math>$\-curves are very similar for the NARMA and memory capacity tasks, since in both cases the input to the reservoirs is a uniform random signal. However, the fact that the plots for the speech recognition task are very similar adds to the validity of the pseudo-Lyapunov exponent as a measure of input-dependent reservoir dynamics. Note also that a largest pseudo-Lyapunov exponent larger than zero does not mean that a system is chaotic.

## 3\. Reservoir computing toolbox

In this section, we will describe the RC toolbox (see [Fig. 10](https://www.sciencedirect.com/science/article/pii/S089360800700038X#fig10)) we have used for the work presented here, and which was developed at our laboratory. The toolbox is written in Matlab, is open source[5](https://www.sciencedirect.com/science/article/pii/S089360800700038X#fn5) and it offers a user-friendly interface for the simulation of all common reservoir computing implementations, such as the LSM, the ESN and the BPDC learning rule. Every parameter relevant to an experiment is set in a global configuration file, and *sweeps* across parameter ranges can be easily done. When multiple parameter ranges are specified, every possible combination will be simulated, which allows a detailed exploration of the performance for a certain benchmark in a certain area of the parameter space.

![](https://ars.els-cdn.com/content/image/1-s2.0-S089360800700038X-gr10.jpg)

1.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S089360800700038X-gr10.jpg "Download full-size image")

Fig. 10. Overview of the simulation pipeline for the RC toolbox.

Usually, an experiment consists of a sweep across a certain parameter range, whereby every point in parameter space is simulated a number of times (*runs*) to capture the variance due to the stochastic construction of the networks. Every single run itself is set up as a modular pipeline, where every step can be configured and where new modules can easily be added (for instance a new benchmark test or reservoir construction algorithm). Plotting utilities are provided that yield the mean performance or error (according to the specified scoring function) and their standard deviation. [6](https://www.sciencedirect.com/science/article/pii/S089360800700038X#fn6) In the following subsections, we will introduce the different stages of the toolbox and discuss their possibilities.

### 3.1. Benchmark tests

The toolbox includes some of the benchmark tests that have been described in RC literature, including the Mackey–Glass timeseries prediction ([Steil, 2005](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b40)), the isolated spoken digit recognition task from [Verstraeten et al. (2005)](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b48), the NARMA task described in [Jaeger (2003)](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b16), [Steil (2005)](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b40) and others. This stage is easily extended to other datasets. Depending on the selected benchmark test, at least two input timeseries vectors and corresponding desired output vectors are generated. In case the reservoir is built from spiking neurons and the input is analog, a spike coding algorithm can be applied to convert the timeseries to spike trains. The toolbox offers three coding hypotheses: a simple rate coding scheme where the spike trains are generated by a Poisson process with the instantaneous firing rate equal to the analog value being encoded, a scheme that uses a Leaky Integrate and Fire neuron to perform the coding where the analog timeseries is fed into the neuron as a membrane current, and finally BSA ([Schrauwen & Van Campenhout, 2003](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b37)), a fast filter-based coding scheme that introduces a low amount of noise in the spiketrain compared to other methods.

### 3.2. Reservoir generation

Reservoirs are constructed in a stochastic manner, and the search for a method to construct a priori suitable reservoirs that are guaranteed or likely to offer a certain performance is the topic of much research ([Jaeger, 2005](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b17)). Several ad hoc methods that all yield satisfactory results have been proposed in the literature. For instance, [Maass et al. (2002)](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b26) construct their reservoirs in a biologically inspired way, whereby the nodes of the reservoir are placed on a 3D lattice (based on the *microcolumnar* structures found in the cortex), and the probability of a connection existing between two nodes $<math><mi is="true">a</mi></math>$ and $<math><mi is="true">b</mi></math>$ is given by $<math><msub is="true"><mrow is="true"><mi is="true">P</mi></mrow><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">conn</mi></mstyle></mrow></msub><mrow is="true"><mo is="true">(</mo><mi is="true">a</mi><mo is="true">,</mo><mi is="true">b</mi><mo is="true">)</mo></mrow><mo is="true">=</mo><mi is="true">C</mi><mo is="true">⋅</mo><msup is="true"><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">e</mi></mstyle></mrow><mrow is="true"><mfrac is="true"><mrow is="true"><mo is="true">−</mo><msup is="true"><mrow is="true"><mi is="true">D</mi></mrow><mrow is="true"><mn is="true">2</mn></mrow></msup><mrow is="true"><mo is="true">(</mo><mi is="true">a</mi><mo is="true">,</mo><mi is="true">b</mi><mo is="true">)</mo></mrow></mrow><mrow is="true"><msup is="true"><mrow is="true"><mi is="true">λ</mi></mrow><mrow is="true"><mn is="true">2</mn></mrow></msup></mrow></mfrac></mrow></msup></math>$, with $<math><mi is="true">D</mi><mrow is="true"><mo is="true">(</mo><mi is="true">a</mi><mo is="true">,</mo><mi is="true">b</mi><mo is="true">)</mo></mrow></math>$ the distance between the nodes and $<math><mi is="true">C</mi></math>$ and $<math><mi is="true">λ</mi></math>$ parameters that control the reservoir connectivity and thus its dynamics. Several other construction heuristics for reservoir were proposed and tested by Jaeger, including random assignment of weights from a small set or a network with a certain fraction of nonzero, normally distributed weights. The toolbox offers a generic method of generating reservoirs that is split into several distinct steps.

•

The connectivity is determined, i.e. which neurons are connected to each other. A wide range of possibilities is supplied, which includes a regular 2D or 3D lattice, with optional rewiring ([Watts & Strogatz, 1998](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b49)) (which yields small world networks[7](https://www.sciencedirect.com/science/article/pii/S089360800700038X#fn7) ([Watts, 1999](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b50))) or a randomly connected network with a certain connection fraction.

•

Weights are assigned to the connections according to some heuristic. For instance, they can be drawn from a normal distribution or taken from a discrete set of values.

•

The global weight matrix can then be rescaled according to some measure, such as the spectral radius, largest single value or $<math><mi is="true">μ</mi></math>$ (ssv) value.

Using this generic reservoir generation method, all reservoir topologies currently described in the literature can be created as well as other novel topologies.

### 3.3. Possible nodetypes

Once the weight matrix of the network is determined, the reservoir can be simulated. The toolbox implements the simulation of a wide variety of neural models, ranging from very simple linear nodes, over analog integrator neurons up to spiking neural models. The simulation occurs either inside Matlab itself in the case of analog neurons, or by using a MEX interface to an external event simulator for spiking neural networks called ESSpiNN developed at our laboratory ([D’Haene, Schrauwen, & Stroobandt, 2006](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b7)). This simulator offers a rich subset of the neural models possible in CSIM ([Natschläger, Markram, & Maass, 2002](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b33), chap. 9),[8](https://www.sciencedirect.com/science/article/pii/S089360800700038X#fn8) but it is event-based as opposed to timestep-based, which gives a much more efficient, fast and accurate simulation of spiking neural networks for simple neuron models. ESSpiNN can simulate Leaky Integrate and Fire neurons, optionally with one or multiple exponential synapse models ([Gerstner & Kistler, 2002](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b10)), intrinsic plasticity ([Triesch, 2004](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b45)), Spike Time Dependent Plasticity ([Markram, Lübke, Frotscher, & Sakmann, 1997](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b29)) or dynamic synapses ([Markram, Pikus, Gupta, & Tsodyks, 1998](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b30)). This means that all reservoir node types described in the literature are available for simulation.

### 3.4. The output pipeline

The reservoir response for each input timeseries is recorded during simulation and–in case the nodes are spiking neural models–low-pass filtered to mimic the operation of a neuron membrane (as described in [Legenstein and Maass (2005)](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b21)). This yields a time-dependent signal for every neuron in the reservoir, which can optionally be resampled at a lower rate dt\_resample. The result is a large matrix of size $<math><mi is="true">N</mi><mo is="true">×</mo><msub is="true"><mrow is="true"><mi is="true">T</mi></mrow><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">rsmp</mi></mstyle></mrow></msub></math>$, with $<math><msub is="true"><mrow is="true"><mi is="true">T</mi></mrow><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">rsmp</mi></mstyle></mrow></msub></math>$ the number of timesteps the simulation has run for in units of dt\_resample. This matrix is multiplied with the weight matrix of a linear or nonlinear regression function of size $<math><mi is="true">N</mi><mo is="true">×</mo><msub is="true"><mrow is="true"><mi is="true">N</mi></mrow><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">out</mi></mstyle></mrow></msub></math>$, where $<math><msub is="true"><mrow is="true"><mi is="true">N</mi></mrow><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">out</mi></mstyle></mrow></msub></math>$ is the number of classes in the case of classification, or the dimensionality of the output vector in the case of a regression task. This results in an $<math><msub is="true"><mrow is="true"><mi is="true">N</mi></mrow><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">out</mi></mstyle></mrow></msub><mo is="true">×</mo><msub is="true"><mrow is="true"><mi is="true">T</mi></mrow><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">rsmp</mi></mstyle></mrow></msub></math>$ matrix, which can then optionally be fed into a post-processing pipeline, consisting of a first nonlinearity, a filtering operation, and a second nonlinearity. These last three steps allow one to transform the signals spatially (using the nonlinearities) or temporally (using the filter). Examples for the nonlinearity operation include the identity function (i.e. no nonlinear operation), the $<math><mo is="true">tanh</mo><mrow is="true"><mo is="true">(</mo><mo is="true">)</mo></mrow></math>$ function, the sign function or winner-take-all across all timesteps. The filtering operation could consist of a low-pass filter with a given timeconstant, or a simple mean operation across all timesteps. In the case of the speech recognition task, for instance, the post-processing pipeline consists of a mean operation followed by winner-take-all. The modular structure of the post-processing pipeline allows the easy addition of other functions.

The BPDC learning rule is also implemented in the toolbox, and all benchmark and reservoir generation functions can be used with this learning rule.

## 4\. Conclusions and future work

In this contribution, we have presented an experimental investigation of the different node types currently described, for a broad range of parameter settings and for a variety of tasks. It appears that, for the speech task, the use of spiking reservoirs is quite beneficial, and that the reservoir size has a significant influence on the performance. Also, for this task, the optimal value for the spectral radius is larger than one, contrary to previous results, and this parameter has no influence on performance for spiking reservoirs. For the memorization task, we found a monotonic increase of the memory capacity as a function of the reservoir size, and also a negative effect of a retainment rate larger than zero. We have found a strong dependence on the spectral radius for analog neurons and an optimum for a spectral radius of one. Similar results were found for the NARMA task. Further, we investigated the influence of the memory function within the nodes and within the reservoir on the reservoir performance and have illustrated the tradeoff between network and node memory for three tasks with very different memory requirements.

We also empirically investigated the relation between several bounds for the echo state property described in the literature and the network dynamics by analytically calculating an approximation of the Lyapunov exponent. This pseudo-Lyapunov exponent is an accurate measure of the task-dependent network dynamics and also a very good indicator of the performance on all of the benchmark tests. We investigated the link between the pseudo-Lyapunov exponents and static bounds based strictly on the weight matrix of the reservoir, and found that optimal values of these bounds correspond to the same exponent value.

Finally, we described the toolbox we used for this work, that offers all current implementations of reservoir computing described in the literature, and that extends this spectrum with additional benchmark problems, network generation algorithms, neural models and post-processing methods. This toolbox allows the user-friendly simulation of a broad range of reservoir types and topologies, the easy optimization of network parameters and a structured way of storing and plotting simulation results.

Future research work includes a thorough investigation of the noise robustness of different neural models — one can hypothesize that spiking neural models are more noise robust due to their inherent filtering behaviour. Also, research into the performance of novel network topologies (such as scale-free networks) is a potential direction for future work, since the network dynamics are largely determined by the connection topology. Finally, we plan to extend the research of the pseudo-Lyapunov exponent as a measure of network dynamics to other benchmark types and reservoir topologies.

## Acknowledgements

David Verstraeten and Michiel D’Haene are sponsored by the Institute for the Promotion of Innovation through Science and Technology in Flanders (IWT-Vlaanderen). Benjamin Schrauwen is sponsored by the FWO Flanders project G.0317.05.

## Appendix A. Specification of experiments

All reservoirs used for experiments in this contribution were constructed as follows: a random matrix was generated whereby a fraction of the entries is set to one (the *connection fraction*). In our experiments, we used a connection fraction of 0.5. Next, the nonzero entries are assigned random values from a normal distribution. Finally, the weight matrix is rescaled to set the spectral radius, LSV or $<math><mi is="true">μ</mi></math>$ to a certain value. The input matrix is constructed in the same way, with a connection fraction of 0.1, but is left unscaled.

### A.1. NARMA task

As cited in the main text, the Non-Linear Auto-Regressive Moving Average (NARMA) task consists of modeling the output of the following tenth-order system: $<math><mi is="true">y</mi><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">+</mo><mn is="true">1</mn><mo is="true">)</mo></mrow><mo is="true">=</mo><mn is="true">0.3</mn><mi is="true">y</mi><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">)</mo></mrow><mo is="true">+</mo><mn is="true">0.05</mn><mi is="true">y</mi><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">)</mo></mrow><mrow is="true"><mo is="true">[</mo><msubsup is="true"><mrow is="true"><mo is="true">∑</mo></mrow><mrow is="true"><mi is="true">i</mi><mo is="true">=</mo><mn is="true">0</mn></mrow><mrow is="true"><mn is="true">9</mn></mrow></msubsup><mi is="true">y</mi><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">−</mo><mi is="true">i</mi><mo is="true">)</mo></mrow><mo is="true">]</mo></mrow><mo is="true">+</mo><mn is="true">1.5</mn><mi is="true">u</mi><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">−</mo><mn is="true">9</mn><mo is="true">)</mo></mrow><mi is="true">u</mi><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">)</mo></mrow><mo is="true">+</mo><mn is="true">0.1</mn></math>$. Here, $<math><mi is="true">u</mi><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">)</mo></mrow></math>$ is a uniform random signal in $<math><mrow is="true"><mo is="true">[</mo><mn is="true">0</mn><mo is="true">,</mo><mn is="true">1</mn><mo is="true">]</mo></mrow></math>$, which serves as the sole input to the reservoir. The readout is trained to reproduce the signal $<math><mi is="true">y</mi><mrow is="true"><mo is="true">(</mo><mi is="true">k</mi><mo is="true">+</mo><mn is="true">1</mn><mo is="true">)</mo></mrow></math>$. The performance is measured as the mean square error (MSE), defined as $<math><mstyle mathvariant="normal" is="true"><mi is="true">MSE</mi></mstyle><mo is="true">=</mo><mfrac is="true"><mrow is="true"><mn is="true">1</mn></mrow><mrow is="true"><mi is="true">n</mi></mrow></mfrac><msubsup is="true"><mrow is="true"><mo is="true">∑</mo></mrow><mrow is="true"><mi is="true">t</mi><mo is="true">=</mo><mn is="true">1</mn></mrow><mrow is="true"><mi is="true">n</mi></mrow></msubsup><msup is="true"><mrow is="true"><mrow is="true"><mo is="true">(</mo><mi is="true">s</mi><mrow is="true"><mo is="true">(</mo><mi is="true">t</mi><mo is="true">)</mo></mrow><mo is="true">−</mo><mi is="true">y</mi><mrow is="true"><mo is="true">(</mo><mi is="true">t</mi><mo is="true">)</mo></mrow><mo is="true">)</mo></mrow></mrow><mrow is="true"><mn is="true">2</mn></mrow></msup></math>$, with $<math><mi is="true">s</mi><mrow is="true"><mo is="true">(</mo><mi is="true">t</mi><mo is="true">)</mo></mrow></math>$ the readout output and $<math><mi is="true">y</mi><mrow is="true"><mo is="true">(</mo><mi is="true">t</mi><mo is="true">)</mo></mrow></math>$ the desired output signal. For each reservoir that was constructed, a readout was trained on an example output of 1000 timesteps, and tested on a different input signal of the same length.

### A.2. Memorization task

This task was introduced in [Jaeger (2002)](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b15). Here, the input signal is again a random uniform signal, in the interval $<math><mrow is="true"><mo is="true">[</mo><mo is="true">−</mo><mn is="true">0.8</mn><mo is="true">,</mo><mn is="true">0.8</mn><mo is="true">]</mo></mrow></math>$. The desired output is multi-dimensional, and consists of a series of delayed versions of the input signal. In this case, a series of 100 regressors was trained to reproduce the input signal delayed over 1 up to 100 timesteps. The performance here is the memory capacity (MC), defined in [Jaeger (2002)](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b15) as $<math><mstyle mathvariant="normal" is="true"><mi is="true">MC</mi></mstyle><mo is="true">=</mo><msubsup is="true"><mrow is="true"><mo is="true">∑</mo></mrow><mrow is="true"><mi is="true">k</mi><mo is="true">=</mo><mn is="true">1</mn></mrow><mrow is="true"><mn is="true">100</mn></mrow></msubsup><msub is="true"><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">MC</mi></mstyle></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub></math>$, with the $<math><mi is="true">k</mi></math>$\-delay memory capacity $<math><msub is="true"><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">MC</mi></mstyle></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub><mo is="true">=</mo><msub is="true"><mrow is="true"><mo is="true">max</mo></mrow><mrow is="true"><msub is="true"><mrow is="true"><mi is="true">W</mi></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub></mrow></msub><mi is="true">d</mi><mrow is="true"><mo is="true">[</mo><msub is="true"><mrow is="true"><mi is="true">W</mi></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub><mo is="true">]</mo></mrow><mrow is="true"><mo is="true">(</mo><msub is="true"><mrow is="true"><mi is="true">s</mi></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub><mrow is="true"><mo is="true">(</mo><mi is="true">t</mi><mo is="true">)</mo></mrow><mo is="true">,</mo><msub is="true"><mrow is="true"><mi is="true">y</mi></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub><mrow is="true"><mo is="true">(</mo><mi is="true">t</mi><mo is="true">)</mo></mrow><mo is="true">)</mo></mrow><mo is="true">=</mo><msub is="true"><mrow is="true"><mo is="true">max</mo></mrow><mrow is="true"><msub is="true"><mrow is="true"><mi is="true">W</mi></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub></mrow></msub><mfrac is="true"><mrow is="true"><msup is="true"><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">cov</mi></mstyle></mrow><mrow is="true"><mn is="true">2</mn></mrow></msup><mrow is="true"><mo is="true">(</mo><msub is="true"><mrow is="true"><mi is="true">s</mi></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub><mrow is="true"><mo is="true">(</mo><mi is="true">t</mi><mo is="true">)</mo></mrow><mo is="true">,</mo><msub is="true"><mrow is="true"><mi is="true">y</mi></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub><mrow is="true"><mo is="true">(</mo><mi is="true">t</mi><mo is="true">)</mo></mrow><mo is="true">)</mo></mrow></mrow><mrow is="true"><msup is="true"><mrow is="true"><mi is="true">σ</mi></mrow><mrow is="true"><mn is="true">2</mn></mrow></msup><mrow is="true"><mo is="true">(</mo><msub is="true"><mrow is="true"><mi is="true">s</mi></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub><mrow is="true"><mo is="true">(</mo><mi is="true">t</mi><mo is="true">)</mo></mrow><mo is="true">)</mo></mrow><msup is="true"><mrow is="true"><mi is="true">σ</mi></mrow><mrow is="true"><mn is="true">2</mn></mrow></msup><mrow is="true"><mo is="true">(</mo><msub is="true"><mrow is="true"><mi is="true">y</mi></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub><mrow is="true"><mo is="true">(</mo><mi is="true">t</mi><mo is="true">)</mo></mrow><mo is="true">)</mo></mrow></mrow></mfrac></math>$, with $<math><msub is="true"><mrow is="true"><mi is="true">s</mi></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub><mrow is="true"><mo is="true">(</mo><mi is="true">t</mi><mo is="true">)</mo></mrow></math>$ the output of the $<math><mi is="true">k</mi></math>$th regressor and $<math><msub is="true"><mrow is="true"><mi is="true">y</mi></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub><mrow is="true"><mo is="true">(</mo><mi is="true">t</mi><mo is="true">)</mo></mrow></math>$ the input signal delayed over $<math><mi is="true">k</mi></math>$ timesteps. Here, $<math><mi is="true">d</mi><mrow is="true"><mo is="true">[</mo><msub is="true"><mrow is="true"><mi is="true">W</mi></mrow><mrow is="true"><mi is="true">k</mi></mrow></msub><mo is="true">]</mo></mrow></math>$ denotes the determination coefficient for the $<math><mi is="true">k</mi></math>$th readout weight matrix, which is a measure of the variance in one signal caused by the other. The maximum determination coefficient is automatically achieved by training the readout weights using the pseudo-inverse or Moore–Penrose inverse method, as is done here.

### A.3. Speech recognition task

The speech recognition task described here consists of the recognition of isolated digits. The dataset is a subset of the TI46 speech corpus, and consists of ten digits, zero to nine, each uttered ten times by five different female speakers, resulting in 500 speech fragments sampled at 12 kHz. The speech was preprocessed using the so-called Lyon Passive Ear model of the human cochlea ([Lyon, 1982](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b22)) using Malcolm Slaney’s Auditory Toolbox for Matlab ([Slaney, 1988](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b39)). This inner ear model is built in three stages: a band-pass filterbank that reflects the human selectivity for certain frequencies, followed by half-wave rectification and automatic gain control (AGC) to model the nonlinear properties of the haircells in the cochlea. The number of filters in the filterbank determines the dimensionality of the model output — in this case there are 77 channels. The result of this preprocessing step is either directly fed into the reservoir in the case of non-spiking nodes, or else transformed into spike trains using a method called BSA (Ben’s Spiker Algorithm) ([Schrauwen & Van Campenhout, 2003](https://www.sciencedirect.com/science/article/pii/S089360800700038X#b37)). This algorithm takes a temporal signal and a filter as input, and yields the spiketrain that will optimally reconstruct the original signal when decoded using this filter. The algorithm works by scanning across the signal, and at each timestep computing a heuristic error measure. When this error measure exceeds a threshold, a spike is generated and the filter is subtracted from the signal. In this case, the filter is exponentially decaying with a timeconstant of 30 sample timesteps.

In the case of spiking neurons, the spike trains generated by the reservoir are transformed back into the analog domain by filtering them with an exponential filter, which mimics the internal operation of the membrane potential of a simple spiking neuron. These analog signals are then subsampled by a factor of 20.

Ten different linear classifiers are trained, each sensitive to a different digit in the vocabulary. These classifiers are trained to output the correct value at each timestep. When tested, a final classification is reached by taking the temporal mean of the output of every classifier, and applying winner-take-all to the resulting vector. The total performance across the dataset is computed using ten-fold cross-validation.

## Appendix B. Fast simulation of Leaky Integrate and Fire neurons

Event-based simulation of LIF neurons requires the calculation of the firing times of a neuron, i.e. the time when the membrane potential $<math><msub is="true"><mrow is="true"><mi is="true">u</mi></mrow><mrow is="true"><mi is="true">i</mi></mrow></msub><mrow is="true"><mo is="true">(</mo><mi is="true">t</mi><mo is="true">)</mo></mrow></math>$ crosses the threshold value $<math><mi is="true">θ</mi></math>$. In the general case, every incoming connection has a separate synapse, each with its own synaptic timeconstant $<math><msub is="true"><mrow is="true"><mi is="true">τ</mi></mrow><mrow is="true"><mi is="true">s</mi></mrow></msub></math>$. The membrane potential is then given by (B.1)$<math><msub is="true"><mrow is="true"><mi is="true">u</mi></mrow><mrow is="true"><mi is="true">i</mi></mrow></msub><mrow is="true"><mo is="true">(</mo><mi is="true">t</mi><mo is="true">)</mo></mrow><mo is="true">=</mo><msubsup is="true"><mrow is="true"><mo is="true">∫</mo></mrow><mrow is="true"><mn is="true">0</mn></mrow><mrow is="true"><mi is="true">∞</mi></mrow></msubsup><msup is="true"><mrow is="true"><mstyle mathvariant="normal" is="true"><mi is="true">e</mi></mstyle></mrow><mrow is="true"><mrow is="true"><mo is="true">(</mo><mo is="true">−</mo><mfrac is="true"><mrow is="true"><mi is="true">s</mi></mrow><mrow is="true"><msub is="true"><mrow is="true"><mi is="true">τ</mi></mrow><mrow is="true"><mi is="true">m</mi></mrow></msub></mrow></mfrac><mo is="true">)</mo></mrow></mrow></msup><mrow is="true"><mo is="true">[</mo><munder is="true"><mrow is="true"><mo is="true">∑</mo></mrow><mrow is="true"><mi is="true">j</mi></mrow></munder><msub is="true"><mrow is="true"><mi is="true">w</mi></mrow><mrow is="true"><mi is="true">i</mi><mi is="true">j</mi></mrow></msub><munder is="true"><mrow is="true"><mo is="true">∑</mo></mrow><mrow is="true"><mi is="true">f</mi></mrow></munder><mi is="true">α</mi><mrow is="true"><mo is="true">(</mo><mi is="true">t</mi><mo is="true">−</mo><munderover accentunder="false" accent="false" is="true"><mrow is="true"><mi is="true">t</mi></mrow><mrow is="true"><mi is="true">j</mi></mrow><mrow is="true"><mrow is="true"><mo is="true">(</mo><mi is="true">f</mi><mo is="true">)</mo></mrow></mrow></munderover><mo is="true">−</mo><mi is="true">s</mi><mo is="true">)</mo></mrow><mo is="true">−</mo><mrow is="true"><mo is="true">(</mo><mi is="true">θ</mi><mo is="true">−</mo><msub is="true"><mrow is="true"><mi is="true">u</mi></mrow><mrow is="true"><mi is="true">r</mi></mrow></msub><mo is="true">)</mo></mrow><munder is="true"><mrow is="true"><mo is="true">∑</mo></mrow><mrow is="true"><mi is="true">f</mi></mrow></munder><mi is="true">δ</mi><mrow is="true"><mo is="true">(</mo><mi is="true">t</mi><mo is="true">−</mo><munderover accentunder="false" accent="false" is="true"><mrow is="true"><mi is="true">t</mi></mrow><mrow is="true"><mi is="true">i</mi></mrow><mrow is="true"><mrow is="true"><mo is="true">(</mo><mi is="true">f</mi><mo is="true">)</mo></mrow></mrow></munderover><mo is="true">−</mo><mi is="true">s</mi><mo is="true">)</mo></mrow><mo is="true">]</mo></mrow><mstyle mathvariant="normal" is="true"><mi is="true">d</mi></mstyle><mi is="true">s</mi></math>$ which needs to be solved for $<math><mi is="true">t</mi></math>$. This is generally a transcendent equation that needs to be approximated numerically using a root-finding algorithm such as Newton–Raphson. However, when we assume that every incoming connection to a neuron has the same synaptic timeconstant $<math><msub is="true"><mrow is="true"><mi is="true">τ</mi></mrow><mrow is="true"><mi is="true">s</mi></mrow></msub></math>$ and that it is half the membrane timeconstant of the neuron $<math><msub is="true"><mrow is="true"><mi is="true">τ</mi></mrow><mrow is="true"><mi is="true">s</mi></mrow></msub><mo is="true">=</mo><mfrac is="true"><mrow is="true"><msub is="true"><mrow is="true"><mi is="true">τ</mi></mrow><mrow is="true"><mi is="true">m</mi></mrow></msub></mrow><mrow is="true"><mn is="true">2</mn></mrow></mfrac></math>$, then this transcendent equation becomes a simple quadratic equation that can be solved analytically and very quickly. This simplification was coined by Olaf Booij.[9](https://www.sciencedirect.com/science/article/pii/S089360800700038X#fn9)

However, when we construct reservoirs consisting of these LIF neurons with a simplified synapse model, we need to take these limitations into account. Indeed, without further precautions, a reservoir with the same weight matrix will show far less activity when simulated with this simplified model due to the presence of a synapse model. For the same input spiketrain, the total current flowing to the neuron membrane will be less in case synapses are modeled, which results in a lower number of emitted spikes. To compensate for this, the weight matrix needs to be scaled by an appropriate factor. This factor can be determined as follows.

When we hypothesize that there is a high activity inside the reservoir,[10](https://www.sciencedirect.com/science/article/pii/S089360800700038X#fn10) we can find the rescaling factor by demanding that the integral of the post-synaptic potential (PSP) over time of both the LIF without synapse model and the simplified synapse model be equal. The integral over time for the PSP of an LIF neuron without synapse is given by (B.2)$<math><msubsup is="true"><mrow is="true"><mo is="true">∫</mo></mrow><mrow is="true"><mn is="true">0</mn></mrow><mrow is="true"><mi is="true">∞</mi></mrow></msubsup><mo is="true">exp</mo><mrow is="true"><mo is="true">(</mo><mo is="true">−</mo><mfrac is="true"><mrow is="true"><mi is="true">t</mi></mrow><mrow is="true"><msub is="true"><mrow is="true"><mi is="true">τ</mi></mrow><mrow is="true"><mi is="true">m</mi></mrow></msub></mrow></mfrac><mo is="true">)</mo></mrow><mstyle mathvariant="normal" is="true"><mi is="true">d</mi></mstyle><mi is="true">t</mi><mo is="true">=</mo><msub is="true"><mrow is="true"><mi is="true">τ</mi></mrow><mrow is="true"><mi is="true">m</mi></mrow></msub><mtext is="true">,</mtext></math>$ while the same quantity for an LIF neuron with a simplified synapse model is given by (B.3)$<math><msubsup is="true"><mrow is="true"><mo is="true">∫</mo></mrow><mrow is="true"><mn is="true">0</mn></mrow><mrow is="true"><mi is="true">∞</mi></mrow></msubsup><mo is="true">exp</mo><mrow is="true"><mo is="true">(</mo><mo is="true">−</mo><mfrac is="true"><mrow is="true"><mi is="true">t</mi></mrow><mrow is="true"><msub is="true"><mrow is="true"><mi is="true">τ</mi></mrow><mrow is="true"><mi is="true">m</mi></mrow></msub></mrow></mfrac><mo is="true">)</mo></mrow><mo is="true">−</mo><mo is="true">exp</mo><mrow is="true"><mo is="true">(</mo><mo is="true">−</mo><mfrac is="true"><mrow is="true"><mi is="true">t</mi></mrow><mrow is="true"><msub is="true"><mrow is="true"><mi is="true">τ</mi></mrow><mrow is="true"><mi is="true">s</mi></mrow></msub></mrow></mfrac><mo is="true">)</mo></mrow><mstyle mathvariant="normal" is="true"><mi is="true">d</mi></mstyle><mi is="true">t</mi><mo is="true">=</mo><msub is="true"><mrow is="true"><mi is="true">τ</mi></mrow><mrow is="true"><mi is="true">m</mi></mrow></msub><mo is="true">−</mo><msub is="true"><mrow is="true"><mi is="true">τ</mi></mrow><mrow is="true"><mi is="true">s</mi></mrow></msub><mtext is="true">.</mtext></math>$ In the case of the Booij model, $<math><msub is="true"><mrow is="true"><mi is="true">τ</mi></mrow><mrow is="true"><mi is="true">s</mi></mrow></msub><mo is="true">=</mo><mfrac is="true"><mrow is="true"><msub is="true"><mrow is="true"><mi is="true">τ</mi></mrow><mrow is="true"><mi is="true">m</mi></mrow></msub></mrow><mrow is="true"><mn is="true">2</mn></mrow></mfrac></math>$, so we find that we need to scale the weights by a factor of 2 in order to achieve the same global activity. This approximation turns out to be accurate for a very broad range of firing rates down to 10 spikes /s.

## References

[Alligood et al., 1996](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb1)

K. Alligood, T. Sauer, J. Yorke

**Chaos: An introduction to dynamical systems**

Springer (1996)

[Atiya and Parlos, 2000](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb2)

A.F. Atiya, A.G. Parlos

**New results on recurrent network training: Unifying the algorithms and accelerating convergence**

IEEE Transactions on Neural Networks, 11 (2000), p. 697

[Buehner and Young, 2006](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb3)

M. Buehner, P. Young

**A tighter bound for the echo state property**

IEEE Transactions on Neural Networks, 17 (3) (2006), pp. 820-824

[Burgsteiner, 2005a](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb4)

Burgsteiner, H. (2005a). On learning with recurrent spiking neural networks and their applications to robot control with real-world devices. *Doctoral dissertation*. Graz University of Technology

[Burgsteiner, 2005b](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb5)

Burgsteiner, H. (2005b). Training networks of biological realistic spiking neurons for real-time robot control. In *Proceedings of the 9th international conference on engineering applications of neural networks* (pp. 129–136)

[Bush and Anderson, 2005](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb6)

Bush, K., & Anderson, C. (2005). Modeling reward functions for incomplete state representations via echo state networks. In *Proceedings of the international joint conference on neural networks* (pp. 2995–3000)

[D’Haene et al., 2006](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb7)

M. D’Haene, B. Schrauwen, D. Stroobandt

**Accelerating event based simulation for multi-synapse spiking neural networks**

Proceedings of the 16th international conference on artificial neural networks: Vol. 4131, Springer, Athens, Berlin, Heidelberg ((2006/9)), pp. 760-769

[Duda et al., 2001](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb8)

R.O. Duda, P.E. Hart, D.G. Stork

**Pattern classification**

(2nd ed.), John Wiley and Sons, Inc (2001)

[Gers and Schmidhuber, 2001](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb9)

F. Gers, J. Schmidhuber

**LSTM recurrent networks learn simple context free and context sensitive languages**

IEEE Transactions on Neural Networks, 12 (6) (2001), pp. 1333-1340

[Gerstner and Kistler, 2002](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb10)

W. Gerstner, W.M. Kistler

**Spiking neuron models**

Cambridge University Press (2002)

[Graves et al., 2004](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb11)

Graves, A., Eck, D., Beringer, N., & Schmidhuber, J. (2004). Biologically plausible speech recognition with LSTM neural nets. In *Proceedings of BIO-ADIT* (pp. 127–136)

[Haykin, 1999](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb12)

S. Haykin

**Neural networks: A comprehensive foundation**

(2nd ed.), Prentice Hall (1999)

[Jaeger, 2001a](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb13)

Jaeger, H. (2001a). The “echo state” approach to analysing and training recurrent neural networks. *Tech. rep. no. GMD report 148*. German National Research Center for Information Technology

[Jaeger, 2001b](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb14)

Jaeger, H. (2001b). Short term memory in echo state networks. *Tech. rep. no. GMD report 152*. German National Research Center for Information Technology

[Jaeger, 2002](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb15)

Jaeger, H. (2002). Tutorial on training recurrent neural networks, covering BPTT, RTRL, EKF and the “echo state network” approach. *Tech. rep. no. GMD report 159*. German National Research Center for Information Technology

[Jaeger, 2003](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb16)

H. Jaeger

**Adaptive nonlinear system identification with echo state networks**

Advances in neural information processing systems (2003), pp. 593-600

[Jaeger, 2005](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb17)

Jaeger, H. (2005). Reservoir riddles: Suggestions for echo state network research (extended abstract). In *Proceedings of the international joint conference on neural networks* (pp. 1460–1462)

[Jaeger and Haas, 2004](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb18)

H. Jaeger, H. Haas

**Harnessing nonlinearity: Predicting chaotic systems and saving energy in wireless telecommunication**

Science, 308 (2004), pp. 78-80

[Joshi and Maass, 2004](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb19)

Joshi, P., & Maass, W. (2004). Movement generation and control with generic neural microcircuits. In *Proceedings of BIO-ADIT* (pp. 16–31)

[Kilian and Siegelmann, 1996](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb20)

J. Kilian, H. Siegelmann

**The dynamic universality of sigmoidal neural networks**

Information and Computation, 128 (1996), pp. 48-56

[Legenstein and Maass, 2005](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb21)

R. Legenstein, W. Maass

**What makes a dynamical system computationally powerful?**

S. Haykin, J. Principe, T. Sejnowski, J. McWhirter (Eds.), New directions in statistical signal processing: From systems to brain, MIT Press (2005)

[Lyon, 1982](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb22)

Lyon, R. (1982). A computational model of filtering, detection and compression in the cochlea. In *Proceedings of the IEEE ICASSP* (pp. 1282–1285)

[Maass, 1997](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb23)

W. Maass

**Noisy spiking neurons with temporal coding have more computational power than sigmoidal neurons**

M. Mozer, M.I. Jordan, T. Petsche (Eds.), Advances in neural information processing systems, Vol. 9, MIT Press, Cambridge (1997), pp. 211-217

[Maass and Bishop, 2001](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb24)

W. Maass, C. Bishop

**Pulsed neural networks**

Bradford Books/MIT Press, Cambridge, MA (2001)

[Maass et al., in press](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb25)

Maass, W., Legenstein, R.A., & Markram, H. (2002). A new approach towards vision suggested by biologically realistic neural microcircuit models. In *Lecture notes in computer science*: *Vol. 2525* (pp. 282–293). *Proceedings of the 2nd workshop on biologically motivated computer vision*. Berlin: Springer

[Maass et al., 2002](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb26)

W. Maass, T. Natschläger, H. Markram

**Real-time computing without stable states: A new framework for neural computation based on perturbations**

Neural Computation, 14 (11) (2002), pp. 2531-2560

[Maass et al., 2003](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb27)

W. Maass, T. Natschläger, H. Markram

**A model for real-time computation in generic neural microcircuits**

Proceedings of NIPS, Vol. 15, MIT Press (2003), pp. 229-236

[Maass et al., 2004](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb28)

W. Maass, T. Natschläger, H. Markram

**Fading memory and kernel properties of generic cortical microcircuit models**

Journal of Physiology, 98 (4–6) (2004), pp. 315-330

[Markram et al., 1997](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb29)

H. Markram, J. Lübke, M. Frotscher, B. Sakmann

**Regulation of synaptic efficacy by coincidence of postsynaptic APS and EPSPS**

Science, 275 (5297) (1997), pp. 213-215

[Markram et al., 1998](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb30)

H. Markram, D. Pikus, A. Gupta, M. Tsodyks

**Potential for multiple mechanisms, phenomena and algorithms for synaptic plasticity at single synapses**

Neuropharmacology, 37 (1998), pp. 489-500

[Minsky and Papert, 1969](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb31)

M. Minsky, S. Papert

**Perceptrons: An introduction to computational geometry**

MIT Press, Cambridge, MA (1969)

[Natschläger et al., 2004](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb32)

Natschläger, T., Bertschinger, N., & Legenstein, R. (2004). At the edge of chaos: Real-time computations and self-organized criticality in recurrent neural networks. In *Proceedings of NIPS ’04* (pp. 145–152)

[Natschläger et al., 2002](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb33)

T. Natschläger, H. Markram, W. Maass

**Computer models and analysis tools for neural microcircuits**

R. Kötter (Ed.), A practical guide to neuroscience databases and associated tools, Kluwer Academic Publishers, Boston (2002)

[Omlin and Giles, 1994](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb34)

C.W. Omlin, C.L. Giles

**Constructing deterministic finite-state automata in sparse recurrent neural networks**

IEEE international conference on neural networks, IEEE Press, Piscataway, NJ (1994), pp. 1732-1737

[Robinson, 1994](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb35)

A.J. Robinson

**An application of recurrent nets to phone probability estimation**

IEEE Transactions on Neural Networks, 5 (1994), pp. 298-305

[Rodriguez, 2001](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb36)

P. Rodriguez

**Simple recurrent networks learn context-free and context-sensitive languages by counting**

Neural Computation, 13 (9) (2001), pp. 2093-2118

[Schrauwen and Van Campenhout, 2003](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb37)

Schrauwen, B., & Van Campenhout, J. (2003). BSA, a fast and accurate spike train encoding scheme. In *Proceedings of IJCNN* (pp. 2825–2830)

[Skowronski and Harris, 2006](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb38)

M.D. Skowronski, J.G. Harris

**Minimum mean squared error time series classification using an echo state network prediction model**

IEEE international symposium on circuits and systems (2006)

[Slaney, 1988](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb39)

Slaney, M. (1988). Lyon’s cochlear model. *Tech. rep. no. 13*. Advanced Technology Group, Apple Computer Inc

[Steil, 2005](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb40)

J. Steil

**Memory in backpropagation–decorrelation: O(N) efficient online recurrent learning**

Proceedings of the international conference on artificial neural networks (2005), pp. 649-654

[Steil, 2006](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb41)

J. Steil

**Online stability of backpropagation–decorrelation recurrent learning**

Neurocomputing, 69 (2006), pp. 642-650

[Steil, 2004](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb42)

J.J. Steil

**Backpropagation–Decorrelation: Online recurrent learning with O(N) complexity**

Proceedings of IJCNN ’04, Vol. 1 (2004), pp. 843-848

[Suykens et al., 1996](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb43)

J. Suykens, J. Vandewalle, B. De Moor

**Artificial neural networks for modeling and control of non-linear systems**

Springer (1996)

[Suykens and Vandewalle, 1998](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb44)

J. Suykens, J. Vandewalle (Eds.), Nonlinear modeling: Advanced black-box techniques, Kluwer Academic Publishers (1998), pp. 29-53

[Triesch, 2004](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb45)

J. Triesch

**Synergies between intrinsic and synaptic plasticity in individual model neurons**

Neural information processing systems, Vol. 17 (2004)

[Vapnik, 1995](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb46)

V. Vapnik

**The nature of statistical learning theory**

Springer-Verlag, New York (1995)

[Verstraeten et al., 2005](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb47)

Verstraeten, D., Schrauwen, B., & Stroobandt, D. (2005/11). Reservoir computing with stochastic bitstream neurons. In *Proceedings of the 16th annual Prorisc workshop* (pp. 454–459)

[Verstraeten et al., 2005](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb48)

D. Verstraeten, B. Schrauwen, D. Stroobandt, J. Van Campenhout

**Isolated word recognition with the liquid state machine: A case study**

Information Processing Letters, 95 (6) (2005), pp. 521-528

[Watts and Strogatz, 1998](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb49)

D. Watts, S.H. Strogatz

**Collective dynamics of ‘small-world’ networks**

Nature, 39 (1998), pp. 440-442

[Watts, 1999](https://www.sciencedirect.com/science/article/pii/S089360800700038X#bb50)

D.J. Watts

**Small worlds: The dynamics of networks between order and randomness**

Princeton University Press (1999)

## Cited by (719)

[View Abstract](https://www.sciencedirect.com/science/article/abs/pii/S089360800700038X)

Copyright © 2007 Elsevier Ltd. All rights reserved.
