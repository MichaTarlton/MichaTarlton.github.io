---
type: log
status: active
priority: p2
project: HF-DRL-course
creationtag: 2022-12-13 16:18
infotags: [course, RL, DRL, dev, programming]
people:
date: 
---

# RL Framework

## Teminology
### State
The complete description of the state of the world. No hidden information

### Observation
A partial description of the state of the world.
![[image-20221213162219307.png]]

### Action Space
- Discrete 
- Continuous

### Trajectory ($\tau$)
- The sequence of states and actions.
- A cumulative reward is based on Trajectory 

### Discount Rate ($\gamma$)
-  We define a discount rate called gamma. **It must be between 0 and 1.** Most of the time between **0.99 and 0.95**.

-   The larger the gamma, the smaller the discount. This means our agent **cares more about the long-term reward.**
-   On the other hand, the smaller the gamma, the bigger the discount. This means our **agent cares more about the short term reward (the nearest cheese).**

## Tasks
### Episodic
Has a starting point and an ending point **(a terminal state). This creates an episode**: a list of States, Actions, Rewards, and new States.
### Continuing
Tasks that continue forever (no terminal state). In this case, the agent must **learn how to choose the best actions and simultaneously interact with the environment.**

For instance, an agent that does automated stock trading. For this task, there is no starting point and terminal state. **The agent keeps running until we decide to stop it.**

## Policy($\pi$)-Based Methods
### Deterministic
- _Deterministic_: a policy at a given state **will always return the same action.**
- action = policy(state)
### Stochastic
-   _Stochastic_: outputs **a probability distribution over actions.**
- policy(actions | state) = probability distribution over the set of actions given the current state

## Value-based methods
- In value-based methods, instead of training a policy function, we **train a value function** that maps a state to the expected value **of being at that state.**

- The value of a state is the **expected discounted return** the agent can get if it **starts in that state, and then act according to our policy.**

- “Act according to our policy” just means that our policy is **“going to the state with the highest value”.**

# Development #dev
[Link to colab notebook](https://colab.research.google.com/drive/1lprNknlhsf_aNQVFBIbey6KY15HFdECP#scrollTo=j5f2cGkdP-mb)

Would be sorta cool if I could just link to a local copy here add to [[Obsidian Vault Meta|Obsidian Needs]]

## import.gym
[[AI-Gym Development]]???

Create an environment `env`
The `Env` class has the attribute `action_space`
- “which describes the numerical structure of the legitimate actions that can be applied to the environment.“”
	- https://blog.paperspace.com/getting-started-with-openai-gym/

## Lunar lander 
- https://www.gymlibrary.dev/environments/box2d/lunar_lander/
- [ ] [Stable-Baselines3 Docs - Reliable Reinforcement Learning Implementations — Stable Baselines3 1.7.0a5 documentation](https://stable-baselines3.readthedocs.io/en/master/) #tp #p2 #dev #software 

## Evaluate_policy
- [Examples — Stable Baselines3 1.7.0a5 documentation](https://stable-baselines3.readthedocs.io/en/master/guide/examples.html#basic-usage-training-saving-loading)
- mean_reward, std_reward = evaluate_policy(model, model.get_env(), n_eval_episodes=10)
# Additional Reading
## Deep Reinforcement Learning

-   [Reinforcement Learning: An Introduction, Richard Sutton and Andrew G. Barto Chapter 1, 2 and 3](http://incompleteideas.net/book/RLbook2020.pdf)
-   [Foundations of Deep RL Series, L1 MDPs, Exact Solution Methods, Max-ent RL by Pieter Abbeel](https://youtu.be/2GwBez0D20A)
-   [Spinning Up RL by OpenAI Part 1: Key concepts of RL](https://spinningup.openai.com/en/latest/spinningup/rl_intro.html)

## Gym

-   [Getting Started With OpenAI Gym: The Basic Building Blocks](https://blog.paperspace.com/getting-started-with-openai-gym/)
# Bonus Tutorial
Well I trained the model successfully but still not entirely certain about it. Mostly just copy passtaed.
See the [Google Colab Notebook](https://colab.research.google.com/drive/1lprNknlhsf_aNQVFBIbey6KY15HFdECP?usp=sharing)