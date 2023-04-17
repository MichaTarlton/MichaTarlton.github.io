---
type: [log, development]
status: active
priority: p2
project: HF-DRL-course
creationtag: 2023-02-08 12:02
infotags: [course, RL, DRL, dev, programming, Q-learning, temporal difference]
people:
date:
---
See: [[HF DRL - Unit 4]]
# Testing against a polecart environment from RL gym
Maybe break out into own note
## Colab Notebook
<iframe src="https://colab.research.google.com/drive/1Eyb6ncBHMWzNUlviOsE0aBsK30dVkWOq?usp=sharing" allow="fullscreen" allowfullscreen="" style="height:100%;width:100%; aspect-ratio: 16 / 9; "></iframe>

## Import the package
``` python
import numpy as np
 
from collections import deque

import matplotlib.pyplot as plt
%matplotlib inline
 
# PyTorch

import torch

import torch.nn as nn

import torch.nn.functional as F

import torch.optim as optim

from torch.distributions import Categorical

  

# Gym

import gym

import gym_pygame

  

# Hugging Face Hub

from huggingface_hub import notebook_login # To log to our Hugging Face account to be able to upload models to the Hub.

import imageio
```
### Breaking down the code
#pytorch
#### `import torch.nn as nn`
Kinda jus the most basic of pytorch


##### From torch tutorial
Made a colab notebook here: https://colab.research.google.com/drive/1nIPsZdTWmpu7mrBiSWL9i6JKwnzOVx4E?usp=sharing
<iframe src="https://pytorch.org/tutorials/beginner/nn_tutorial.html" allow="fullscreen" allowfullscreen="" style="height:100%;width:100%; aspect-ratio: 16 / 9; "></iframe>

#### `import torch.nn.functional as F`
> This module contains all the functions in the `torch.nn` library (whereas other parts of the library contain classes). As well as a wide range of loss and activation functions, you'll also find here some convenient functions for creating neural nets, such as pooling functions. (There are also functions for doing convolutions, linear layers, etc, but as we'll see, these are usually better handled using other parts of the library.)

#### `import torch.optim as optim`

#### `from torch.distributions import Categorical`





## Let's build the Reinforce Architecture
So we want:

-   Two fully connected layers (fc1 and fc2).
-   Using [[ReLU]] as activation function of fc1
-   Using [[Softmax]] to output a probability distribution over actions

This implementation is based on two implementations:

