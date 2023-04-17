---
type: reading
---

See [[Granmo 2010 Topics]]
See [[Granmo 2010 Comments]]

# Solving Stochastic Nonlinear Resource Allocation Problems Using a Hierarchy of Twofold Resource Allocation Automata

Skipping 1.1

# 1.2
> The above problem instances can be formulated as _Stochastic Nonlinear Fractional Equality Knapsack (NEFK) Problems_ as exemplified earlier [7], [8], [9].

## **The linear fractional knapsack (FK) problem**. 
> The linear FK problem is a classical continuous optimization problem which also has applications within the field of resource allocation. 
> The problem involves 
> $n$ materials 
> of different value $v_i$ 
> per unit volume, $1≤i≤n$, 
> where each material is available in a certain amount $x_i≤b_i$. 
> Let $f_i(x_i)$ denote the value of the amount $x_i$ of material $i$, i.e., $f_i(x_i)=v_ix_i$. The problem is to fill a knapsack of fixed volume $c$ with the material mix $x⃗ =[x_1,…,x_n]$ of maximal value $∑n_1f_i(x_i)$ [2].

## **The nonlinear equality FK (NEFK) problem**. 
> One important extension of the above classical problem is the _Nonlinear_ _Equality_ FK problem with a separable and concave objective function. The problem can be stated as follows [13]: 
> **Maximize:**   ${f}( \vec{x}) = \sum_{1}^n f_i(x_i)$
> **subject to: ** $\sum_{1}^n x_i = c \quad {\rm and}\quad \forall i \in \{1, \ldots, n \}, x_i \ge 0.$

> Since the objective function is considered to be concave, the value function fi(xi) of each material is also concave. This means that the derivatives of the material value functions fi(xi) with respect to xi (hereafter denoted f′i), are nonincreasing. In other words, the material value _per unit volume_ is no longer constant as in the linear case, but decreases with the material amount, and so the optimization problem becomes:

**Maximize**$${f}( \vec{x}) = \sum_{1}^n f_i(x_i), \;{\rm where }\; f_i(x_i) = \int^{x_i}_0 f_i^{\prime }(x_i) dx_i,$$
**Subject to** $$\sum_{1}^n x_i = c\quad{\rm and}\quad \forall i \in \{1, \ldots, n \}, x_i \ge 0.$$

> Efficient solutions to the latter problem, based on the principle of Lagrange multipliers, have been devised. In short, the optimal value occurs when the derivatives f′i of the material value functions are equal, subject to the knapsack constraints [3], [5]:$$\eqalign{ f^{\prime }_1(x_1) &= \cdots = f^{\prime }_n(x_n),\hfill\cr \sum_{1}^n x_i &= c\quad {\rm and}\quad \forall i \in \{1, \ldots, n \}, x_i \ge 0.}$$

Concave fnc, so there is an optimization to be found that is not linear, and the return on value decreases with each item (time?)

## **The stochastic NEFK problem**.
> we let the material value per unit volume for any xi be a _probability_ function pi(xi). Furthermore, we consider the distribution of pi(xi) to be _unknown_. That is, each time an amount xi of material i is placed in the knapsack, we are only allowed to observe an instantiation of pi(xi) at xi, and not pi(xi) itself.

> we are provided with a knapsack of fixed volume c, which is to be filled with a mix of n different materials. 
> However, unlike the NEFK, in the Stochastic NEFK Problem the unit volume value of a material $i$, $1≤i≤n$, is a random quantity
> —it takes the value 1 with probability $p_i(x_i)$ 
> and the value 0 with probability $1−p_i(x_i)$, respectively. 

So all or nothing for the value, it is 1 or it is 0
but like 69% 1 and 31% 0

> As an additional complication, $p_i(x_i)$ is nonlinear in the sense that it decreases monotonically with $x_i$, 
> i.e., $x_{i_1}≤x_{i_2}⇔p_i(x_{i_1})≥p_i(x_{i_2})$.

So probability of value = 1 decreases as → i 

