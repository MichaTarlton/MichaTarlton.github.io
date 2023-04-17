---
type: log
status: active
priority: p2
project: HF-DRL-course
creationtag: 2023-01-10 16:44
infotags: [course, RL, DRL, dev, programming, Q-learning, temporal difference]
people:
date:
---
web:: https://huggingface.co/deep-rl-course/unit3/

# Top Comments
- They really gloss over how the network architecture actually works or how credit is assigned
- 




# Glossary 
- [ ] *Experience Tuples #tp*

## Glossary (community) #tp
-   **Tabular Method:** type of problem in which the state and action spaces are small enough to approximate value functions to be represented as arrays and tables. **Q-learning** is an example of tabular method since a table is used to represent the value for different state-action pairs.
    
-   **Deep Q-Learning:** method that trains a neural network to approximate, given a state, the different **Q-values** for each possible action at that state. Is used to solve problems when observational space is too big to apply a tabular Q-Learning approach.
    
-   **Temporal Limitation:** is a difficulty presented when the environment state is represented by frames. A frame by itself does not provide temporal information. In order to obtain temporal information, we need to **stack** a number of frames together.
    
-   **Phases of Deep Q-Learning:**
    
    -   **Sampling:** actions are performed, and observed experience tuples are stored in a **replay memory**.
    -   **Training:** batches of tuples are selected randomly and the neural network updates its weights using gradient descent.
-   **Solutions to stabilize Deep Q-Learning:**
    
    -   **Experience Replay:** a replay memory is created to save experiences samples that can be reused during training. This allows the agent to learn from the same experiences multiple times. Also, it makes the agent avoid to forget previous experiences as it get new ones. **Random sampling** from replay buffer allows to remove correlation in the observation sequences and prevents action values from oscillating or diverging catastrophically.
        
    -   **Fixed Q-Target:** In order to calculate the **Q-Target** we need to estimate the discounted optimal **Q-value** of the next state by using Bellman equation. The problem is that the same network weigths are used to calculate the **Q-Target** and the **Q-value**. This means that everytime we are modifying the **Q-value**, the **Q-Target** also moves with it. To avoid this issue, a separate network with fixed parameters is used for estimating the Temporal Difference Target. The target network is updated by copying parameters from our Deep Q-Network after certain **C steps**.
        
    -   **Double DQN:** method to handle **overstimation** of **Q-Values**. This solution uses two networks to decouple the action selection from the target **-Value generation**: -**DQN Network** to select the best action to take for the next state (the action with the highest **Q-Value**) -**Target Network** to calculate the target **Q-Value** of taking that action at the next state. This approach reduce the **Q-Values** overstimation, it helps to train faster and have more stable learning.

# The Deep Q-Network (DQN)
Because tabular Q-learning can’t efficiently encode a large state space, we will instead use a Deep Q-Network to approximate our Q policies
![[image-20230110165707092.png]]

- [ ] Temporal Limitation #tp 
	- One frame of environment is not enough to sense motion
	- SO instead they stack multiple frames of motion together to capture spatial relationship across images
# The Deep Q-Learning Algorithm
![[image-20230110170442691.png]]

![[image-20230110170449300.png]]

> in Deep Q-Learning, we create a **loss function that compares our Q-value prediction and the Q-target and uses gradient descent to update the weights of our Deep Q-Network to approximate our Q-values better**.

> The Deep Q-Learning training algorithm has _two phases_:
> -   **Sampling**: we perform actions and **store the observed experience tuples in a replay memory**.
> -   **Training**: Select a **small batch of tuples randomly and learn from this batch using a gradient descent update step**.
> ![[image-20230110170543307.png]]

> Deep Q-Learning training **might suffer from instability**, mainly because of combining a non-linear Q-value function (Neural Network) and bootstrapping (when we update targets with existing estimates and not an actual complete return).

To help us stabilize the training, we implement three different solutions:

1. [ ]  _Experience Replay_ #tp
	1. to make more **efficient use of experiences**.
2. [ ]  _Fixed Q-Target_ #tp
	1. **to stabilize the training**. 
3. [ ]  _Double Deep Q-Learning_ #tp
		1. , to **handle the problem of the overestimation of Q-values**.

# Experience Replay to make more efficient use of experiences

Experience Replay in Deep Q-Learning has two functions:

1.  **Make more efficient use of the experiences during the training**. Usually, in online reinforcement learning, the agent interacts in the environment, gets experiences (state, action, reward, and next state), learns from them (updates the neural network), and discards them. This is not efficient
Experience replay helps **using the experiences of the training more efficiently**. We use a replay buffer that saves experience samples **that we can reuse during the training.**

![[image-20230110171335961.png]]

⇒ This allows the agent to **learn from the same experiences multiple times**.

2.  **Avoid forgetting previous experiences and reduce the correlation between experiences**.

-   The problem we get if we give sequential samples of experiences to our neural network is that it tends to forget **the previous experiences as it gets new experiences.** For instance, if the agent is in the first level and then in the second, which is different, it can forget how to behave and play in the first level.

