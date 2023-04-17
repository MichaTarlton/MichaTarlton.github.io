---
type: log
status: active
priority: p2
project: HF-DRL-course
creationtag: 2023-01-11 18:50
infotags: [course, RL, DRL, dev, programming, Q-learning, temporal difference]
people:
date:
---
web:: https://huggingface.co/deep-rl-course/unit4

# POLICY GRADIENT WITH PYTORCH

In value-based methods, the policy **π** only exists because of the action value estimates since the policy is just a function(for instance, greedy-policy) that will select the action with the highest value given a state.

But, with policy-based methods, we want to optimize the policy directly **without having an intermediate step of learning a value function.**

So today, **we’ll learn about ==policy-based methods== and study a subset of these methods called ==policy gradient==**. Then we’ll implement our first policy gradient algorithm called ==Monte Carlo **Reinforce==** or just [[REINFORCE]] [^2] from scratch using PyTorch. Then, we’ll test its robustness using the CartPole-v1 and PixelCopter environments.

# What are the policy-based methods?

The main goal of Reinforcement learning is to **find the optimal policy \pi^{*}π∗ that will maximize the expected cumulative reward**. Because Reinforcement Learning is based on the _reward hypothesis_: **all goals can be described as the maximization of the expected cumulative reward.**

## Value-based, Policy-based, and Actor-critic methods

We studied in the first unit, that we had two methods to find (most of the time approximate) this optimal policy \pi^{*}π∗.

-   In _value-based methods_, we learn a value function.
    -   The idea is that an optimal value function leads to an optimal policy \pi^{*}π∗.
    -   Our objective is to **minimize the loss between the predicted and target value** to approximate the true action-value function.
    -   We have a policy, but it’s implicit since it **was generated directly from the value function**. For instance, in Q-Learning, we defined an epsilon-greedy policy.
-   On the other hand, in _policy-based methods_, we directly learn to approximate \pi^{*}π∗ without having to learn a value function.
    
    -   The idea is **to parameterize the policy**. For instance, using a neural network \pi_\thetaπθ​, this policy will output a probability distribution over actions (stochastic policy).
![[image-20230112101717652.png]]

-   Our objective then is **to maximize the performance of the parameterized policy using gradient ascent**.
-   To do that, we control the parameter θθ that will affect the distribution of actions over a state.

![[image-20230112101749251.png]]

Consequently, thanks to policy-based methods, we can directly optimize our policy πθπθ​ to output a probability distribution over actions πθ(a∣s)πθ​(a∣s) that leads to the best cumulative return. To do that, we define an objective function J(θ)J(θ), that is, the expected cumulative reward, and we **want to find θθ that maximizes this objective function**.

## The difference between policy-based and policy-gradient methods

Policy-gradient methods, what we’re going to study in this unit, is a subclass of policy-based methods. In policy-based methods, the optimization is most of the time _on-policy_ since for each update, we only use data (trajectories) collected **by our most recent version of** πθπθ​.

The difference between these two methods **lies on how we optimize the parameter** θθ:

-   In _policy-based methods_, we search directly for the optimal policy. We can optimize the parameter θθ **indirectly** by maximizing the local approximation of the objective function with techniques like hill climbing, simulated annealing, or evolution strategies.
-   In _policy-gradient methods_, because we’re a subclass of the policy-based methods, we search directly for the optimal policy. But we optimize the parameter θθ **directly** by performing the gradient ascent on the performance of the objective function J(θ)J(θ).

Before diving more into how works policy-gradient methods (the objective function, policy gradient theorem, gradient ascent, etc.), let’s study the advantages and disadvantages of policy-based methods.

# The advantages and disadvantages of policy-gradient methods
## Advantages
### The simplicity of integration

We can estimate the policy directly without storing additional data (action values).

### Policy-gradient methods can learn a stochastic policy

Policy-gradient methods can **learn a stochastic policy while value functions can’t**.

This has two consequences:

1.  We **don’t need to implement an exploration/exploitation trade-off by hand**. Since we output a probability distribution over actions, the agent explores **the state space without always taking the same trajectory.**
    
2.  We also get rid of the problem of **[[perceptual aliasing]]**. Perceptual aliasing is when two states seem (or are) the same but need different actions.
Let’s take an example: we have an intelligent vacuum cleaner whose goal is to suck the dust and avoid killing the hamsters.