> Since unit volume values are random, we operate with expected unit volume values rather than the actual unit volume values. 
> With this understanding, and the above perspective in mind, the expected value of the amount $x_i$ of material i, $1≤i≤n$, becomes $f_i(x_i)=∫^{x_i}_{0} p_i(u)du$. 
> 
> Accordingly, the expected value per unit volume of material i becomes $f′_i(x_i)=p_i(x_i)$. In this stochastic and nonlinear version of the FK problem, the goal is to fill the knapsack so that the expected value $f(x⃗)=∑^n_1f_i(x_i)$ of the material mix contained in the knapsack is maximized. Thus, we aim to:
> **maximize:** $${f}( \vec{x}) = \sum_{1}^n f_i(x_i),$$
> **where:** $$f_i(x_i) = \int^{x_i}_0 p_i(u)du$$
> **And:** $$p_i(x_i) = f_i^{\prime }(x_i)$$
> **subject to:** $$\sum_{1}^n x_i = c\quad {\rm and }\quad \forall i \in \{1, \ldots, n \}, x_i \ge 0.$$

> A fascinating property of the above problem is that the amount of information available to the decision maker is limited—the decision maker is only allowed to observe the current unit value of each material (either 0 or 1). 
> 
> That is, each time a material mix is placed in the knapsack, the unit value of each material is provided to the decision maker. The actual outcome probabilities pi(xi),1≤i≤n, however, remain _unknown_.
> 
> As a result of the latter, the expected value of the material mix must be maximized by means of trial-and-failure, i.e., by experimenting with different material mixes and by observing the resulting random unit-value outcomes.

# 2.0 ## A Hierarchy of Twofold Resource Allocation Automata (H-TRAA)

Algorithmic Solution for Linear FK problem
>  Because a fraction of each material can be placed in the knapsack, the following greedy algorithm from [2] finds the most valuable mix: _Take as much as possible of the material that is most valuable per unit volume. If there is still room, take as much as possible of the next most valuable material. Continue until the knapsack is full._

This of course would mean we know the value of each material type

> generalize this and assume that the material unit volume values are _random_ variables with _constant_ and _known_ distributions.
> 
> for the sake of conceptual clarity, let us only consider binary variables that _either_ instantiate to the values of 0 or 1
> 
> let pi denote the probability of the unit volume value vi=1 for material i, 1≤i≤n, which means that the probability of the unit volume value vi=0 becomes 1−pi
> 
> With some insight, it becomes evident that under such conditions, the above greedy strategy can again be used to maximize the _expected_ value of the knapsack, simply by selecting material based on the _expected_ unit volume values, E[vi]=0×(1−pi)+1×pi, rather than actual unit volume values.

Ok so essentially the same strat bt linear and probable models, except for in the prob model we select the highest expected value for material.

I think we are just explaing rl selection so far.

> The above indicated solution is, of course, inadequate when the pi s are unknown. Furthermore, the problem becomes even more challenging when the pi s are no longer constant, but rather depend on their respective material amounts xi, 1≤i≤n. 
> 
> Let pi(xi) denote the probability that the current unit volume value of material i is vi=1, given that the amount xi has already been placed in the knapsack. 

So here we create an expectation value based on our average score from material xi plucked

> Then, the expected value per unit volume of material i, 1≤i≤n, becomes E[vi]=0×[1−pi(xi)]+1×pi(xi)=pi(xi), and accordingly, the expected value of the amount xi becomes fi(xi)=∫xi0pi(u)du.

Moving on to the more stochastic solution

> Because of the above intricacies, we approach the problem by relying on informed material mix _guesses_, i.e., by experimenting with different material mixes and learning from the resulting random unit volume value outcomes. We shall assume that xi is any number in the interval (0,1). 
> 
> The question of generalizing this will be considered later. The crucial issue that we have to address, then, is that of determining how to change our current guesses on xi,1≤i≤n. 

> We shall attempt to do this in a discretized manner by subdividing the unit interval into $N$ points ${\frac{1}{N+1},\frac{2}{N+1},…,\frac{N}{N+1}}$, where **$N$ is the resolution of the learning scheme. We will see that a larger value of N will ultimately imply a more accurate solution to the knapsack problem.**

Not sure what’s up with the intervals. As in what is this intervals of?
I think the resolution is arbitrary and decided by levelof granularityyou want to the solution accuracy.

See [[Oomen 2017]]

