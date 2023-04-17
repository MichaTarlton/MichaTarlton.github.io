---
aliases: SBFA
type: project
project: SBF-automata
status: active
priority: p1
creationtag: 2022-11-25 12:16
infotags: [automata, sbf]
---

Descendant of [[Survey Paper]] Project
Descendant of [[Recreating SBF Model]] Project
Remade out of [[Ooman Collab]]
- merge with this one and discontinue it
Making a pseudo code Document [[Pseudocode for SBF Automata]]
Writing up the experiment design in [[SBF - Automata - Design 1]]
Making new log for this project [[SBFA Development Log]]
For development knowledge: [[SBFA Experiment Development]]


```dataview
table rows.file.link AS "Related",
dateformat(rows.file.ctime,"yyyy . MM . dd") as "Created",
dateformat(rows.file.mtime,"yyyy . MM . dd") as "Modified",
rows.infotags as "Tags"
FROM ""
WHERE contains(project,"SBF-automata")
OR contains(project,"sbf-automata")
GROUP BY type
SORT file.ctime desc 
```
# To-Do
- [x] Figure out the sort issue with the oscillator list ✅ 2023-02-06
	- 
- [ ] Make a more stochastic reward version
- [ ] What if there are two reward periods (at the same time)
- [ ] Make changes to figures prescribed by Anis
	- [ ] ![[Supe Meeting with Anis - 06.03.23#Anis’ comments]]
- See Onyx notes relating to it as it may be easier to draw out
- Need to write up what it is
- See if previous literature on this exists (see below)

# Notes
- Might need to divide out the development of the two models, WMA and Normalized automata
- 

# Log
## [[SBFA Development Log]]

# Development
**[[SBFA Experiment Development]]**

### Abstract
[[SBF - Automata - Design 1]]
[[SBF - Automata Algorithm Formalized]]
[[Pseudocode for SBF Automata]]


### Code
## [[First python implementation - conditions and results]]
- See [[Pseudocode for SBF Automata]] for a rough outline of the programmatic algorithm.
- The code has been implemented in a google colab notebook which can be viewed here: [SBF Temp Automata.ipynb - Colaboratory](https://colab.research.google.com/drive/1mC19lGwOrCA8cdEzlYdsuVc5lNUt6z8L?usp=sharing)

### Results


# Related Literature
Break into dedicated
- From the literature search to see if this has been done before

### Keywords I’m finding #tp
- Dynamic [[Multi-Armed Bandit Problem|MAB]]
- 



## Besbes, Gur, Zeevi (????) - Stochastic Multi-Armed-Bandit Problem with Non-stationary Rewards
[Stochastic Multi-Armed-Bandit Problem with Non-stationary Rewards](https://proceedings.neurips.cc/paper/2014/hash/903ce9225fca3e988c2af215d4e544d3-Abstract.html)[https://proceedings.neurips.cc/paper/2014/file/903ce9225fca3e988c2af215d4e544d3-Paper.pdf](https://proceedings.neurips.cc/paper/2014/file/903ce9225fca3e988c2af215d4e544d3-Paper.pdf)

Appears to deal with not only, multiple choice (arms pull options), multiple  time periods

I definitely need help dissecting this one


> The objective is to maximize the expected sum of (possibly discounted) rewards received over a given (possibly infinite) time horizon.

![[image-20221125164302767.png]]

- ok so it does have oscillatory rewards
## Bandits with Temporal Stochastic Constraints
[[1811.09026] Bandits with Temporal Stochastic Constraints](https://arxiv.org/abs/1811.09026)
> [!Abstract] Abstract
> We study the effect of impairment on stochastic multi-armed bandits and develop new ways to mitigate it.
> 
>  [[Impairment effect]] is the phenomena where an agent only accrues reward for an action if they have played it at least a few times in the recent past. 
>  
>  It is practically motivated by repetition and recency effects in domains such as advertising (here consumer behavior may require repeat actions by advertisers) and vocational training (here actions are complex skills that can only be mastered with repetition to get a payoff). Impairment can be naturally modelled as a temporal constraint on the strategy space, and we provide two novel algorithms that achieve sublinear regret, each working with different assumptions on the impairment effect. We introduce a new notion called bucketing in our algorithm design, and show how it can effectively address impairment as well as a broader class of temporal constraints. Our regret bounds explicitly capture the cost of impairment and show that it scales (sub-)linearly with the degree of impairment. Our work complements recent work on modeling delays and corruptions, and we provide experimental evidence supporting our claims.

## Dynamic Bandits with an Auto-Regressive Temporal Structure
[[2210.16386] Dynamic Bandits with an Auto-Regressive Temporal Structure](https://arxiv.org/abs/2210.16386)
> [!Abstract] Abstract
> Multi-armed bandit (MAB) problems are mainly studied under two extreme settings known as stochastic and adversarial. These two settings, however, do not capture realistic environments such as search engines and marketing and advertising, in which rewards stochastically change in time. Motivated by that, we introduce and study a dynamic MAB problem with stochastic temporal structure, where the expected reward of each arm is governed by an auto-regressive (AR) model. Due to the dynamic nature of the rewards, simple "explore and commit" policies fail, as all arms have to be explored continuously over time. We formalize this by characterizing a per-round regret lower bound, where the regret is measured against a strong (dynamic) benchmark. We then present an algorithm whose per-round regret almost matches our regret lower bound. Our algorithm relies on two mechanisms: (i) alternating between recently pulled arms and unpulled arms with potential, and (ii) restarting. These mechanisms enable the algorithm to dynamically adapt to changes and discard irrelevant past information at a suitable rate. In numerical studies, we further demonstrate the strength of our algorithm under different types of non-stationary settings.