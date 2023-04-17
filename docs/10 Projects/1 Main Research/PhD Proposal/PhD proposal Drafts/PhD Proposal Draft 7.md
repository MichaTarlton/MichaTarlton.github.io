---
type: writing/draft
status: active
priority: p1
creationtag: 2022-05-18 19:18
infotags: proposal
comment: "goal of this one is to rewrite for flow"
---

# Introduction
## Combining Reinforcement, Deep Learning, and Spiking Neural Networks 

Current machine learning techniques face several limitations when it comes to generality, speed, and efficiency. The typical model of supervised learning, deep learning, can be generalized to many tasks, using deep, flexible, layers of artificial neurons communicating with each other. If the architecture is right, a supervised model can be taught to perform any task. However, these systems do not react in real time, instead training on data passed through at all artificial timesteps. %%I don’t  like this sentence at all.%% Additionally, the required amount of training and input from an external observer increases with the size of state space.

Comparatively, reinforcement learning models are reactive, optimizing for good policies (what actions to take as a function of the environment) based on feedback from the environment. This feedback is typically of the form of a teaching signal or a performance score. Making reinforcement learning ideal for real-world applications where optimizations must be made on chaotic and unpredictable flows of data. This is made difficult though as reinforcement learning trades-off in the size of task spaces which can be reasonably learned without constraining dimensionality. 


>  "Biological intelligence provides evidence for general intelligence, quick one-shot learning, and flexible learning. Humans and animals are not only able to learn good and adaptive policies from scarce data, balancing exploration and exploitation, but they are also able to generalize temporal patterns learned from single experiences. For instance, a singer can sing a song learned in a particular tempo in multiple speeds. ..." 
>  Then you can use this to justify investigating biologically plausible networks to maximize the chance of obtaining a timing capable system.

However, biological models rely on a dimension of communication that conventional models still struggle with, time and multiple timescale representation. 

%%Biologically motivated models of spiking networks offer a method of reinforcing and accelerating the capabilities of machine learning.%% 

Issues in increasing the flexibility of reinforcement learning with the deep neural structures of deep learning, require alternatives to the time-stationary methods of deep learning. The same real-time learning mechanisms which will be necessary in working spiking network models. 

Because the temporal dynamics of in-vivo neural structures are able to simultaneously process information at multiple timescales, a biologically inspired, temporally driven, learning scheme should be able to train a model of Deep Reinforcement Learning, for multiple dimensions of a task in relation to multiple associations in time.



# Research Questions
> Need to cut this down into 3-4 paragraphs


In this project, we ask how can we exploit the innate properties of temporal dynamics found in spiking neural networks, to create a  model which can learn in a complex, time-dependent environment. In detail, the answers we seek are the following:

- Can we combine models of current machine learning to create a new model which performs multi-objective learning in multiple frames of time?
- What temporal dynamics of a SNN can be used to create a model which learn multiple timescales?
- How do these representations of time emerge in the dynamics of such a model, and how can they be modulated?
→ Can we implement this model in modern neuromorphic hardware, and how effective will its performance be?
- Can we relate any novel findings in SNN dynamics to biological models?



How can these timescales be recognized by a synthetic agent? Not only is
the learning dependent on association between event and time, but also
on recognition of different intervals of time. Additionally, correct
association between the appropriate time interval and the relevant event
must be learned. How can we implement separate learning events in the plasticity of the neuronal units? 

The association between time and events has been addressed by machine
learning methods up until now, in only short time scales and to single
tasks. We ask if it is possible to create a learning method to optimize
the behavior of an agent, not only in regard to the short term, but the
actions required in the short term to maximally a long term policy.

Thus a pertinent question emerges: Can we create a model, which learns simultaneous state-action
optimizations for multiple reference frames of time, the same way an
animal may choose its behaviors? For example, such a model can make decisions not only on
the time of day, but the time of year. In this case, can such a  model correctly
associate reward with actions made, not most recently, but most relevant
over the whole time-space?

Assuming, we achieve our goal of encoding multiple, flexible, timescales
in SNNs to amplify the abilities of DRL, we can then:\\
→ Create a model which will self-learn\\
→ Do so for a large state, action, reward, and time relation space\\
→ Optimize across multiple competing objectives in time

By result of this research, we will have developed:\\
→ Novel discoveries in SNN temporal dynamics\\
→ Novel DRL-SNN architecture design and models\\
→ Novel concept mechanisms to relate to biological systems and implement
in neuromorphic hardware