## Contributions
This paper designs to update from this paper in order to add additional features:
1. remove “oracle”
2. use a hierarchy of LAs working in synchrony
3. study performance in “space varying responses from the environment”
	- I assume this means the envrionment respnding to option selection with probablistic variance in the response rewards
4. “Applicable to time varying environments” 
	- Which I take to mean it scales to any width of timestep
	- 
5. The previous is “truly” Ergodic, while this one is not.
> Unlike the latter, in which the system is truly ergodic, our present LA would be absorbing if the end-states of the probability space are also included. However, to forcefully render this present machine ergodic, we have artificially made the LA ergodic by excluding these states from the set of possible probability values.
- Really not sure what is meant by asorbing or “end states” here
- 


## 2.2 & 2.3 Details of the (H)TRAA Solution
Skipping over section 2.2.2 Analysis ofthe TRAA (which I will put below) so I can go directly from TRAA to H-TRAA

### Stochastic environment
- Delivers the reward value based on some probablistic method in response to option selection (from EDF scheduler)
- The probability $P_i(x_i)$ is unknown to the **TRAA**
- 

> **Stochastic Environment.** The Stochastic Environment for the two-material case can be characterized by:
> 1. the capacity $c$ of the knapsack; and
> 2. two-material unit volume value probability functions $p_{1}\left(x_{1}\right)$ and $p_{2}\left(x_{2}\right)$.
> In brief, if the amount $x_{i}$ of material $i$ is suggested to the Stochastic Environment, the Environment replies with a unit volume value $v_{i}=1$ with probability $p_{i}\left(x_{i}\right)$ and a unit volume value $v_{i}=0$ with probability $1-p_{i}\left(x_{i}\right), i \in\{1,2\}$. It should be emphasized that to render the problem both interesting and nontrivial, we assume that $p_{i}\left(x_{i}\right)$ is unknown to the TRAA.




### EDF Scheduler
- SO I know the least about this part,and couldn’t really decipher what it actually *does*
- “accesses the functions according to $\vec{x}$"
- “EDF Scheduler, which suggests which unit volume value function $p_{i}\left(x_{i}\right)$ to access next.”
- “Finally, a new candidate material mix $\vec{x}=\left[x_{1}, \ldots, x_{n}\right]$ is suggested by the H-TRAA to the EDF Scheduler.”
- According to the schema it is the portion which makes some selectionof the environment based on the input from the TRAA

> EDF Scheduler. The Scheduler takes material amounts $\vec{x}=\left[x_{1}, \ldots, x_{n}\right]$ as its input (for the two-material case the input is $\left.\vec{x}=\left[x_{1}, x_{2}\right]\right)$. The purpose of the Scheduler is:
> 
> 1. to provide accesses to the Stochastic Environment in a sequential manner, and
> 2. to make sure that the unit volume value functions are accessed with frequencies proportional to $\vec{x}$.
> 
> The reader should note that our scheme does not rely on accessing the unit volume value functions sequentially with frequencies proportional to $\vec{x}$ for solving the knapsack problem. 
> 
> However, this restriction is obviously essential for solving the problem incrementally and online (or rather in a “real-time” manner). 
> 
> Note that since it, in some cases, may be essential to access each unit volume value function with a constant period and not randomly (for example, in the earlier-alluded-to problem which analyzes webpage polling), we use the EDF Scheduling to access the functions according to $\vec{x}$.




### TRAA
-  Don’t let the states distract you, it is a finte automata with finite states according to $N$
- This is the step which takes the reward and then decides the probability state in which the machine is in based on the reward input
- where $r_{s(t)}$ and $q_{s(t)}$ are the *reward probability* for either of the choosable options
- And at each step the probabilities are updated based on the reward
- and this is outpput to the EDF scheduler

