---
 tags: reading
 status: open
 title: "A Distributional Code for Value in Dopamine-Based Reinforcement Learning"
 citekey: undefined
 infotags: video, lecture, deepmind, TD, temporal difference, learning
 people: Will Dabney  
 creationtag: 2022-05-05 14:08
 date: 26.08.2020
---
[JNS Lecture: Will Dabney. "A Distributional Code for Value in Dopamine-Based Reinforcement Learning" - YouTube](https://www.youtube.com/watch?v=_Z9R-uwU2Yc)

## Temporal Difference Learning
![[Pasted image 20220505111715.png]]

![[Pasted image 20220505111827.png]]

Pushes an *expected value* towards the middle of the reward distribution.


![[Pasted image 20220505112228.png]]
Using the sign function for the reward drives the  ER towards the median of distribution

![[Pasted image 20220505112537.png]]

   You can set this to any adjust ment to predict whichever quartile of the reward distribution you want

![[Pasted image 20220505112632.png]]

**Quantile Regression** #topics 
A type of asymetric regression
> you can decide to learn any quantile of the distribution of rewards specifically you learn the quantile
> if you can learn any part of the distribution any quantile of the distribution then why not just learn all of them in parallel and within a single agent so instead of making a single value prediction you make a whole spectrum of value predictions

Using $s_i^{+-}$  to denote the quantile

> here we'll denote them v sub i and each v sub i will be paired or will correspond to a different s plus and s minus which we can now denote as an s i plus and an s i minus which will cause it to be tuned to find a different quantile of the reward distribution just using td learning now you'll end up learning the whole distribution over rewards not just the mean or the variance but you can actually capture modes and the overall shape of the distribution

![[Pasted image 20220505113735.png]]

  ***Encoding of the distribution!***

> one more important thing if instead of step functions you have prediction errors that are linear in r minus v or let's say piecewise linear where the positive and negative domains are scaled asymmetrically so it's linear and positive and linear and negative but their slopes can be different you're not learning the quantiles anymore you'll end up learning something called the expectiles 
> 
> you can think of them as being like quantiles are to the median expectations are to the mean .
> Estimatord also encode the distributions
Refs:
[[@rowlandStatisticsSamplesDistributional2019]]
Bellemare 2017 - Distributional Perspective on RL
Dabney 2018 - Distributional RL with Quantile Regression [[@dabneyDistributionalReinforcementLearning2017]] 

## Distributional TD Learning
> we know from previous work already that there is heterogeneity in the responses of dopaminergic neurons the distributional td model proposes an explanation it proposes that unlike in td these cells are actually reporting asymmetric rpe and doing so against different value predictions
> ![[Pasted image 20220505115608.png]]
> it says that the different asymmetric scaling functions directly give rise to these different value baselines and that together they result in a distributional code of value

Mean value agents v. Distributional Value agents
- That is what is being discussed here
- Where as traditionally they were using mean as some encoding of the distribution, instead we are capturing a more unique and accurate encoding of the dist using this quantile method

## Distributional TD model
Is it an accurate representation of the brain, testing this model in animals
What is zero-crossing referring to here?
Crossing the mean RPE?

So each line is a cell, and we can see how optimistic cells (towards the top) over report an extremely negative reward, but for the most part are very reportive for a majority of the positive rewards. Ironically, also under reporting a very high reward as well.

Likewise, we see this flipped in the pessimistic cells for reporting on negative rewards.

I would like to see this with a slightly higher resolution of cell distributions towards pess/optimistic. Rn I’m guessing it’s mostly binned, but not sure how they “sorted” them. The fitted curve seems too neat while the datapoints indicate a ‘Z’ shape as opposed to a ‘S’ shape.
Oh lol nvm these are **SIMULATED**. See real below

> could the brain be doing something similar to distributional td learning the distributional td model makes some specific predictions and they differ from those of the classic td model specifically these will show up in in how they explain individual cell reactions not so much in the overall aggregate of the entire population
> 
> the most obvious prediction to start with is that there should be multiple distinct value representations occurring at the same time both optimistic pessimistic and neutral simultaneously 
> ![[Pasted image 20220505120852.png]]
> 
> ![[Pasted image 20220505120918.png]]
>
> ![[Pasted image 20220505122152.png]]
 
Actual cells are more diverse in their RPE
>  ![[Pasted image 20220505122530.png]]


**Took a lunch break and sorta fell off around 20 minute mark.** Pick back up there if you are too lost.

Need to find the actual definitioni of **zero-crossing**
**Zero-crossing**, probably just means how far the stimulus was from the mean RPE
See below figure where they measure zero-crossing in fluid amounts (i.e. the amount of reward given to the mice)

> ![[Pasted image 20220505142814.png]]

> ![[Pasted image 20220505143138.png]]
 and what jumps out is that the red optimistic cells are the same exact ones that amplify their positive rpes here we see that correlation viscerally

## Comments
Ok so I don’t really see what they did with decoding of these distribution value, but I am curious about it. perhaps revisit the end of the video another time