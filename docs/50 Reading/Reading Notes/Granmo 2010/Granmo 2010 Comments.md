# Personal Summary

H-TRAA:
So essentially you coose from one of two conditions based on how likely some option or subset of options contained in those conditions are likely to give a discrete reward. Only update the odds of one over the other if reward is given (thoug they mix this up in sections 3 and 4 with penalty-reward, inaction-penalty being effective) and do so with some resolution N for the probability (N seems to be tied to knapsack capacity).

Do this repeatedly in a series of binar choices, subdividing the sets into two subsets at ach layerin the hierarchy until reachingthe atomic choices available. From the probability alloted to the atomic options, submitthese to the EDF scheduler which will select the options accordingly. (I can’t seem to figure out “how” the EDF selects though.)

The selections made then return some probablistic chance of a reward, which is then fed back to the root node of the hierarchy.

---
What if the environment returns higher reward (or reward probability) with certain selection amounts? They show this convergesthough so….


What would a non-binary version ofthis look like?
Like you would need some way of deciding at the atomic level
Maybe you could do something that always discard the lowest option up top and then makes subsequent sets smaller?
I could see that getting stuck preety easily though



The important take away we are getting from these automatons is the ability to incrementatlly select  and rank selection scores with [[Ergodicity]], which I assume means the system at least tries to sample all options. The incrmental part means it will slowly bias towards an attractor PDist,and because it is very lightly limited it is easy to redefeine this bias (they go on to confirm this and illustrate it in section 4.5 and fig 10 ) either in it’s search of the probability space or in response to changes in the environment (Iassumeon the last part).

So this begs the question, is there another functionwhich could be added toadjust the rate at which it increments towards a bias? And whatwould that optimally be? Like , this is quite linear in how quickly it approaches a solution. However, too quick a change and you may fail to properly sample all optionsor become stuckin some local attractor bias.

Perhaps as long asthe bias score is logarthmic, then itmay be easy to keep it even-ish? But you may even have some “bipolar” behavior where it quickly swings between options.