![Hamster 1](https://huggingface.co/datasets/huggingface-deep-rl-course/course-images/resolve/main/en/unit6/hamster1.jpg)

Our vacuum cleaner can only perceive where the walls are.

The problem is that the **two rose cases are aliased states because the agent perceives an upper and lower wall for each**.

![Hamster 1](https://huggingface.co/datasets/huggingface-deep-rl-course/course-images/resolve/main/en/unit6/hamster2.jpg)

Under a deterministic policy, the policy either will move right when in a red state or move left. **Either case will cause our agent to get stuck and never suck the dust**.

Under a value-based Reinforcement learning algorithm, we learn a **quasi-deterministic policy** (“greedy epsilon strategy”). Consequently, our agent can **spend a lot of time before finding the dust**.

On the other hand, an optimal stochastic policy **will randomly move left or right in rose states**. Consequently, **it will not be stuck and will reach the goal state with a high probability**.

### Policy-gradient methods are more effective in high-dimensional action spaces and continuous actions spaces

The problem with Deep Q-learning is that their **predictions assign a score (maximum expected future reward) for each possible action**, at each time step, given the current state.

But what if we have an infinite possibility of actions?

For instance, with a self-driving car, at each state, you can have a (near) infinite choice of actions (turning the wheel at 15°, 17.2°, 19,4°, honking, etc.). **We’ll need to output a Q-value for each possible action**! And **taking the max action of a continuous output is an optimization problem itself**!

Instead, with policy-gradient methods, we output a **probability distribution over actions.**

### Policy-gradient methods have better convergence properties

In value-based methods, we use an aggressive operator to **change the value function: we take the maximum over Q-estimates**. Consequently, the action probabilities may change dramatically for an arbitrarily small change in the estimated action values if that change results in a different action having the maximal value.

For instance, if during the training, the best action was left (with a Q-value of 0.22) and the training step after it’s right (since the right Q-value becomes 0.23), we dramatically changed the policy since now the policy will take most of the time right instead of left.

On the other hand, in policy-gradient methods, stochastic policy action preferences (probability of taking action) **change smoothly over time**.
## Disadvantages

Naturally, policy-gradient methods also have some disadvantages:

-   **Frequently, policy-gradient converges on a local maximum instead of a global optimum.**
-   Policy-gradient goes slower, **step by step: it can take longer to train (inefficient).**
-   Policy-gradient can have high variance. We’ll see in actor-critic unit why and how we can solve this problem.

👉 If you want to go deeper into the advantages and disadvantages of policy-gradient methods, [you can check this video](https://youtu.be/y3oqOjHilio).

# Diving deeper into policy-gradient methods

## Getting the big picture

We just learned that policy-gradient methods aim to find parameters \thetaθ that **maximize the expected return**.

The idea is that we have a _parameterized stochastic policy_. In our case, a neural network outputs a probability distribution over actions. The probability of taking each action is also called _action preference_.

If we take the example of CartPole-v1:

-   As input, we have a state.
-   As output, we have a probability distribution over actions at that state.
![[image-20230112122414811.png]]

Our goal with policy-gradient is to **control the probability distribution of actions** by tuning the policy such that **good actions (that maximize the return) are sampled more frequently in the future.** Each time the agent interacts with the environment, we tweak the parameters such that good actions will be sampled more likely in the future.

But **how are we going to optimize the weights using the expected return**?

The idea is that we’re going to **let the agent interact during an episode**. And if we win the episode, we consider that each action taken was good and must be more sampled in the future since they lead to win.

So for each state-action pair, we want to increase the P(a|s)P(a∣s): the probability of taking that action at that state. Or decrease if we lost.

The Policy-gradient algorithm (simplified) looks like this:

![[image-20230112122500047.png]]

## Diving deeper into policy-gradient methods

We have our stochastic policy \piπ which has a parameter \thetaθ. This \piπ, given a state, **outputs a probability distribution of actions**.

![[image-20230112122519941.png]]

Where \pi_\theta(a_t|s_t)πθ​(at​∣st​) is the probability of the agent selecting action a_tat​ from state s_tst​ given our policy.

**But how do we know if our policy is good?** We need to have a way to measure it. To know that, we define a score/objective function called J(\theta)J(θ).


### The objective function

The _objective function_ gives us the **performance of the agent** given a trajectory (state action sequence without considering reward (contrary to an episode)), and it outputs the _expected cumulative reward_.
![[image-20230112122539704.png]]

-   The _expected return_ (also called expected cumulative reward), is the weighted average (where the weights are given by P(\tau;\theta)P(τ;θ) of all possible values that the return R(\tau)R(τ) can take.
-   R(τ) : Return from an arbitrary trajectory. To take this quantity and use it to calculate the expected return, we need to multiply it by the probability of each possible trajectory.
-   P(\tau;\theta)P(τ;θ) : Probability of each possible trajectory \tauτ (that probability depends on \thetaθ since it defines the policy that it uses to select the actions of the trajectory which as an impact of the states visited).
![[image-20230112122911013.png]]

-   J(θ) : Expected return, we calculate it by summing for all trajectories, the probability of taking that trajectory given \thetaθ, and the return of this trajectory.

Our objective then is to maximize the expected cumulative reward by finding \thetaθ that will output the best action probability distributions:
![[image-20230112122935065.png]]

## Gradient Ascent and the Policy-gradient Theorem

Policy-gradient is an optimization problem: we want to find the values of \thetaθ that maximize our objective function J(\theta)J(θ), we need to use **gradient-ascent**. It’s the inverse of _gradient-descent_ since it gives the direction of the steepest increase of J(\theta)J(θ).

(If you need a refresher on the difference between gradient descent and gradient ascent [check this](https://www.baeldung.com/cs/gradient-descent-vs-ascent) and [this](https://stats.stackexchange.com/questions/258721/gradient-ascent-vs-gradient-descent-in-logistic-regression)).

Our update step for gradient-ascent is:

$$\theta \leftarrow \theta + \alpha * \nabla_\theta J(\theta)$$θ←θ+α∗∇θ​J(θ)

We can repeatedly apply this update state in the hope that \thetaθ converges to the value that maximizes J(\theta)J(θ).

However, we have two problems to obtain the derivative of J(\theta)J(θ):

1.  We can’t calculate the true gradient of the objective function since it would imply calculating the probability of each possible trajectory which is computationally super expensive. We want then to **calculate a gradient estimation with a sample-based estimate (collect some trajectories)**.
2. We have another problem that I detail in the next optional section. To differentiate this objective function, we need to differentiate the state distribution, called Markov Decision Process dynamics. This is attached to the environment. It gives us the probability of the environment going into the next state, given the current state and the action taken by the agent. The problem is that we can’t differentiate it because we might not know about it.

Fortunately we’re going to use a solution called the Policy Gradient Theorem that will help us to reformulate the objective function into a differentiable function that does not involve the differentiation of the state distribution.

![[image-20230112132323188.png]]

If you want to understand how we derivate this formula that we will use to approximate the gradient, check the next (optional) section.

## The Reinforce algorithm (Monte Carlo Reinforce)

The Reinforce algorithm, also called Monte-Carlo policy-gradient, is a policy-gradient algorithm that **uses an estimated return from an entire episode to update the policy parameter** \thetaθ:

In a loop:

-   Use the policy $\pi_\theta$​ to collect an episode $\tau$
-   Use the episode to estimate the gradient $\hat{g} = \nabla_\theta J(\theta)$ (see eq below)
-   Update the weights of the policy: $\theta \leftarrow \theta + \alpha \hat{g}$
![[image-20230112141344806.png]]

The interpretation we can make is this one:
-   $\nabla_\theta log \pi_\theta(a_t|s_t)$ is the direction of **steepest increase of the (log) probability** of selecting action at from state $s_t$. This tells us **how we should change the weights of policy** if we want to increase/decrease the log probability of selecting action $a_t$​ at state $s_t$​.
-   $R(\tau)$: is the scoring function:
    -   If the return is high, it will **push up the probabilities** of the (state, action) combinations.
    -   Else, if the return is low, it will **push down the probabilities** of the (state, action) combinations.

We can also **collect multiple episodes (trajectories)** to estimate the gradient:
![[image-20230112141540649.png]]

# (Optional) the Policy Gradient Theorem

In this optional section where we’re **going to study how we differentiate the objective function that we will use to approximate the policy gradient**.

Let’s first recap our different formulas:

1.  The Objective function
![[image-20230112141603785.png]]

2.  The probability of a trajectory (given that action comes from $\pi_\theta$​):
![[image-20230112141649739.png]]

So we have:
$$
\nabla_\theta J(\theta)=\nabla_\theta \sum_\tau P(\tau ; \theta) R(\tau)
$$
We can rewrite the gradient of the sum as the sum of the gradient:
$$
=\sum_\tau \nabla_\theta P(\tau ; \theta) R(\tau)
$$
We then multiply every term in the sum by $\frac{P(\tau ; \theta)}{P(\tau ; \theta)}$ (which is possible since it's = 1)
$$
\begin{aligned}
& =\sum_\tau \frac{P(\tau ; \theta)}{P(\tau ; \theta)} \nabla_\theta P(\tau ; \theta) R(\tau) \\
& \text { We can simplify further this since } \frac{P(\tau ; \theta)}{P(\tau ; \theta)} \nabla_\theta P(\tau ; \theta)=P(\tau ; \theta) \frac{\nabla_\theta P(\tau ; \theta)}{P(\tau ; \theta)} \\
& =\sum_\tau P(\tau ; \theta) \frac{\nabla_\theta P(\tau ; \theta)}{P(\tau ; \theta)} R(\tau)
\end{aligned}
$$
We can then use the ==[[derivative log trick]] (also called likelihood ratio trick or REINFORCE trick==), a simple rule in calculus that implies that $\nabla_x \log f(x)=\frac{\nabla_x f(x)}{f(x)}$
So given we have $\frac{\nabla_\theta P(\tau ; \theta)}{P(\tau ; \theta)}$ we transform it as $\nabla_\theta \log P(\tau \mid \theta)$
So this is our likelihood policy gradient:
$$
\nabla_\theta J(\theta)=\sum_\tau P(\tau ; \theta) \nabla_\theta \log P(\tau ; \theta) R(\tau)
$$
Thanks for this new formula, we can estimate the gradient using trajectory samples (we can approximate the likelihood ratio policy gradient with sample-based estimate if you prefer).
$\nabla_\theta J(\theta)=\frac{1}{m} \sum_{i=1}^m \nabla_\theta \log P\left(\tau^{(i)} ; \theta\right) R\left(\tau^{(i)}\right)$ where each $\tau^{(i)}$ is a sampled trajectory.

---

But we still have some mathematics work to do there: we need to simplify $\nabla_\theta \log P(\tau \mid \theta)$
We know that:
$$
\nabla_\theta \log P\left(\tau^{(i)} ; \theta\right)=\nabla_\theta \log \left[\mu\left(s_0\right) \prod_{t=0}^H P\left(s_{t+1}^{(i)} \mid s_t^{(i)}, a_t^{(i)}\right) \pi_\theta\left(a_t^{(i)} \mid s_t^{(i)}\right)\right]
$$
Where $\mu\left(s_0\right)$ is the initial state distribution and $P\left(s_{t+1}^{(i)} \mid s_t^{(i)}, a_t^{(i)}\right)$ is the state transition dynamics of the MDP.

---

==We know that the log of a product is equal to the sum of the logs==:

$$
\nabla_\theta \log P\left(\tau^{(i)} ; \theta\right)=\nabla_\theta \log \mu\left(s_0\right)+\nabla_\theta \sum_{t=0}^H \log P\left(s_{t+1}^{(i)} \mid s_t^{(i)} a_t^{(i)}\right)+\nabla_\theta \sum_{t=0}^H \log \pi_\theta\left(a_t^{(i)} \mid s_t^{(i)}\right)
$$
---

Since neither initial state distribution or state transition dynamics of the MDP are dependent of $\theta$, the derivate of both terms are 0 . So we can remove them:
Since: $\nabla_\theta \sum_{t=0}^H \log P\left(s_{t+1}^{(i)} \mid s_t^{(i)} a_t^{(i)}\right)=0$ and $\nabla_\theta \mu\left(s_0\right)=0$
$$
\nabla_\theta \log P\left(\tau^{(i)} ; \theta\right)=\nabla_\theta \sum_{t=0}^H \log \pi_\theta\left(a_t^{(i)} \mid s_t^{(i)}\right)
$$
---

We can rewrite the gradient of the sum as the sum of gradients:
$$
\nabla_\theta \log P\left(\tau^{(i)} ; \theta\right)=\sum_{t=0}^H \nabla_\theta \log \pi_\theta\left(a_t^{(i)} \mid s_t^{(i)}\right)
$$
So, the final formula for estimating the policy gradient is:
$$
\nabla_\theta J(\theta)=\hat{g}=\frac{1}{m} \sum_{i=1}^m \sum_{t=0}^H \nabla_\theta \log \pi_\theta\left(a_t^{(i)} \mid s_t^{(i)}\right) R\left(\tau^{(i)}\right)
$$
# Coding
See the dedicated note: [[HF DRL Coding - Unit 4]]
