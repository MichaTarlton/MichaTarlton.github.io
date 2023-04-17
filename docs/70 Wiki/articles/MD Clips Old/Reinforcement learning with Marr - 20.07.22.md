---
type: web article
creationtag: 2022-07-20 12:04
URL: "https://www.sciencedirect.com/science/article/pii/S2352154616300821"
people: []
infotags: [RL, Marr]
project:
citekey: nivReinforcementLearningMarr2016
---

> [!Excerpt] Reinforcement learning with Marr - ScienceDirect
> To many, the poster child for David Marr's famous three levels of scientific inquiry is reinforcement learning — a computational theory of reward opti…

---
[![[70 Wiki/articles/MD Clips Old/Reinforcement learning with Marr/elsevier-non-solus.png]]](https://www.sciencedirect.com/journal/current-opinion-in-behavioral-sciences "Go to Current Opinion in Behavioral Sciences on ScienceDirect")

[![[1-s2.0-S2352154615X00106-cov150h.gif]]](https://www.sciencedirect.com/journal/current-opinion-in-behavioral-sciences/vol/11/suppl/C)

## Highlights

•

Reinforcement learning as a field spans all three of Marr's levels of analysis.

•

Despite much progress, open questions remain at every level.

•

These call for multidisciplinary research that crosses boundaries between levels.

To many, the poster child for David Marr's famous three levels of scientific inquiry is reinforcement learning — a computational theory of reward optimization, which readily prescribes algorithmic solutions that evidence striking resemblance to signals found in the brain, suggesting a straightforward neural implementation. Here we review questions that remain open at each level of analysis, concluding that the path forward to their resolution calls for inspiration across levels, rather than a focus on mutual constraints.

-   [**Previous**](https://www.sciencedirect.com/science/article/pii/S2352154616301048)
-   [**Next**](https://www.sciencedirect.com/science/article/pii/S2352154616301243)

**Current Opinion in Behavioral Sciences** 2016, **11**:67–73

This review comes from a themed issue on **Computational modeling**

Edited by **Peter Dayan** and **Daniel Durstewitz**

For a complete overview see the [Issue](http://www.sciencedirect.com/science/journal/23521546/11) and the [Editorial](https://doi.org/10.1016/j.cobeha.2016.07.008)

Available online 28th April 2016

[**http://dx.doi.org/10.1016/j.cobeha.2016.04.005**](https://doi.org/10.1016/j.cobeha.2016.04.005)

2352-1546/© 2016 Elsevier Ltd. All rights reserved.

Over the past 25 years, reinforcement learning (RL) has risen from relative obscurity to scientific stardom ([Figure 1](https://www.sciencedirect.com/science/article/pii/S2352154616300821#fig0005)), now encompassing hundreds of researchers in disciplines as varied as economics, computer science, robotics, psychology, ethology, and [neuroscience](https://www.sciencedirect.com/topics/neuroscience/neurosciences "Learn more about neuroscience from ScienceDirect's AI-generated Topic Pages"). Arguably this success can be attributed to the fact that, as a field, RL straddles all three levels of Marr's famous framework of scientific inquiry in computational neuroscience \[[1](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0520)\]. At the *computational* level, RL defines a small set of normative targets (accurately predicting the sum of future rewards, choosing actions that maximize reward attained, etc.). The *algorithmic* level — a host of solutions that achieve these normative goals — elegantly derives directly from the definition of the computational targets \[[2](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0525)\]. In particular, describing decision making problems in terms of Markov (memoryless) decision processes allows for recursive computation of both reward predictions and action values, using local prediction errors \[[3](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0530), [4](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0535)\]. Finally, at the *implementational* level, these algorithms have been closely tied to neural substrates of learning and prediction in the basal ganglia \[[5](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0540), [6](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0545), [7](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0550), [8](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0555)\], and in particular, prediction errors have been linked to [dopaminergic](https://www.sciencedirect.com/topics/neuroscience/dopaminergic "Learn more about dopaminergic from ScienceDirect's AI-generated Topic Pages") signaling in the brain \[[9](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0560), [10](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0565), [11](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0570)\]. At the risk of drawing boundaries that are sometimes artificial, here we summarize at each of these levels recent findings and current open questions in the field of RL as it is studied in the fields of psychology and neuroscience. Marr's levels, as an organizing principle, serve to highlight conceptual differences between questions asked at each level, and how findings at one level can inspire progress in another.

![[1-s2.0-S2352154616300821-gr1.jpg]]

1.  [Download : Download full-size image](https://ars.els-cdn.com/content/image/1-s2.0-S2352154616300821-gr1.jpg "Download full-size image")

Figure 1. Number of papers containing the term ‘reinforcement learning’ published by Nature Publishing Group between 1990 and 2015.

## The computational level: the goals of a decision-making system

At the computational level, the basic goal of an agent or a decision-making system is to maximize reward and minimize punishment. Although one might argue whether this is the true goal of agents from an evolutionary perspective, different definitions of reward and punishment allow considerable flexibility. Indeed, work in recent years has elaborated on what constitutes a reward — in addition to the obvious food and shelter (and their associated conditioned reinforcers) there seem to be other forms of reward that are perhaps similarly primary in nature \[[12](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0575)\]. For instance, ‘curiosity’ can be seen as motivated by the goal of seeking information \[[13](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0580), [14](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0585)\], and work on intrinsic motivation \[[15](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0590)\] has suggested that agents may maximize not only the sum of future rewards, but also the reduction of uncertainty about rewards in the environment \[[16](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0595), [17](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0600), [18](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0605)\]. Moreover, behavioral results, and corresponding neural recordings in monkeys, have convincingly shown that advance information is valuable in of itself, that is, even if this information cannot be acted upon \[[19](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0610), [20](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0615), [21](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0620), [22](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0625), [23](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0630)\].

A related line of work has asked what fictitious, internal rewards an animal (or experimenter) could design, that would assist in ultimately achieving highest fitness in the environment. In this framework of ‘shaping rewards’ the computational-level question is: what is the optimal (pseudo-)reward function with which learning with a specific (possibly limited) set of algorithms would end up maximizing real reward or evolutionary fitness? Recent findings have highlighted that separating the evaluative role of reward functions from their policy-shaping role is beneficial for agents that are bounded (e.g., in terms of the accuracy of their representation of the environment, their capacity for planning, or the learning algorithms they are restricted to use). That is, for different statistics of environments and structure of agents, there exist internal reward functions that lead to faster learning and higher asymptotic behavior, and these are different from the objective reward function \[[24](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0635), [25](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0640)\]. By reinforcing behaviors such as exploration or information seeking that are only indirectly related to objective fitness these internal reward functions mitigate the boundedness of the agent \[[26](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0645)\], although one might argue that this is due to the reward function providing the agent with information (e.g., from past history) that was otherwise unavailable to it. In general, these questions about what constitutes a reward link back to work in the 1940s by Hull \[[27](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0650)\], with the advent of algorithms and neuroscientific tools that allow precise quantification of the reward value of different events resurrecting hitherto unanswerable questions \[[28•](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0655), [29](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0660)\]. Moreover, this question now has practical import, for instance in mobile-health applications and other adaptive interventions where an optimal pseudo-reward function can promote adherence to health recommendations (e.g., exercise regimens) toward the long-term goal of improved health \[[30](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0665), [31](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0670)\].

One relatively neglected computational-level goal for animals is to define (and, algorithmically, learn) an optimal representation for a task. Different representations of the same task can render it easy (in the case of a small number of Markov states, or with states that allow a smooth value function), hard (when unnecessary detail is represented in the states), verging on intractable (for non-Markov partially-observable representations) or even impossible to solve (if information that is critical to task performance is not included in the representation). Different state representations also give rise to values or policies that generalize differently to new tasks \[[32](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0675)\]. Therefore, alongside the normative goal of maximizing reward, one might define a (subsidiary) goal of optimizing task representation. Although RL applications often use a predesigned representation, in the animal (and human) kingdom most task representations are not ‘given’ but rather must be learned through experience, raising the algorithmic question of how this computational goal can be achieved \[[33](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0680)\]. The advent of principled, statistical methods for studying trial-by-trial learning dynamics \[[34](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0685)\] has allowed critical examination of the early phases of learning, when animals learn the ‘rules of the game’ (or the state representation). Behavioral findings point to a process akin to Bayesian inference in which animals attempt to use observed information to infer the unobservable (latent) causal structure of the task, which is then used to craft task states that accurately describe the task dynamics \[[35](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0690), [36](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0695), [37](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0700), [38](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0705)\]. This ‘representation learning’ process has been linked to memory processes \[[39](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0710), [40](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0715)\] as well as neural selective attention mechanisms \[[41](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0720)\]. As is the case here, computational level questions in RL link intimately with the algorithmic level, to which we now turn.

## The algorithmic level: multiple solutions to the decision-making problem

Given the computational goal of maximizing reward, how does a decision-making agent learn which states of the world predict reward, and what actions enable their attainment? RL provides multiple algorithmic solutions to the problem of credit assignment (i.e., correctly assigning credit or laying blame for an outcome on preceding actions or states). Many of these algorithms proceed through the incremental update of state- and action-specific ‘values’ defined as the (discounted) sum of future expected rewards. This update hinges on the calculation of reward prediction errors that compare the predicted value to the current outcome plus expected future value \[[4](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0535)\].

A major focus in recent years has been uncovering the neural substrates of computations of the economic value of goods \[[42](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0725)\]. Here, a major algorithmic question is whether reward is indeed evaluated in terms of common currency that allows maximization over bundles of outcomes. This idea, central to economics and especially to the field of [neuroeconomics](https://www.sciencedirect.com/topics/neuroscience/neuroeconomics "Learn more about neuroeconomics from ScienceDirect's AI-generated Topic Pages"), has found some support \[[43](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0730), [44](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0735), [45](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0740)\]. However, it is not yet clear that common-currency values are at all necessary in order to achieve optimality. Alternative methods for RL that hail from engineering and computer science search instead in the space of behavioral policies and can find the best policy without computing the reward value of different actions \[[46](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0745), [47](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0750), [48](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0755)\]. Indeed, recent evidence suggests that prediction error signals in the brain correspond to value differences between actions, which can supply the appropriate gradient for such ‘policy search’ algorithms \[[49](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0760)\].

In addition to learning values, a ubiquitous aspect of real-world tasks is time: learning *when* a reward will occur is sometimes as important as learning that it will occur. Indeed, at the heart of RL algorithms is the temporal-difference method that compares predictions across consecutive time points in a task. However, one might argue that time has been mistreated in RL, typically simplified and discretized in order to conform to the Markov assumption \[[50](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0765)\]. For example, in ‘tapped delay line’ or ‘serial compound’ representations, the passage of time is modeled using discrete sequential states that each accrue a separate value. This redundancy of values requires additional mechanisms to accelerate learning (e.g., eligibility traces \[[2](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0525)\]), and results in erroneous predictions when outcomes arrive earlier than expected \[[51](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0770)\]. Moreover, discretizing time raises the question of an appropriate resolution, and is hard-pressed to account for well-established phenomena such as scalar timing noise. Recent work attempting to address these issues proposed distributed temporal representations that span multiple durations, thereby allowing multi-timescale learning in an elegant way \[[52](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0775), [53](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0780)\]. Another promising alternative is to model learning using a semi-Markov framework where (continuous) duration is an explicit property of each state, along with value \[[51](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0770), [54](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0785)\]. Here learning when things will happen proceeds in parallel to learning what will happen, allowing the temporal representation to adapt to the properties of the task \[[55](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0790)\], in line with recent work suggesting that neurons in the striatum indeed represent time in a task-relevant, adaptive way \[[56•](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0795), [57](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0800), [58](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0805)\].

More generally, the efficiency and correctness of different RL algorithms depends critically on how states and actions are represented, highlighting again the centrality of (environment-)appropriate representations in trial-and-error learning. For instance, an active area of research seeks to extend RL to address scenarios that have hierarchical structure (e.g., navigating a building or cooking a meal), in which tasks can be subdivided into a series of simpler subtasks (with their associated subgoals) to aid learning and simplify action selection \[[59](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0810), [60](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0815)\]. Many real-world tasks have such structure, and moreover, different tasks often share subcomponents. Thus encapsulation of the policy that achieves a particular subgoal (e.g., finding the elevator) allows easy transfer to other tasks that involve this same subgoal, making the learning of novel tasks more efficient. As a result, algorithmic issues involved in parsing a task to useful subcomponents interact with a computational-level goal of not only solving the current task, but also acquiring a useful ‘toolkit’ of policies that can be composed to solve many other tasks. This brings to the fore questions about how a task should be optimally hierarchically decomposed \[[61](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0820)\], and how to quantify the future benefits of a certain decomposition so they may be weighed against the resulting costs to performance and learning of the current task.

This attempt to divine structure in the learning problem relates more broadly to the necessity of dealing effectively with partially-observable environments where current observations (i.e., perceptual cues) are only probabilistically related to the underlying state that generated them. Optimal RL in partially-observable environments is theoretically possible, although practically intractable \[[62](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0825)\]. The problem is that the non-Markovian observations are inappropriate as inputs to RL algorithms. Instead, one must compute a Bayesian ‘belief state’ over the underlying states, which does have the Markov property, but is high dimensional and continuous. In practice, approximate solutions have been suggested. For instance, recent work marrying the principles of ‘deep’ representations with RL has exceeded human performance in simple Atari games \[[63•](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0830)\]. This work established the robustness and flexibility of relatively naïve RL methods when learning in the space of abstract, generalized representations.

Finally, nodding to the implementational level is the question of which RL algorithm is implemented in the brain, and the inevitable conclusion that several algorithms may be at play at once. Considering the multiplicity of algorithmic solutions that RL offers, each enjoying different strengths and suffering from its own shortcomings, it may indeed be optimal for learning to proceed via parallel, likely interacting, learning and decision making systems \[[64](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0835), [65](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0840)\]. Much recent work has studied the interplay between so-called model-based and model-free modes of RL, capturing and explaining the behavioral consequences of calculating reward predictions using prospection in an internal model of the environment (model-based decision making, also called goal-directed behavior), versus using previously cached values that were learned incrementally through experience (model-free decision making, or habitual behavior) \[[66](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0845), [67](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0850), [68•](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0855)\]. This dual-systems approach is increasingly applied to understanding abnormal behavior as an imbalance in computationally distinct learning systems \[[39](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0710), [69](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0860), [70•](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0865)\]. Similarly inspired by the multiplicity of pathways through the basal ganglia, more mechanistic models of action learning have suggested that action values are a product of parallel, balanced, ‘go’ (excitatory) and ‘no-go’ (inhibitory) action selection systems, with recent instantiations of this framework directly implementing model-free RL \[[71•](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0870), [72](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0875)\]. Such a composite approach to understanding learning processes underlying rich behavior has been attractive in bridging the algorithmic level of RL with its neural implementation, suggesting a mapping from component algorithms to identifiable and distinct neural structures and circuits, as will be discussed below.

## The implementational level: dopamine-dependent learning in the basal ganglia

At the final level of the hierarchy, neuroscientists have had considerable success in mapping functions implied by RL algorithms to neurobiological substrates. Whereas some of the computational and algorithmic questions highlighted above revolved around scaling RL to environments with real-world action and state complexity, the problems at the implementational level arise from the sheer complexity of the neural system, as well as the limitations of different experimental methods.

Much of this work has focused on the basal ganglia, a collection of forebrain nuclei that have long been associated with learning, action selection and decision making. The idea that the basal ganglia implement formal RL algorithms stems from the close correspondence between the responses of midbrain dopamine neurons and the reward prediction-error signal at the heart of RL algorithms \[[10](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0565), [73](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0880)\]. The striatum, the input structure of the basal ganglia and a primary target of the widely broadcast [dopaminergic](https://www.sciencedirect.com/topics/neuroscience/dopaminergic "Learn more about dopaminergic from ScienceDirect's AI-generated Topic Pages") [neuromodulation](https://www.sciencedirect.com/topics/neuroscience/neuromodulation "Learn more about neuromodulation from ScienceDirect's AI-generated Topic Pages"), is a prime candidate for learning values and biasing action selection so as to implement RL policies. Indeed, plasticity in cortico-striatal synapses is modulated by dopamine signaling \[[74](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0885)\], in perfect accord with the effect of reward prediction errors on learning in RL algorithms \[[75](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0890)\].

Despite the seemingly direct correspondence between RL and the function of the basal ganglia, many aspects of this mapping remain open. Primary among these is how are reward prediction errors computed by dopaminergic neurons. The circuit mechanism that compares predictions associated with past and present states (as is necessary for computing temporal-difference prediction errors) is the subject of a number of mechanistic models (e.g., \[[6](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0545), [76](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0895), [77](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0900), [78](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0905)\]). Many models posit that this computation derives from the difference in sign of direct and indirect inputs from the striatum to dopamine neurons, however, it remains unclear whether these implementations have the necessary fidelity to the known anatomy \[[79](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0910)\]. Curiously, few models place the burden of the difference computation on local circuitry in dopaminergic areas \[[80••](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0915), [81](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0920)\].

Alongside this question, the perennial doubt of whether dopamine signals correspond to prediction error signals lingers. Here, the question has evolved from initial skepticism \[[82](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0925), [83](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0930)\] that has mostly been put to rest \[[84](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0935)\], to understanding the heterogeneity of dopaminergic responses to both appetitive and aversive stimuli \[[85](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0940), [86](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0945), [87](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0950), [88](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0955)\]. Recent findings illustrating the complexity of what was once thought to be a scalar signal broadcast widely — a last haven of apparent simplicity in brain signaling — suggest a relatively broad mapping between the algorithmic and implementation levels, preserving the spirit, if not the letter, of RL algorithms. However, some implementations of RL actually require multiple parallel prediction errors (e.g., hierarchical RL \[[89](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0960)\] and successor representation frameworks \[[90](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0965), [91](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0970)\]), suggesting that diversity is perhaps a feature of the system rather than a bug. Still, the relationship between dopamine signals and areas that represent positive prediction errors for aversive stimuli (such as the lateral [habenula](https://www.sciencedirect.com/topics/neuroscience/habenula "Learn more about habenula from ScienceDirect's AI-generated Topic Pages") \[[92](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0975), [93](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0980)\]) is unclear. In addition, [dopamine release](https://www.sciencedirect.com/topics/neuroscience/dopamine-release "Learn more about dopamine release from ScienceDirect's AI-generated Topic Pages") has long been associated with action initiation \[[94](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0985), [95](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0990)\] and energization \[[82](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0925)\], suggesting a functional role for dopamine beyond reward prediction-error signaling. Dopamine aside, much work has focused on the interplay between dual excitatory (so-called ‘go’) and inhibitory (‘no-go’) pathways through the basal ganglia, and whether this architecture can be mapped onto RL action-selection mechanisms \[[71•](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0870), [96](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0995), [97](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib1000)\]. New [optogenetic](https://www.sciencedirect.com/topics/neuroscience/optogenetics "Learn more about optogenetic from ScienceDirect's AI-generated Topic Pages") and imaging techniques in mice now allow the basic tenets of these dual-pathway action-selection models to be directly tested, with sometimes surprising results \[[98](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib1005), [99](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib1010), [100](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib1015)\].

Finally, the almost-exclusive focus of research in the last two decades on implementations of model-free incremental RL in the basal ganglia and in dopaminergic signaling has recently been challenged by demonstrations of model-based signals in the same neural substrates \[[66](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib0845)\]. While these findings may be taken to suggest that the basal ganglia do not implement RL-based learning and action selection, an alternative interpretation is that model-based and model-free RL methods are not as separated in the brain as [lesion studies](https://www.sciencedirect.com/topics/neuroscience/lesion-studies "Learn more about lesion studies from ScienceDirect's AI-generated Topic Pages") first suggested \[[101](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib1020)\]. Perhaps the strong appeal of a simple dichotomic implementation of two different algorithmic solutions has led researchers to overly-simplified interpretations of data. Ultimately, the intricate nature of a neural implementation of RL is likely due to the variety of interrelated goals that this system must fulfill in complex environments (optimizing reward, transferring learning to new situations, scaling to the current context, etc.), as well as to the fact that different brain areas function together and not in isolation.

One cautionary tale is that a simple model, while extremely powerful at understanding the functions of different neural substrates, is at the same time limited and should not be expected to explain all aspects of the signaling in these areas. The bidirectional interaction between models and neural findings suggests iterative refinement of the models to widen their scope to more phenomena. Progressively more complex experimental designs that are specifically tailored to asking algorithmic (or even computational level) questions are invaluable in this effort — simple designs can elucidate basic principles, but the reach of the conclusions that one can draw from these experiments should not be overextended. Indeed, optogenetics and other targeted neural manipulations now allow powerful tests of models of RL at the level of neural implementation \[[102••](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib1025), [103•](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bib1030)\]. However, the ability to transiently perturb neural activity with cell-type selectivity and temporal precision during ongoing behavior demands that precise hypotheses be articulated at the mechanistic level, and behavioral paradigms be sensibly exploited.

## Conclusion — inspiration across levels

Reinforcement learning is perhaps the poster child of Marr's levels of analysis — a computational problem that, expressed formally, leads to a host of algorithmic solutions that seem to be implemented in human and animal brains. However, as with many classification schemes, too much emphasis on delineation of levels can distract from the holistic nature of scientific inquiry. As we have shown, the boundaries between the levels are not clear cut, and cross-disciplinary interaction among researchers from different fields and focusing on different levels has only served to advance the field. By some accounts, the different levels should be used to constrain each other — implementational limitations determining which algorithms are feasible, algorithmic (in)efficiencies affecting which computational problems are solvable, etc. However, we feel that this approach is optimistic at best, and misleading at worst — given the degrees of freedom at each level, hard constraints are difficult to derive, and may lead to unnecessary restrictions on creativity at other levels. Instead, to paraphrase Rich Sutton (personal communication, Barbados 2008), Marr's levels serve scientific inquiry much better when used to inspire one another.

## Conflict of interests

Nothing declared.

## References and recommended reading

Papers of particular interest, published within the period of review, have been highlighted as:

• of special interest

•• of outstanding interest

## Acknowledgements

We are grateful to Gecia Bravo-Hermsdorff, Mingbo Cai, Andra Geana, Nina Rouhani, Nico Schuck and Yeon Soon Shin for valuable comments on this manuscript. This work was funded by the Human Frontier Science Program Organization and by NIMH grant [R01MH098861](https://www.sciencedirect.com/science/article/pii/S2352154616300821#gs1).

## References

[1](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0520)

D. Marr, T. Poggio

**From understanding computation to understanding neural circuitry**

Neurosci Res Program Bull, 15 (1977), pp. 470-488

[2](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0525)

R.S. Sutton, A.G. Barto

**Reinforcement learning: an introduction**

MIT Press (1998)

[3](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0530)

R.S. Sutton

**Learning to predict by the methods of temporal differences**

Mach Learn, 3 (1988), pp. 9-44

[4](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0535)

Y. Niv, G. Schoenbaum

**Dialogues on prediction errors**

Trends Cogn Sci, 12 (2008), pp. 265-272

[5](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0540)

Y. Niv

**Reinforcement learning in the brain**

J Math Psychol, 53 (2009), pp. 139-154

[6](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0545)

J.C. Houk, J.L. Adams, A.G. Barto

**A model of how the basal ganglia generate and use neural signals that predict reinforcement**

J.C. Houk, J.L. Davis, D.G. Beiser (Eds.), Models of information processing in the basal ganglia, MIT Press (1995), pp. 249-270

[7](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0550)

R.C. O’Reilly, M.J. Frank

**Making working memory work: a computational model of learning in the prefrontal cortex and basal ganglia**

Neural Computat, 18 (2006), pp. 283-328

[8](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0555)

P. Redgrave, T.J. Prescott, K. Gurney

**The basal ganglia: a vertebrate solution to the selection problem?**

Neuroscience, 89 (1999), pp. 1009-1023

[9](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0560)

P.R. Montague, P. Dayan, T.J. Sejnowski

**A framework for mesencephalic dopamine systems based on predictive Hebbian learning**

J Neurosci, 16 (1996), pp. 1936-1947

[10](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0565)

W. Schultz, P. Dayan, P.R. Montague

**A neural substrate of prediction and reward**

Science, 275 (1997), pp. 1593-1599

[11](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0570)

A.G. Barto

**Adaptive critics and the basal ganglia**

J.C. Houk, J.L. Davis, D.G. Beiser (Eds.), Models of information processing in the basal ganglia, MIT Press (1995), pp. 215-232

[12](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0575)

M.J. Kang, M. Hsu, I.M. Krajbich, G. Loewenstein, S.M. McClure, J.T. Wang, C.F. Camerer

**The wick in the candle of learning epistemic curiosity activates reward circuitry and enhances memory**

Psychol Sci, 20 (2009), pp. 963-973

[13](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0580)

G. Loewenstein

**The psychology of curiosity: a review and reinterpretation**

Psychol Bull, 116 (1994), p. 75

[14](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0585)

J. Schmidhuber

**A possibility for implementing curiosity and boredom in model-building neural controllers**

From animals to animats: proceedings of the first international conference on simulation of adaptive behavior (1991)

[15](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0590)

P.-Y. Oudeyer, F. Kaplan

**What is intrinsic motivation? A typology of computational approaches**

Front Neurorobot, 1 (2007), p. 6

[16](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0595)

A.G. Barto

**Intrinsic motivation and reinforcement learning**

G. Baldassarre, M. Mirolli (Eds.), Intrinsically motivated learning in natural and artificial systems, Springer (2013), pp. 17-47

[17](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0600)

Ö. Şimşek, A.G. Barto

**An intrinsic reward mechanism for efficient exploration**

Proceedings of the 23rd international conference on Machine learning, ACM (2006), pp. 833-840

[18](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0605)

S. Singh, R.L. Lewis, A.G. Barto

**Where do rewards come from**

Proceedings of the annual conference of the cognitive science society (2009), pp. 2601-2606

[19](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0610)

M. McDevitt, R. Dunn, M. Spetch, E. Ludvig

**When good news leads to bad choices**

J Exp Anal Behav, 105 (2016), pp. 23-40

[20](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0615)

J.M. Pisklak, M.A. McDevitt, R.M. Dunn, M.L. Spetch

**When good pigeons make bad decisions: choice with probabilistic delays and outcomes**

J Exp Anal Behav, 104 (2015), pp. 241-251

[21](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0620)

E.S. Bromberg-Martin, O. Hikosaka

**Midbrain dopamine neurons signal preference for advance information about upcoming rewards**

Neuron, 63 (2009), pp. 119-126

[22](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0625)

E.S. Bromberg-Martin, O. Hikosaka

**Lateral habenula neurons signal errors in the prediction of reward information**

Nature Neurosci, 14 (2011), pp. 1209-1216

[23](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0630)

T.C. Blanchard, B.Y. Hayden, E.S. Bromberg-Martin

**Orbitofrontal cortex uses distinct codes for different choice attributes in decisions motivated by curiosity**

Neuron, 85 (2015), pp. 602-614

[24](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0635)

S. Singh, R.L. Lewis, A.G. Barto, J. Sorg

**Intrinsically motivated reinforcement learning: An evolutionary perspective**

IEEE Trans Autonom Mental Dev, 2 (2010), pp. 70-82

[25](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0640)

X. Guo, S. Singh, R.L. Lewis

**Reward mapping for transfer in long-lived agents**

Adv Neural Inform Process Syst (2013), pp. 2130-2138

[26](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0645)

J. Sorg, S.P. Singh, R.L. Lewis

**Internal rewards mitigate agent boundedness**

Proceedings of the 27th international conference on machine learning (ICML-10) (2010), pp. 1007-1014

[27](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0650)

C. Hull

**Principles of behavior: an introduction to behavior theory**

D. Appleton-Century Company (1943)

[28•](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0655)

M. Keramati, B. Gutkin

**Homeostatic reinforcement learning for integrating reward collection and physiological stability**

eLife, 3 (2014), p. e04811

The authors introduce a new RL theory in which rewards are defined as outcomes that fulfill physiological needs, and use this framework to show how animals learn to perform actions that lead to rewards in order to maintain a stable physiological state. The model can account for a range of phenomena related to food seeking and risk aversion, and suggests a normative understanding of delay discounting as a consequence of optimally minimizing physiological deviations.

[29](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0660)

M. Keramati, B.S. Gutkin

**A reinforcement learning theory for homeostatic regulation**

Advances in neural information processing systems (2011), pp. 82-90

[30](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0665)

I. Nahum-Shani, S.N. Smith, A. Tewari, K. Witkiewitz, L.M. Collins, B. Spring, S. Murphy

**Just in time adaptive interventions (JITAIs): an organizing framework for ongoing health behavior support**

Methodology Center Technical Report No. 14-126 (2014)

[31](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0670)

I. Nahum-Shani, E.B. Hekler, D. Spruijt-Metz

**Building health behavior models to guide the development of just-in-time adaptive interventions: a pragmatic framework**

Health Psychol, 34 (2015), p. 1209

[32](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0675)

G. Konidaris, I. Scheidwasser, A.G. Barto

**Transfer in reinforcement learning via shared features**

J Mach Learn Res, 13 (2012), pp. 1333-1371

[33](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0680)

S.J. Gershman, Y. Niv

**Learning latent structure: carving nature at its joints**

Curr Opin Neurobiol, 20 (2010), pp. 251-256

[34](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0685)

N. Daw

**Trial by trial data analysis using computational models**

Decision making, affect and learning: attention and performance XXIII, Oxford University Press (2011)

[35](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0690)

S.J. Gershman, K.A. Norman, Y. Niv

**Discovering latent causes in reinforcement learning**

Curr Opin Behav Sci, 5 (2015), pp. 43-50

[36](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0695)

S.J. Gershman, D.M. Blei, Y. Niv

**Context, learning, and extinction**

Psychol Rev, 117 (2010), p. 197

[37](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0700)

S.J. Gershman, C.E. Jones, K.A. Norman, M.-H. Monfils, Y. Niv

**Gradual extinction prevents the return of fear: implications for the discovery of state**

Front Behav Neurosci, 7 (2013), p. 164

[38](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0705)

S.J. Gershman, Y. Niv

**Perceptual estimation obeys Occam's razor**

Front Psychol, 4 (2013), p. 623

[39](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0710)

A.G. Collins, J.K. Brown, J.M. Gold, J.A. Waltz, M.J. Frank

**Working memory contributions to reinforcement learning impairments in schizophrenia**

J Neurosci, 34 (2014), pp. 13747-13756

[40](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0715)

S.J. Gershman, A. Radulescu, K.A. Norman, Y. Niv

**Statistical computations underlying the dynamics of memory updating**

PLoS Computat Biol, 10 (2014), p. e1003939

[41](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0720)

Y. Niv, R. Daniel, A. Geana, S.J. Gershman, Y.C. Leong, A. Radulescu, R.C. Wilson

**Reinforcement learning in multidimensional environments relies on attention mechanisms**

J Neurosci, 35 (2015), pp. 8145-8157

[42](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0725)

P.W. Glimcher, E. Fehr

**Neuroeconomics: decision making and the brain**

Academic Press (2013)

[43](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0730)

D.J. Levy, P.W. Glimcher

**The root of all value: a neural common currency for choice**

Curr Opin Neurobiol, 22 (2012), pp. 1027-1038

[44](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0735)

C. Padoa-Schioppa, J.A. Assad

**Neurons in the orbitofrontal cortex encode economic value**

Nature, 441 (2006), pp. 223-226

[45](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0740)

C. Padoa-Schioppa, J.A. Assad

**The representation of economic value in the orbitofrontal cortex is invariant for changes of menu**

Nature Neurosci, 11 (2008), pp. 95-102

[46](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0745)

J. Baxter, P.L. Bartlett

**Infinite-horizon policy-gradient estimation**

J Artif Intell Res (2001), pp. 319-350

[47](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0750)

R.S. Sutton, D.A. McAllester, S.P. Singh, Y. Mansour

**Policy gradient methods for reinforcement learning with function approximation**

Adv Neural Inform Process Syst (1999), pp. 1057-1063

[48](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0755)

S. Bhatnagar, M. Ghavamzadeh, M. Lee, R.S. Sutton

**Incremental natural actor-critic algorithms**

Adv Neural Inform Process Syst (2007), pp. 105-112

[49](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0760)

J. Li, N.D. Daw

**Signals in human striatum are appropriate for policy update rather than value prediction**

J Neurosci, 31 (2011), pp. 5504-5511

[50](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0765)

S.J. Gershman, A.A. Moustafa, E.A. Ludvig

**Time representation in reinforcement learning models of the basal ganglia**

Front Computat Neurosci (2014), p. 7

[51](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0770)

N.D. Daw, A.C. Courville, D.S. Touretzky

**Representation and timing in theories of the dopamine system**

Neural Computat, 18 (2006), pp. 1637-1677

[52](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0775)

E.A. Ludvig, R.S. Sutton, E.J. Kehoe

**Evaluating the TD model of classical conditioning**

Learn Behav, 40 (2012), pp. 305-319

[53](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0780)

F. Rivest, J.F. Kalaska, Y. Bengio

**Alternative time representation in dopamine models**

J Computat Neurosci, 28 (2010), pp. 107-130

[54](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0785)

S.J. Bradtke, M.O. Duff

**Reinforcement learning methods for continuous time Markov decision problems**

Adv Neural Inform Process Syst, 7 (1995), p. 393

[55](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0790)

Y. Takahashi, A.J. Langdon, Y. Niv, G. Schoenbaum

**Temporal specificity of reward prediction errors signaled by putative dopamine neurons in rat VTA depends on ventral striatum**

Neuron (2016)

[56•](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0795)

G.B. Mello, S. Soares, J.J. Paton

**A scalable population code for time in the striatum**

Curr Biol, 25 (2015), pp. 1113-1122

Using a serial fixed interval task, the authors find a population of neurons in the dorsal striatum that adaptively represents time. An adaptive temporal representation such as this is one of the essential components of RL in semi-Markov environments.

[57](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0800)

T.S. Gouvêa, T. Monteiro, A. Motiwala, S. Soares, C. Machens, J.J. Paton

**Striatal dynamics explain duration judgments**

eLife, 4 (2016), p. e11386

[58](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0805)

X. Jin, F. Tecuapetla, R.M. Costa

**Basal ganglia subcircuits distinctively encode the parsing and concatenation of action sequences**

Nature Neurosci, 17 (2014), pp. 423-430

[59](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0810)

M.M. Botvinick, Y. Niv, A.C. Barto

**Hierarchically organized behavior and its neural foundations: a reinforcement learning perspective**

Cognition, 113 (2009), pp. 262-280

[60](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0815)

M.M. Botvinick

**Hierarchical reinforcement learning and decision making**

Curr Opin Neurobiol, 22 (2012), pp. 956-962

[61](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0820)

A. Solway, C. Diuk, N. Córdova, D. Yee, A.G. Barto, Y. Niv, M.M. Botvinick

**Optimal behavioral hierarchy**

PLoS Computat Biol, 10 (2014)

[62](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0825)

L.P. Kaelbling, M.L. Littman, A.R. Cassandra

**Planning and acting in partially observable stochastic domains**

Artif Intell, 101 (1998), pp. 99-134

[63•](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0830)

V. Mnih, K. Kavukcuoglu, D. Silver, A.A. Rusu, J. Veness, M.G. Bellemare, A. Graves, M. Riedmiller, A.K. Fidjeland, G. Ostrovski

**Human-level control through deep reinforcement learning**

Nature, 518 (2015), pp. 529-533

The authors marry a deep convolutional artifical neural network with the Q-learning algorithm from RL to produce an agent (called the deep Q-network; DQN) that learns to play a range of Atari games at human level or beyond. With only the game pixel display and the score as input, the DQN agent is able to learn a generalized, high-dimensional action-value representation of the display to support flexible game-playing behavior.

[64](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0835)

N.D. Daw, Y. Niv, P. Dayan

**Uncertainty-based competition between prefrontal and dorsolateral striatal systems for behavioral control**

Nature Neurosci, 8 (2005), pp. 1704-1711

[65](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0840)

M. Keramati, A. Dezfouli, P. Piray

**Speed/accuracy trade-off between the habitual and the goal-directed processes**

PLoS Computat Biol, 7 (2011)

[66](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0845)

N.D. Daw, S.J. Gershman, B. Seymour, P. Dayan, R.J. Dolan

**Model-based influences on humans’ choices and striatal prediction errors**

Neuron, 69 (2011), pp. 1204-1215

[67](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0850)

A.R. Otto, S.J. Gershman, A.B. Markman, N.D. Daw

**The curse of planning dissecting multiple reinforcement-learning systems by taxing the central executive**

Psychol Sci, 24 (2013), pp. 751-761

[68•](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0855)

B.B. Doll, K.D. Duncan, D.A. Simon, D. Shohamy, N.D. Daw

**Model-based choices involve prospective neural activity**

Nature Neurosci, 18 (2015), pp. 767-772

Behavioral work has suggested that planning in model-based RL involves prospection at decision time. Neural findings of hippocampal preplay offer a neural substrate for this, but have not been connected to choices. Here Doll *et al*. use a clever task in humans undergoing fMRI to show that the extent to which participants behave according to model-based RL is correlated with the decodability of prospective representations in their brain, and conversely, prediction error signals can be detected in participants’ striatum to the degree that they are using model-free RL.

[69](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0860)

V. Voon, K. Derbyshire, C. Rück, M. Irvine, Y. Worbe, J. Enander, L. Schreiber, C. Gillan, N. Fineberg, B. Sahakian

**Disorders of compulsivity: a common bias towards learning habits**

Mol Psychiatry, 20 (2015), pp. 345-352

[70•](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0865)

C. Gillan, R.W. Kosinski, E.A. Phelps, N.D. Daw

**Characterizing a psychological dimension related to deficits in goal-directed control**

eLife, 5 (2016), p. e11305

Using a large sample of thousands of healthy participants on Amazon's Mechanical Turk, the authors identify compulsivity, anxious depression and social withdrawal as factors that cut across symptoms of different mental disorders. They then use a sequential choice task to quantify the relative contribution of model-based versus model-free RL to each participant's decisions, and show that reduced model-based control is specifically related to increased compulsivity.

[71•](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0870)

A.G. Collins, M.J. Frank

**Opponent actor learning (OpAL): modeling interactive effects of striatal dopamine on reinforcement learning and choice incentive**

Psychol Rev, 121 (2014), p. 337

The authors present an expanded actor-critic RL algorithm that incorporates symmetric and balanced positive and negative action-value learning to reflect the parallel ‘go’ and ‘no-go’ pathways found in the basal ganglia. This model accounts for seemingly incompatible effects of dopamine on learning and on motivation. The authors go on to show that such an apparently redundant action-representation mechanism might be normative, as it allows the agent to learn equally well in ‘rich’ as in ‘lean’ environments.

[72](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0875)

J. Cockburn, A.G. Collins, M.J. Frank

**A reinforcement learning mechanism responsible for the valuation of free choice**

Neuron, 83 (2014), pp. 551-557

[73](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0880)

M.R. Roesch, D.J. Calu, G. Schoenbaum

**Dopamine neurons encode the better option in rats deciding between differently delayed or sized rewards**

Nature Neurosci, 10 (2007), pp. 1615-1624

[74](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0885)

J.N. Reynolds, B.I. Hyland, J.R. Wickens

**A cellular mechanism of reward-related learning**

Nature, 413 (2001), pp. 67-70

[75](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0890)

J.N. Reynolds, J.R. Wickens

**Dopamine-dependent plasticity of corticostriatal synapses**

Neural Netw, 15 (2002), pp. 507-521

[76](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0895)

K. Morita, M. Morishima, K. Sakai, Y. Kawaguchi

**Reinforcement learning: computing the temporal difference of values via distinct corticostriatal pathways**

Trends Neurosci, 35 (2012), pp. 457-467

[77](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0900)

W. Potjans, M. Diesmann, A. Morrison

**An imperfect dopaminergic error signal can drive temporal-difference learning**

PLoS Computat Biol, 7 (2011)

[78](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0905)

W. Potjans, A. Morrison, M. Diesmann

**A spiking neural network model of an actor-critic learning agent**

Neural Computat, 21 (2009), pp. 301-339

[79](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0910)

D. Joel, Y. Niv, E. Ruppin

**Actor–critic models of the basal ganglia: new anatomical and computational perspectives**

Neural Netw, 15 (2002), pp. 535-547

[80••](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0915)

N. Eshel, M. Bukwich, V. Rao, V. Hemmelder, J. Tian, N. Uchida

**Arithmetic and local circuitry underlying dopamine prediction errors**

Nature, 525 (2015), pp. 243-246

Using optogenetics and extracellular recordings, the authors demonstrate that dopamine neurons in the ventral tegmental area (VTA) perform subtraction, and that this operation depends critically on the activity of inhibitory interneurons within the VTA. This is the first demonstration in this circuit of this arithmetic operation, central to the computation of reward prediction errors in RL.

[81](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0920)

R.P. Rao, T.J. Sejnowski

**Spike-timing-dependent Hebbian plasticity as temporal difference learning**

Neural Computat, 13 (2001), pp. 2221-2237

[82](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0925)

K.C. Berridge

**The debate over dopamine's role in reward: the case for incentive salience**

Psychopharmacology, 191 (2007), pp. 391-431

[83](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0930)

P. Redgrave, T.J. Prescott, K. Gurney

**Is the short-latency dopamine response too short to signal reward error?**

Trends Neurosci, 22 (1999), pp. 146-151

[84](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0935)

J.M. Schulz, P. Redgrave, C. Mehring, A. Aertsen, K.M. Clements, J.R. Wickens, J.N. Reynolds

**Short-latency activation of striatal spiny neurons via subcortical visual pathways**

J Neurosci, 29 (2009), pp. 6336-6347

[85](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0940)

J.Y. Cohen, S. Haesler, L. Vong, B.B. Lowell, N. Uchida

**Neuron-type-specific signals for reward and punishment in the ventral tegmental area**

Nature, 482 (2012), pp. 85-88

[86](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0945)

P. Henny, M.T. Brown, A. Northrop, M. Faunes, M.A. Ungless, P.J. Magill, J.P. Bolam

**Structural correlates of heterogeneous in vivo activity of midbrain dopaminergic neurons**

Nature Neurosci, 15 (2012), pp. 613-619

[87](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0950)

F. Brischoux, S. Chakraborty, D.I. Brierley, M.A. Ungless

**Phasic excitation of dopamine neurons in ventral VTA by noxious stimuli**

Proc Natl Acad Sci U S A, 106 (2009), pp. 4894-4899

[88](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0955)

M. Joshua, A. Adler, R. Mitelman, E. Vaadia, H. Bergman

**Midbrain dopaminergic neurons and striatal cholinergic interneurons encode the difference between reward and aversive events at different epochs of probabilistic classical conditioning trials**

J Neurosci, 28 (2008), pp. 11673-11684

[89](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0960)

C. Diuk, K. Tsai, J. Wallis, M. Botvinick, Y. Niv

**Hierarchical learning induces two simultaneous, but separable, prediction errors in human basal ganglia**

J Neurosci, 33 (2013), pp. 5797-5805

[90](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0965)

S.J. Gershman, C.D. Moore, M.T. Todd, K.A. Norman, P.B. Sederberg

**The successor representation and temporal context**

Neural Computat, 24 (2012), pp. 1553-1568

[91](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0970)

P. Dayan

**Improving generalization for temporal difference learning: the successor representation**

Neural Computat, 5 (1993), pp. 613-624

[92](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0975)

M. Matsumoto, O. Hikosaka

**Lateral habenula as a source of negative reward signals in dopamine neurons**

Nature, 447 (2007), pp. 1111-1115

[93](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0980)

M. Matsumoto, O. Hikosaka

**Representation of negative motivational value in the primate lateral habenula**

Nature Neurosci, 12 (2009), pp. 77-84

[94](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0985)

E.C. Syed, L.L. Grima, P.J. Magill, R. Bogacz, P. Brown, M.E. Walton

**Action initiation shapes mesolimbic dopamine encoding of future rewards**

Nature Neurosci, 19 (2016), pp. 34-36

[95](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0990)

P.E. Phillips, G.D. Stuber, M.L. Heien, R.M. Wightman, R.M. Carelli

**Subsecond dopamine release promotes cocaine seeking**

Nature, 422 (2003), pp. 614-618

[96](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib0995)

M.J. Frank, L.C. Seeberger, R.C. O’Reilly

**By carrot or by stick: cognitive reinforcement learning in parkinsonism**

Science, 306 (2004), pp. 1940-1943

[97](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib1000)

S.M. Cox, M.J. Frank, K. Larcher, L.K. Fellows, C.A. Clark, M. Leyton, A. Dagher

**Striatal D1 and D2 signaling differentially predict learning from positive and negative outcomes**

Neuroimage, 109 (2015), pp. 95-101

[98](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib1005)

L.-H. Tai, A.M. Lee, N. Benavidez, A. Bonci, L. Wilbrecht

**Transient stimulation of distinct subpopulations of striatal neurons mimics changes in action value**

Nature Neurosci, 15 (2012), pp. 1281-1289

[99](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib1010)

G. Cui, S.B. Jun, X. Jin, M.D. Pham, S.S. Vogel, D.M. Lovinger, R.M. Costa

**Concurrent activation of striatal direct and indirect pathways during action initiation**

Nature, 494 (2013), pp. 238-242

[100](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib1015)

P. Calabresi, B. Picconi, A. Tozzi, V. Ghiglieri, M. Di Filippo

**Direct and indirect pathways of basal ganglia: a critical reappraisal**

Nature Neurosci, 17 (2014), pp. 1022-1030

[101](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib1020)

B.W. Balleine

**Neural bases of food-seeking: affect, arousal and reward in corticostriatolimbic circuits**

Physiol Behav, 86 (2005), pp. 717-730

[102••](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib1025)

E.E. Steinberg, R. Keiflin, J.R. Boivin, I.B. Witten, K. Deisseroth, P.H. Janak

**A causal link between prediction errors, dopamine neurons and learning**

Nature Neurosci, 16 (2013), pp. 966-973

The authors use the behavioral paradigm of blocking together with optogenetic manipulation of dopamine neurons to show that dopamine activity is sufficient to generate learning, as predicted by RL theories.

[103•](https://www.sciencedirect.com/science/article/pii/S2352154616300821#bbib1030)

C.Y. Chang, G.R. Esber, Y. Marrero-Garcia, H.-J. Yau, A. Bonci, G. Schoenbaum

**Brief optogenetic inhibition of dopamine neurons mimics endogenous negative reward prediction errors**

Nature Neurosci, 19 (2016), pp. 111-116

The authors use optogenetics to briefly suppress firing activity of dopamine neurons and show that this manipulation alters learning in a Pavlovian overexpectation task, consistent with the effect of a negative prediction error in RL.

## Cited by (26)

© 2016 Elsevier Ltd. All rights reserved.
