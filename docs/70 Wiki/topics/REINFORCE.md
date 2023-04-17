---
aliases: [monte carlo reinforce,]
type: topics
status: open
priority: p4
creationtag: 2023-01-12 16:57
infotags: [rl, algorithm, stochastic, policy, gradient, based, method]
---

See also [[derivative log trick]] as I think it’s the same thing and they are botching the delivery.

## From [PyTorch documentation](https://pytorch.org/docs/stable/distributions.html):
> It is not possible to directly backpropagate through random samples. However, there are two main methods for creating surrogate functions that can be backpropagated through. These are the score function estimator/likelihood ratio estimator/REINFORCE and the pathwise derivative estimator. REINFORCE is commonly seen as the basis for policy gradient methods in reinforcement learning, and the pathwise derivative estimator is commonly seen in the reparameterization trick in variational autoencoders. Whilst the score function only requires the value of samples f(x)f(x), the pathwise derivative requires the derivative f'(x)f′(x). The next sections discuss these two in a reinforcement learning example. For more details see [Gradient Estimation Using Stochastic Computation Graphs](https://arxiv.org/abs/1506.05254) .
> 
> [**Score function**](https://pytorch.org/docs/stable/distributions.html#score-function)
 > When the probability density function is differentiable with respect to its parameters, we only need `sample()` and `log_prob()` to implement REINFORCE:
 > $$\Delta\theta = \alpha r \frac{\partial\log p(a|\pi^\theta(s))}{\partial\theta}$$
> where $\theta$ are the parameters, $α$ is the learning rate, $r$ is the reward and $p(a|\pi^\theta(s))$ is the probability of taking action $a$ in state $s$ given policy $\pi^\theta$ .
> 
> In practice we would sample an action from the output of a network, apply this action in an environment, and then use `log_prob` to construct an equivalent loss function. Note that we use a negative because optimizers use gradient descent, whilst the rule above assumes gradient ascent.


## From [[HF DRL - Unit 4]]:
This is the Reinforce algorithm pseudocode:
![[image-20230112172103375.png]]
-   When we calculate the return Gt (line 6), we see that we calculate the sum of discounted rewards **starting at timestep t**.
    
-   Why? Because our policy should only **reinforce actions on the basis of the consequences**: so rewards obtained before taking an action are useless (since they were not because of the action), **only the ones that come after the action matters**.
    
-   Before coding this you should read this section [don’t let the past distract you](https://spinningup.openai.com/en/latest/spinningup/rl_intro3.html#don-t-let-the-past-distract-you) that explains why we use reward-to-go policy gradient.

We use an interesting technique coded by [Chris1nexus](https://github.com/Chris1nexus) to **compute the return at each timestep efficiently**. The comments explained the procedure. Don’t hesitate also [to check the PR explanation](https://github.com/huggingface/deep-rl-class/pull/95) But overall the idea is to **compute the return at each timestep efficiently**

# Query
```query 
line:("REINFORCE") OR  line:("monte carlo reinforce") 
```