The solution is to create a Replay Buffer that stores experience tuples while interacting with the environment and then sample a small batch of tuples. This prevents **the network from only learning about what it has done immediately before.**

Experience replay also has other benefits. By randomly sampling the experiences, we remove correlation in the observation sequences and avoid **action values from oscillating or diverging catastrophically.**

In the Deep Q-Learning pseudocode, we **initialize a replay memory buffer D from capacity N** (N is a hyperparameter that you can define). We then store experiences in the memory and sample a batch of experiences to feed the Deep Q-Network during the training phase.

# Fixed Q-Target to stabilize the training

When we want to calculate the TD error (aka the loss), we calculate the **difference between the TD target (Q-Target) and the current Q-value (estimation of Q)**.

But we **don’t have any idea of the real TD target**. We need to estimate it. Using the Bellman equation, we saw that the TD target is just the reward of taking that action at that state plus the discounted highest Q value for the next state.

![[image-20230110171916440.png]]

However, the problem is that we are using the same parameters (weights) for estimating the TD target **and** the Q-value. Consequently, there is a significant correlation between the TD target and the parameters we are changing.

Therefore, it means that at every step of training, **our Q-values shift but also the target value shifts.** We’re getting closer to our target, but the target is also moving. It’s like chasing a moving target! This can lead to a significant oscillation in training.

Instead, what we see in the pseudo-code is that we:

-   Use a **separate network with fixed parameters** for estimating the TD Target
-   **Copy the parameters from our Deep Q-Network at every C step** to update the target network.
![[image-20230110172103073.png]]

# Double DQN

- [ ] [[Double DQN]]s, or Double Learning #tp ^62wcac
	- were introduced [by Hado van Hasselt](https://papers.nips.cc/paper/3964-double-q-learning). 
	- This method **handles the problem of the overestimation of Q-values.**

We face a simple problem by calculating the TD target: how are we sure that **the best action for the next state is the action with the highest Q-value?**

We know that the accuracy of Q-values depends on what action we tried **and** what neighboring states we explored.

Consequently, we don’t have enough information about the best action to take at the beginning of the training. Therefore, taking the maximum Q-value (which is noisy) as the best action to take can lead to false positives. If non-optimal actions are regularly **given a higher Q value than the optimal best action, the learning will be complicated.**

The solution is: when we compute the Q target, we use two networks to decouple the action selection from the target Q-value generation. We:

-   Use our **DQN network** to select the best action to take for the next state (the action with the highest Q-value).
-   Use our **Target network** to calculate the target Q-value of taking that action at the next state.
- 
Therefore, Double DQN helps us reduce the overestimation of Q-values and, as a consequence, helps us train faster and have more stable learning.

Since these three improvements in Deep Q-Learning, many have been added such as 
- [ ] Prioritized Experience Replay #tp #rl 
- [ ] Dueling Deep Q-Learning #tp #rl
They’re out of the scope of this course but if you’re interested, check the links we put in the reading list.
z

# Running the code
The direct you to go look at the hyperparameters 
https://stable-baselines3.readthedocs.io/en/master/modules/dqn.html#parameters
 Which links to the papers, maybe these will give more context to the architecture

- [ ] [[1312.5602] Playing Atari with Deep Reinforcement Learning](https://arxiv.org/abs/1312.5602) #rd #rl
- [ ] [Human-level control through deep reinforcement learning | Nature](https://www.nature.com/articles/nature14236) #rd #rl

# Additional Readings

These are **optional readings** if you want to go deeper.

-   [Foundations of Deep RL Series, L2 Deep Q-Learning by Pieter Abbeel](https://youtu.be/Psrhxy88zww)
-   [Playing Atari with Deep Reinforcement Learning](https://arxiv.org/abs/1312.5602)
-   [Double Deep Q-Learning](https://papers.nips.cc/paper/2010/hash/091d584fced301b442654dd8c23b3fc9-Abstract.html)
-   [Prioritized Experience Replay](https://arxiv.org/abs/1511.05952)

# Bonus Unit 2
## [[Optuna]]
[Optuna](https://optuna.org/) is a library that helps you to automate the search. In this Unit, we’ll study a **little bit of the theory behind automatic hyperparameter tuning**. We’ll first try to optimize the parameters of the DQN studied in the last unit manually. We’ll then **learn how to automate the search using Optuna**.

## Optuna Tutorial
The content below comes from [Antonin’s Raffin ICRA 2022 presentations](https://araffin.github.io/tools-for-robotic-rl-icra2022/), he’s one of the founders of Stable-Baselines and RL-Baselines3-Zoo.

### The theory behind Hyperparameter tuning
[Automatic Hyperparameter Optimization @ ICRA 22 | Tools for Robotic RL 6/8 - YouTube](https://youtu.be/AidFTOdGNFQ)

### Optuna Tutorial
[Hyperparameter Tuning with Optuna Notebook @ ICRA 22 | Tools for Robotic RL 7/8 - YouTube](https://youtu.be/ihP7E76KGOI)

### The notebook 👉 [here](https://colab.research.google.com/github/araffin/tools-for-robotic-rl-icra2022/blob/main/notebooks/optuna_lab.ipynb)
