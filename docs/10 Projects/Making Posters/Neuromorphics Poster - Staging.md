---
type: [writing]
status: closed
priority: p1
project: posters
creationtag: 2022-12-01 10:24
infotags:
people:
date:
---

**See:**
- [[Neuromorphics Poster 2nd draft]]
- [[Making Posters]]


# Pulling from:
[[Project Ideas Pecha Kucha]]
[[@zenkeVisualizingJointFuture2021]]
[[Mehonic 2022]]
[[@cramerSurrogateGradientsAnalog2022|Cramer et al. (2022)]]


# Title
## Neurological Inspirations for High-Efficiency Autonomous Hardware


# Intro
- Neuromorphic computing stands to cause a paradigm shift in computing and robotics
- Current data-intensive computing requires large amount of energy that is only growing by the year and is projected to increase with the expansion of larger AI models.
	> data centres currently use around 200 terawatt hours of energy per year, forecast to grow by around an order of magnitude by 2030
	- Mehonic 2022, citing [How to stop data centres from gobbling up the world’s electricity](https://www.nature.com/articles/d41586-018-06610-y)
- With the expansion of low-powered, standalone devices as part of the internet of things (IoT)
- There is need for highly energy efficient, highly autonomous models as the backbone of next generation robotics and industrial machinery
- To solve this we are exploring a new paradigm in computing called ***Neuromorphics***
- This field builds off recent AI models and AI optimized hardware substrates to bridge a gap between current AI and computational neuroscience inspired methods
- Where the brain is computationally and resource efficient, we can adapt well studied processes from neuroscience to implement in specialized models and hardware

# Motivations
- Traditional computing methods have fallen off in efficiency in recent years.
> Recent analysis shows that increasing demand for computing power vastly outpaces improvements made through Moore’s law scaling3. Computing power demands now double every two months (Fig. 1a). Remarkable improvements have been made through a combination of smart architecture and software–hardware co-design. For example, the performance of NVIDIA GPUs (graphics processing units) has improved by the factor of 317 since 2012: far beyond what would be expected from Moore’s law alone (Fig. 1b)—although the power consumption of units has increased from approximately 25 W to around 320 W in the same period. Further impressive performance improvements have been demonstrated at the research and development stage (Fig. 1b, red) and it is likely that we can achieve more4,5. Unfortunately, it is unlikely that conventional computing solutions alone will cope with demand over an extended period. This is especially apparent when we consider the shockingly high cost of training required for the most complex deep learning models (Fig. 1c). We need alternative approaches.
- Mehonic 2022, 
	- Citing:
		- [AI and Compute](https://openai.com/blog/ai-and-compute/)
		- [A 0.11 PJ/OP, 0.32-128 Tops, Scalable Multi-Chip-Module-Based Deep Neural Network Accelerator Designed with A High-Productivity vlsi Methodology | IEEE Conference Publication | IEEE Xplore](https://doi.org/10.1109/HOTCHIPS.2019.8875657) 
		- [MAGNet: A Modular Accelerator Generator for Neural Networks | IEEE Conference Publication | IEEE Xplore](https://ieeexplore.ieee.org/document/8942127)
		
- Neuromorphics extends from the neural network optimized architecture of Graphical Processing Units and Tensor Processing Units 
	- from CPU to GPU to TPU to NPU
		> The energy problem is largely a consequence of digital computing systems storing data separately from where they are processed. This is the classical von Neumann architecture underpinning digital computing systems. Processors spend most of their time and energy moving data. Fortunately, we can improve the situation by taking inspiration from biology, which takes a different approach entirely—co-locating memory and processing, encoding information in a wholly different way or operating directly on signals, and employing massive parallelism, for example (Box 1).
					- Mehonic 2022  
	- A key feature we see during this progression of distribution and atomization of memory and information integration away from hierarchical and centralized Von Neumann architecture into more disperse and universally connected units

- And fully embraces a neural-network first optimized hardware design 
- These are able to gain speed and low-cost computational power by integrating analog components alongside traditional computing components
	-  Where digital computing relies on discrete binary calculations
	- Using continuous variable charges the *memresitors* can make immediate physics-driven calculations
- There is a spectrum in the 

# Methods
## Spiking Neural Networks
- Spiking Communication
	- The default communication method of the brain
	- Is sparse coded and event-driven
	- Capable of encoding high dimensions of data including timing
- Write about this as why it is good to use in these systems
- Further research required in how they learn and communicate

## Deep Reinforcement Learning
- Autonomous agents require the ability to meet performance expectations with little to no human supervision
- This becomes an increasingly necessary requirement in agents that may be placed in physically remote and rapidly changing environments, such as deep sea or wind farms.

- Reinforcement Learning and its deep neural network derivative, learn policies of reaction to a task based on environment input and optimality scoring
- On-The-Fly, unsupervised learning can be applied in a spiking environment to create rapidly learning, autonomous models

# Proposal / Future Plans
- This project involves adapting biologically plausible models of spiking communication networks to a deep reinforcement based model
- Using local plasticity methods which operate on a reward signal, such as *Three-Factor Spike-timing Dependent Plasticity* to map the Environment-Action Policy space
- Develop solutions for important challenges to autonomous systems such as learning temporally spatial rewards
- Implement in neurmorphic hardware such as the Intel Loihi chip or potentially drive development of new neuromorphic hardware
- Set a cornerstone into the foundation of the new *classical-neuromorphic-quantum computing paradigm*
# Figures
- Include some images of windmills or something idk

## Recreate this somehow
![Screenshot_20220428_164718.png](https://dynalist.io/u/LefbNjJ26VlRx_B8P1Ymx2bk)
	- Found the CPU architecture here:
		- [Von Neumann Architecture - Computer Science GCSE GURU](https://www.computerscience.gcse.guru/theory/von-neumann-architecture)
		- ![[image-20221201161954620.png]]


![Fig 2. ](https://dynalist.io/u/FIbbhYi7ry9ZyVthUVJRlQlA)

# Images
## random
![[image-20221201162201893.png]]

## [Exploring the GPU Architecture | VMware](https://core.vmware.com/resource/exploring-gpu-architecture#section1)

![[image-20221201162239527.png]]

![[image-20221201162249179.png]]

## [IPU Processors](https://www.graphcore.ai/products/ipu)
![[image-20221201162738402.png]]

![[image-20221201162943276.png]]


![[image-20221201163111710.png]]
[1. Switched GW-Links in large scale Bow Pod systems — Switched GW-Links in large scale Pod systems](https://docs.graphcore.ai/projects/switched-gwlinks/en/latest/switched_gwlinks.html)

## NPU
### Intel Loihi
![[image-20221201163530961.png]]

[https://download.intel.com/newsroom/2021/new-technologies/neuromorphic-computing-loihi-2-brief.pdf](https://download.intel.com/newsroom/2021/new-technologies/neuromorphic-computing-loihi-2-brief.pdf)
[Fetching Title#kja4](https://download.intel.com/newsroom/2021/new-technologies/neuromorphic-computing-loihi-2-brief.pdf)
![[image-20221201163608952.png]]

![[image-20221201163656072.png]]