> TRAA. The scheme which attempts to learn the optimal allocation $\vec{x}^{*}=\left[x_{1}^{*}, x_{2}^{*}\right]$ can be described as follows: A finite fixed structure automaton with the states $s(t) \in\{1,2, \ldots, N\}$ is used to decide the allocation of resources among the two materials. Let the current state of the automaton be $s(t)$. Furthermore, let $q_{s(t)}$ refer to the fraction $\frac{s(t)}{N+1}$, and let $r_{s(t)}$ refer to the fraction: $1-q_{s(t)}$. Then, the automaton's current guess is $\vec{x}=\left[q_{s(t)}, r_{s(t)}\right]$.
> 
> If the Stochastic Environment tells the automaton that the unit volume value of material $i$ is $v_{i}(t)$ at time $t$, the automaton updates its state as follows:
> $s(t+1):=s(t)+1 \quad$ If $\operatorname{rand}() \leq r_{s(t)}$ and $v_{i}(t)=1$ and $1 \leq s_{i}(t)<N$ and $i=1$,
> $s(t+1):=s(t)-1 \quad$ If $\operatorname{rand}() \leq q_{s(t)}$ and $v_{i}(t)=1$ and $1<s_{i}(t) \leq N$ and $i=2$,
> $$
 s(t+1):=s(t) \quad \text { Otherwise. }
 $$
> 

- Pretty sure $rand()$ here is just a uniformly random distribution, to compare against the reward probabilities
- 


### Hierarchial-TRAA
- $n$-material problems
	- Where $n$ is the number of materials 
	- until now we were just doing $n=2$
- The binary options are now sets and subsets of options
- Where starting with the first layer (or *Depth* as they call it) the full set is bifurcated into two subsets
- Which the TRAA at that layer then performs its choice evaluation for those subsets
- The next layer then takes one of the two sets from the previous layer
- and then bifurcates that into two more subsets
- repeating the option set evaluation

> Root node. The hierarchy root (at depth 1 ) is assigned the complete set of materials $S_{1,1}=\{1, \ldots, n\}$. These $n$ materials are partitioned into two disjoint and exhaustive subsets of equal size: $S_{2,1}$ and $S_{2,2}$. An associated TRAA, $T_{1,1}$, decides how to divide the full knapsack capacity $c$ (which, for the sake of notational correctness will be referred to as $c_{1,1}$ ) among the two subsets. That is, subset $S_{2,1}$ receives the capacity $c_{2,1}$ and subset $S_{2,2}$ receives the capacity $c_{2,2}$, with $c_{2,1}+c_{2,2}=c_{1,1}$. Accordingly, this TRAA is given the power to prioritize one subset of the materials at the expense of the other.
- Subnotation here referes to $i$ depth and $j$  subset
- 


> **Interaction of H-TRAA with EDF scheduler and environment.** 
> As in the single TRAA case, H-TRAA interacts with an EDF Scheduler, which suggests which unit volume value function $p_{i}\left(x_{i}\right)$ to access next. A response is then generated from the Stochastic Environment using $p_{i}\left(x_{i}\right)$. This response is given to all the TRAAs that were involved in determining the material amount $x_{i}$, that is, the TRAAs in the hierarchy that have allocated capacity to a material subset that contains material $i$. Finally, a new candidate material mix $\vec{x}=\left[x_{1}, \ldots, x_{n}\right]$ is suggested by the H-TRAA to the EDF Scheduler.
> 
> **Example 1.** 
> Consider a four-material problem. Fig. 4 shows the associated hierarchy, constructed as described above. At the root level, the TRAA $T_{1,1}$ divides the knapsack capacity among the two-material subsets $\{1,2\}$ and $\{3,4\}$, respectively, related to TRAA $T_{2,1}$ and $T_{2,2}$. At the level below, then, the TRAA $T_{2,1}$ allocates its share of the capacity among material 1 and material 2, while TRAA $T_{2,2}$ assigns its share of the capacity to material 3 and material 4. Based on the present assignment at time $t$, the EDF Scheduler selects material $i$, suggesting the amount $x_{i}(t)$ to the Stochastic Environment. The Stochastic Environment, in turn, responds with a randomly drawn material unit volume value, $v_{i}(t)$, using the probability value function $p_{i}\left(x_{i}\right)$. By way of example, if $i=2$, the latter feedback is given to TRAAs $T_{1,1}$ and $T_{2,1}$, which update their states accordingly, and the feedback loop continues.
- So EDF selects one material and “suggests” “amount”?
- Amount present or amount to grab?
- I asked at this point what the stochastic env is doing,what $p(x)$ is but it’s already apparent at ths poin that it is some uknown process
- $P$ is the porbability that $v$ will have a value of 0 or 1

 ## Analysis of 2.2.2 and 2.2.3
 skipping for now
