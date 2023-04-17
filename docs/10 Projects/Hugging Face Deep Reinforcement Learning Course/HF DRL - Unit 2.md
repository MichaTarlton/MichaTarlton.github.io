---
type: log
status: active
priority: p2
project: HF-DRL-course
creationtag: 2022-12-15 16:57
infotags: [course, RL, DRL, dev, programming, Q-learning, temporal difference]
people:
date:
---
web:: https://huggingface.co/deep-rl-course/unit2/

# Introduction
![[image-20221215182917187.png]]


## Value-Based Methods
- Two different types
![[image-20221215182841257.png]]


### State-Value Function
- **In state-value function, we calculate **the value of a state $S_t$****

### Action-Value Function
-   In action-value function, we calculate **the value of the state-action pair $( S_t, A_t)$ hence the value of taking that action at that state.**

## [[Bellman Equation]]
> Instead of calculating the expected return for each state or each state-action pair, **we can use the Bellman equation.** (hint: if you know what Dynamic Programming is, this is very similar! if you don’t know what it is, no worries!)

![[image-20221215183548183.png]]

- What does **Discounted value** mean?
	- Literally just use gamma to add some discount to the value
	- not sure why

> **The Bellman equation is a recursive equation** that works like this: instead of starting for each state from the beginning and calculating the return, we can consider the value of any state as:
> 
> $Rt+1 + gamma * V(St+1)$
> 
> The immediate reward + the discounted value of the state that follows

## Temporal Difference 
![[image-20221216165840477.png]]

If we take the same example,
> -   We just started to train our value function, so it returns 0 value for each state.
>
> -   Our learning rate (lr) is 0.1, and our discount rate is 1 (no discount).
>
> -   Our mouse explore the environment and take a random action: **going to the left**
>
> -   It gets a reward $R_{t+1} = 1$ since **it eats a piece of cheese**
> 
> - We can now update $V(S_0)$:
> 
> - New $V(S_0) = V(S_0) + lr * [R_1 + \gamma * V(S_1) - V(S_0)]$
> 
> - New $V(S_0) = 0 + 0.1 * [1 + 1 * 0–0]$
> 
> - New $V(S_0) = 0.1$
> 
> - So we just updated our value function for State 0.
>
> Now we **continue to interact with this environment with our updated value function.**

- Ok so Action is at state t+1?
- Regardless the point is that the reward is given at the current action step (which isn’t t 🙄)

### vs Monte Carlo 
![[image-20221216170708226.png]]

[[Nomenclature for Experiments]]

# Q-Learning
Q-Learning is an **off-policy value-based method that uses a TD approach to train its action-value function:**

-   _Off-policy_: we’ll talk about that at the end of this unit.
-   _Value-based method_: finds the optimal policy indirectly by training a value or action-value function that will tell us **the value of each state or each state-action pair.**
-   _Uses a TD approach:_ **updates its action-value function at each step instead of at the end of the episode.**

**Q-Learning is the algorithm we use to train our Q-Function**, an **action-value function** that determines the value of being at a particular state and taking a specific action at that state.

If we recap, _Q-Learning_ **is the RL algorithm that:**

-   Trains a _Q-Function_ (an **action-value function**), which internally is a **Q-table that contains all the state-action pair values.**
-   Given a state and action, our Q-Function **will search into its Q-table the corresponding value.**
-   When the training is done, **we have an optimal Q-function, which means we have optimal Q-Table.**
-   And if we **have an optimal Q-function**, we **have an optimal policy** since we **know for each state what is the best action to take.**
 
 Our $Q(S_t, A_t)$ **update formula goes like this:**
 ![[image-20221216173046858.png]]

It means that to update our $Q(S_t, A_t)$:

-   We need $S_t, A_t, R_{t+1}, S_{t+1}$.
-   To update our Q-value at a given state-action pair, we use the TD target.

How do we form the TD target?

1.  We obtain the reward after taking the action $R_{t+1}$.
2.  To get the **best next-state-action pair value**, we use a greedy policy to select the next best action. Note that this is not an epsilon greedy policy, this will always take the action with the highest state-action value.

Then when the update of this Q-value is done, we start in a new state and select our action **using a epsilon-greedy policy again.**


## Off-policy vs On-policy
#policy 

The difference is subtle:

-   **_Off-policy_:** using **a different policy for acting (inference) and updating (training).**

For instance, with Q-Learning, the epsilon greedy policy (acting policy), is different from the greedy policy that is **used to select the best next-state action value to update our Q-value (updating policy).**

-   **_On-policy:_** using the **same policy for acting and updating.**

For instance, with Sarsa, another value-based algorithm, **the epsilon greedy Policy selects the next state-action pair, not a greedy policy.**

![[image-20221216174258014.png]]

![[image-20221216174405810.png]]