-   [PyTorch official Reinforcement Learning example](https://github.com/pytorch/examples/blob/main/reinforcement_learning/reinforce.py)
-   [Udacity Reinforce](https://github.com/udacity/deep-reinforcement-learning/blob/master/reinforce/REINFORCE.ipynb)
-   [Improvement of the integration by Chris1nexus](https://github.com/huggingface/deep-rl-class/pull/95)
![[image-20230112152152953.png]]

``` python
class Policy(nn.Module):
    def __init__(self, s_size, a_size, h_size): # sample space, action space, ? space
        super(Policy, self).__init__()
		# Create two fully connected layers
        self.fc1 = nn.Linear(s_size, h_size) # applies linear transform
        self.fc2 = nn.Linear(h_size, a_size)

    def forward(self, x):
        x = F.relu(self.fc1(x)) # not entirely seeing how this makes them fully connected
        x = self.fc2(x)
        return F.softmax(x, dim=1)

    def act(self, state):
        state = torch.from_numpy(state).float().unsqueeze(0).to(device)
        probs = self.forward(state).cpu()
        m = Categorical(probs)
        #action = np.argmax(m) see why we replace this below
        action = m.sample()
        return action.item(), m.log_prob(action)
```

### Breaking down this code block
### **`class Policy(nn.Module)`**
A python class for pytorch functions
> Next up, we'll use `nn.Module` and `nn.Parameter`, for a clearer and more concise training loop. We subclass `nn.Module` (which itself is a class and able to keep track of state). In this case, we want to create a class that holds our weights, bias, and method for the forward step. `nn.Module` has a number of attributes and methods (such as `.parameters()` and `.zero_grad()`) which we will be using.
> 
> Note> 
> `nn.Module` (uppercase M) is a PyTorch specific concept, and is a class we'll be using a lot. ``nn.Module`` is not to be confused with the Python concept of a (lowercase ``m``) [module](https://docs.python.org/3/tutorial/modules.html), which is a file of Python code that can be imported.

<iframe src="https://pytorch.org/docs/stable/generated/torch.nn.Module.html" allow="fullscreen" allowfullscreen="" style="height:100%;width:100%; aspect-ratio: 16 / 9; "></iframe>

https://pytorch.org/docs/stable/nn.html
###  `def __init__(self, s_size, a_size, h_size):`
The variables are defined earlier as aspects of the environment
```  python
# Get the state space and action space
s_size = env.observation_space.shape[0]
a_size = env.action_space.n
```
`h_size` is input later

### `super(Policy, self)
super function is a whole thing unto itself.
Apparently for referencing a class indirectly
https://www.artima.com/weblogs/viewpost.jsp?thread=236275
https://rhettinger.wordpress.com/2011/05/26/super-considered-super/
https://docs.python.org/2/library/functions.html#super

#### Stack exchange post on `super`
<iframe src="https://stackoverflow.com/questions/576169/understanding-python-super-with-init-methods" allow="fullscreen" allowfullscreen="" style="height: 100%; width: 100%; aspect-ratio: 1 / 1;"></iframe>




### Creating two fully connected layers
Looks like the first one takes in the env state inputs
and the second one outputs the actions


``` python 
# Create two fully connected layers
        self.fc1 = nn.Linear(s_size, h_size)
        self.fc2 = nn.Linear(h_size, a_size)
        ```
### Assigning node types to layers?
Not entirely certain what is going on here.
I guess, x is some value that is being updated based on the functions being applied to it at each layer?

``` python
def forward(self, x):
        x = F.relu(self.fc1(x))
        x = self.fc2(x)
        return F.softmax(x, dim=1)
```


### updating state of network?
Not certain what is happening here either
looks like it is taking the “state” and probabilities(?) from the network 
What does categorical do? See: [Probability distributions - torch.distributions — PyTorch 1.13 documentation](https://pytorch.org/docs/stable/distributions.html)[^1]
> The `distributions` package contains parameterizable probability distributions and sampling functions. This allows the construction of stochastic computation graphs and stochastic gradient estimators for optimization. This package generally follows the design of the [TensorFlow Distributions](https://arxiv.org/abs/1711.10604) package.
> It is not possible to directly backpropagate through random samples. However, there are two main methods for creating surrogate functions that can be backpropagated through. These are the score function estimator/likelihood ratio estimator/REINFORCE and the pathwise derivative estimator. REINFORCE is commonly seen as the basis for policy gradient methods in reinforcement learning, and the pathwise derivative estimator is commonly seen in the reparameterization trick in variational autoencoders. Whilst the score function only requires the value of samples f(x)f(x), the pathwise derivative requires the derivative f'(x)f′(x). The next sections discuss these two in a reinforcement learning example. For more details see [Gradient Estimation Using Stochastic Computation Graphs](https://arxiv.org/abs/1506.05254) .

Taking an argmax of probabilities and returning that as “action”???”

- Apparently there is a mistake in this code. When trying to run .
- Ah it is because the argmax will take the action with the highest probability when we want it to sample an action from prob. dist. ‘P(.|s)’[^3]
- Replace with `action = m.sample()`
- Returning to this some months later, I’m uncertain what the out put type is of the data
	- Presumably the argmax is a single value output

## Let's build the Reinforce Training Algorithm

This is the Reinforce algorithm pseudocode:
![[image-20230112172103375.png]]
[^4]
-   When we calculate the return $G_t$ (line 6), we see that we calculate the sum of discounted rewards **starting at timestep t**.   
-   Why? Because our policy should only **reinforce actions on the basis of the consequences**: so rewards obtained before taking an action are useless (since they were not because of the action), **only the ones that come after the action matters**.
-   Before coding this you should read this section [don’t let the past distract you](https://spinningup.openai.com/en/latest/spinningup/rl_intro3.html#don-t-let-the-past-distract-you) that explains why we use reward-to-go policy gradient.

We use an interesting technique coded by [Chris1nexus](https://github.com/Chris1nexus) to **compute the return at each timestep efficiently**. The comments explained the procedure. Don’t hesitate also [to check the PR explanation](https://github.com/huggingface/deep-rl-class/pull/95) But overall the idea is to **compute the return at each timestep efficiently**.

The second question you may ask is **why do we minimize the loss**? Did you talk about Gradient Ascent, not Gradient Descent?

-   We want to maximize our utility function $J(\theta)$, but in PyTorch and TensorFlow, it’s better to **minimize an objective function.**
    -   So let’s say we want to reinforce action 3 at a certain timestep. Before training this action P is 0.25.
    -   So we want to modify $\theta$ such that $\pi_\theta(a_3|s; \theta) > 0.25$
    -   Because all P must sum to 1, max $\pi_\theta(a_3|s; \theta)$ will **minimize other action probability.**
    -   So we should tell PyTorch **to min $1 - \pi_\theta(a_3|s; \theta)$.**
    -   This loss function approaches 0 as $\pi_\theta(a_3|s; \theta)$ nears 1.
    -   So we are encouraging the gradient to max $\pi_\theta(a_3|s; \theta)$

``` python
def reinforce(policy, optimizer, n_training_episodes, max_t, gamma, print_every):
    # Help us to calculate the score during the training
    scores_deque = deque(maxlen=100)
    scores = []
    # Line 3 of pseudocode
    for i_episode in range(1, n_training_episodes + 1):
        saved_log_probs = []
        rewards = []
        state = env.reset()
        # Line 4 of pseudocode
        for t in range(max_t):
            action, log_prob = policy.act(state)
            saved_log_probs.append(log_prob)
            state, reward, done, _ = env.step(action)
            rewards.append(reward)
            if done:
                break
        scores_deque.append(sum(rewards))
        scores.append(sum(rewards))

        # Line 6 of pseudocode: calculate the return
        returns = deque(maxlen=max_t)
        n_steps = len(rewards)
        # Compute the discounted returns at each timestep,
        # as
        #      the sum of the gamma-discounted return at time t (G_t) + the reward at time t
        #
        # In O(N) time, where N is the number of time steps
        # (this definition of the discounted return G_t follows the definition of this quantity
        # shown at page 44 of Sutton&Barto 2017 2nd draft)
        # G_t = r_(t+1) + r_(t+2) + ...

        # Given this formulation, the returns at each timestep t can be computed
        # by re-using the computed future returns G_(t+1) to compute the current return G_t
        # G_t = r_(t+1) + gamma*G_(t+1)
        # G_(t-1) = r_t + gamma* G_t
        # (this follows a dynamic programming approach, with which we memorize solutions in order
        # to avoid computing them multiple times)

        # This is correct since the above is equivalent to (see also page 46 of Sutton&Barto 2017 2nd draft)
        # G_(t-1) = r_t + gamma*r_(t+1) + gamma*gamma*r_(t+2) + ...

        ## Given the above, we calculate the returns at timestep t as:
        #               gamma[t] * return[t] + reward[t]
        #
        ## We compute this starting from the last timestep to the first, in order
        ## to employ the formula presented above and avoid redundant computations that would be needed
        ## if we were to do it from first to last.

        ## Hence, the queue "returns" will hold the returns in chronological order, from t=0 to t=n_steps
        ## thanks to the appendleft() function which allows to append to the position 0 in constant time O(1)
        ## a normal python list would instead require O(N) to do this.
        for t in range(n_steps)[::-1]:
            disc_return_t = returns[0] if len(returns) > 0 else 0
            returns.appendleft(gamma * disc_return_t + rewards[t])

        ## standardization of the returns is employed to make training more stable
        eps = np.finfo(np.float32).eps.item()
        ## eps is the smallest representable float, which is
        # added to the standard deviation of the returns to avoid numerical instabilities
        returns = torch.tensor(returns)
        returns = (returns - returns.mean()) / (returns.std() + eps)

        # Line 7:
        policy_loss = []
        for log_prob, disc_return in zip(saved_log_probs, returns):
            policy_loss.append(-log_prob * disc_return)
        policy_loss = torch.cat(policy_loss).sum()

        # Line 8: PyTorch prefers gradient descent
        optimizer.zero_grad()
        policy_loss.backward()
        optimizer.step()

        if i_episode % print_every == 0:
            print("Episode {}\tAverage Score: {:.2f}".format(i_episode, np.mean(scores_deque)))

    return scores
```



[^1]: Actually this is really great just for a summary of how everything is working here from REINFORCE to the code
[^2]: I think
[^3]: Not sure what they mean by this, should obviously be P(a|s) right?
[^4]: What is $G_t$ here?