---
aliases: [End to end RL,]
type: topics
status: open
priority: p4
creationtag: 2023-02-01 17:01
infotags:
---

Ok from what I gather, it means there is only one model at play in the full model. I.e. compared to other ML models which may require several different models stacked into each other, a e2e is a single type. The idea being it modulates itself internally.
https://ai.stackexchange.com/questions/16575/what-does-end-to-end-training-mean

I’m not sure if say a conv alyer to a FC layer counts


> In **end-to-end reinforcement learning**, the entire process from sensors to motors in a robot or agent (called the end-to-end process) involves a single, layered or [recurrent neural network](https://handwiki.org/wiki/Recurrent_neural_network "Recurrent neural network") without modularization, and is trained by [reinforcement learning](https://handwiki.org/wiki/Reinforcement_learning "Reinforcement learning") (RL).[[1]](https://handwiki.org/wiki/End-to-end_reinforcement_learning#cite_note-Hassabis-1)[^1]

> In end-to-end reinforcement learning, an agent captures the entire mapping from its raw sensor data to actuation commands using a single neural network. End-to-end reinforcement learning is mostly studied in single-agent domains, and its scalability to multi-agent setting is under-explored.[^2]

https://arxiv.org/abs/1703.02239


> End-to-end (E2E) learning refers to training a possibly complex learning system represented by a single model (specifically a Deep Neural Network) that represents the complete target system, bypassing the intermediate layers usually present in traditional pipeline designs.

https://towardsdatascience.com/e2e-the-every-purpose-ml-method-5d4f20dafee4#:~:text=End-to-end%20(E2E,present%20in%20traditional%20pipeline%20designs.

```query 
line:("End-to-End Reinforcement-Learning") OR  line:("End to End RL") 
```

[^1]: https://handwiki.org/wiki/End-to-end_reinforcement_learning
[^2]: [ Jiao and Oh 2019 IEEE Xplore Full-Text PDF:](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=8999172)