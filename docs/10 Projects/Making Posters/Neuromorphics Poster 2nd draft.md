---
type: [writing]
status: closed
priority: p2
project: posters
creationtag: 2022-12-01 20:43
infotags: neuromorphic
people:
date:
---

# Title

## Neuromorphic Computing
### Crisis
The current expansion of ever enlarging AI models and data-intensive computing has lead to a crises of efficiency. Data centers currently consume around 200 terawatt hours of energy per year [Mehonic] and consumption is forecast to increase tenfold by 2030. Meanwhile, traditional computing hardware has plateaued in efficiency. Faced with the expansion of an *Internet of Things*, minute low-powered, standalone devices, there is need for new hardware models to serve as the backbone of the next generation of robotics and industrial machinery.

### Neuromorphics
In light of the processing requirements of neural networks, adaptations were made to utilize the array-based math optimization of common graphics processing units. This led to the creation of neural network dedicated hardware optimized specifically for the tensor math common to AI models and algorithms. These furthered optimized energy and computational efficiency in AI application through atomization of centers of memory and information integration. However, these still suffer decreasing return as models scale.

To solve this we are exploring ***Neuromorphics***, a new paradigm in computing. Where the brain is extremely efficient in both computational and energy resources, we are adopting well studied models from recent computational neuroscience to inspire specialized AI models and previously unseen hardware architectures.

This methodology fully embraces a neural network design in the hardware architecture at the transistor level, where *memresistors* replace traditional digital switches. These analog components eschew the digital layer of mathematical computation for immediate and continuous calculations. Currently available neuromorphic hardware, provides a spectrum of….



## Methods
### Spiking Neural Networks
The brain relies on spike-based communication between neurons, which has numerous advantages. *Sparse-coding*, in which information is infrequently passed in bits of energy across the network, and is effectively “off” as a default state. Likewise, the communication is *event-driven*, meaning it can effectively lie dormant and only pass along information to the necessary neurons when in response to an event or internal process, allowing it to make rapid, online learning decisions. A further desired property is the dense encoding of higher dimensional information including a natural encoding of time, and the ability to fully distribute encoded memory across the entire network.

The study of spiking neural networks as AI models is a relatively recent one, which while already having shown great promise in efficiency with current models, is still a new frontier of unexplored methods and models.


### Deep Reinforcement Learning
**Reinforcement Learning** provides a framework of models which are able to teach themselves an optimal strategy using a reward signal or environmental status to inform their learning. This reflects neurophysiological models where neuronal circuit plasticity is modified through “reward” and modulatory signal chemicals such as dopamine and acetylcholine. 

A more recent implementation of reinforcement learning uses deep networks to more efficiently represent the learning policies at the core of the reinforcement learning algorithms. However, the interlinking of reinforcement learning and deep neural networks is not an easy one, as the methods of assigning corrections during learning is fundamentally different; the *Credit Assignment Problem*. 

We are developing solutions to this problem through simultaneous development of spiking neural networks and their neurological bases of assigning credit in a deeply recurrent and entangled architecture. 