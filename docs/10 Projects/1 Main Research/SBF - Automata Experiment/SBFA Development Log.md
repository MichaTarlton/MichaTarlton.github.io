
---
type: [log, development]
status: active
priority: p1
project: SBF-automata
creationtag: 2022-12-12 11:53
infotags: [SBF, dev]
people:
date:
---

# [[04.04.23]]
## I’m not convinced the weights are accurately tuned
- So I have done several things to see what happens when the RP changes
- First, changed the experiment to run twice as long and for the RP to change halfway through
- Initial attempt changed the RP to the next one in the array of RPs
	- This appeared to have little to no effect on oscillator weights, shockingly
	- So I set up an experiment where no  reward will be issued
- Set the RP to change to RP=999999999 after the halfway timestep (t=10000)
	- In order to no longer deliver reward
	- This didn’t seem to have the intended effect so 
	- So I increased the beta value (learning punishment parameter) in the next
- I set $\beta = \alpha*0.5$
	- This leads to more chaotic weight distribution
	- No apparent changes though
- I now set the time step to be super long $T_{end} = 50000$ to see what the long term behavior is
	- THis didn’t have enough of an impact
- I realized I should scale the end time to the RP size, so I have produced a version of my code to do that as well
- I am going through and changing the figures, Wosc_T_lineplot, Rrp_T_lineplot, and smoothed raster



# [[03.04.23]]
## Working on python modules with top script
Almost there
See changes and proposal for multiple environments

### See new [[Pseudocode for Modular Arrangement]]
- Going to come back to this as the current arrangement does not abstract nicely
- Might need to build entirely from scratch

### Made some progress with figure starting on the basic line plot
see "modules/fig/lineplot/04-1_W-T_osc_lineplot_deconstruct.py" for template to apply to the rest of plots.
I’m a little done for the day.

### Perhaps make a figstats with the save config 
and iterate from there instead of having the stats rerun every damn time


# [[24.03.23]]
## Kill something

## Fixing the module doesn’t load the library
It’s easy, just [PASTE IMPORT LIBRARY AS BLABBALAH AIN EVERY FUCKING
MODULE](https://stackoverflow.com/questions/28445373/python-import-numpy-as-np-from-outer-code-gets-lost-within-my-own-user-defined) Holy shit how are you a real programming language


### See also adding an `__init__.py`
https://www.reddit.com/r/Python/comments/1bbbwk/whats_your_opinion_on_what_to_include_in_init_py/





# [[23.03.23]]
## Refactor Code
- Make a set of environment modules
- Make set of Algo modules
- Make results and figures modules



# [[17.03.23]]
## Figures
- Made a defacto ridgeline figure for showing pull distributions
- One for multiple RPs
- One for multiple trials and one RP
- Had to use a ``gaussian_filter1d``  with sigma=100 in order to get it to work
	- Which also add another library, scipy
- This is actually a line plot with a smoothed kernel over the timestep
- A regular histogram or dist plot simply does not work here as take sums of certain bins and not binned sums of values on timesteps






# [[14.03.23]]
Trying to make the NA with cost.
However my original idea wasn’t really working.
Weights explode around t = 1500
So experimenting with some methods

### Holy shit I may have actually made one that works
```python
if:
 l2_weights[active_nodes] += sum(l2_weights[inactive_nodes]*i_alpha) / sum(active_nodes)
 l2_weights[inactive_nodes] *= (1 - i_alpha)
else:
 l2_weights[inactive_nodes] += sum(l2_weights[active_nodes]*i_alpha) / sum(inactive_nodes)
 l2_weights[active_nodes] *= (1 - i_alpha)
 ```
And it actually does pretty decently compared to my other methods
Also doesn’t blow up like original method
Also seemingly less pulling? More distributed?
Pulls less than the WMV
New: 3666 Pulls, rewards: 3, ratio: .82
Old: 6495 pulls, rewards: 6
WMV: 6120 pulls, rewards: 6, ratio: .98

Saved some comparisons in my desktop results folder

## [[SBFA Results with Gustavo - 14.03.23]]
![[SBFA Results with Gustavo - 14.03.23#Take aways]]

# Experiment [[06.03.23]]  
Currently working with the Normalized Automata version.



## Comments
- Am I tracking reward?

## Initial Conditions
Shared initial conditions for both variants in order to compare.
- $T = 5,000$
- $RP = [ 50, 57, 64, 71, 78, 85, 92, 99, 106, 113, 120]$
- $Oscillators \ Phases \ (n) = [23, 29, 31, 37, 41, 43, 47, 53, 59, 61, 67, 71, 73, 79, 83, 89, 97]$
- $Trials = 10$
- $Initial \ weights \ (w_i) = \frac{1}{N}$
- $Learning \  Control \ \alpha = 0.5$

## Outline

## Statement
In this experiment I am using the SBF Normalized Automata algorithm as speced by anis. See the outline here: [[SBFA - Normalized Automata Vote]].



## Results







# [[06.03.23]] #dev


## Comparing local git with colab
- Pretty sure colab is out of date 
- I think the files are majority the same but with things moved around
- Moved the colab copies to archive

### To use github version in colab
**In colab open from github, make edits, and when done save to github. It should all work.**


### Works with the remote box



## Ok further direction
- The jupyter lab will have access to the files from where you start it in bash
- So you will want to activate the venv from the home directory `source ~/pyvenv/sbfa/bin/activate` 
- Then you can load it as normally
- I’m making a project folder to actually house the main files and tracking with git



## More bullshit with a lost kernel
- Trying to update pip
- Deleted the venv
- check to see if the venv is still in some register with ```lsvirtualenv```
- Recreated the venv from scratch with
```python
python venv -m sbfa --system-site-packages
``````
to “overinstall” the same system packages

### venv in one folder, project files in another
GOing to make a projects directiory in my home
and then connect the venv kernel to jplab

does jupyter already do this?

https://janakiev.com/blog/jupyter-virtual-envs/

I connected jupyterlab to thevenv with ```python -m ipykernel install --user --name=sbfa```
I think this just allows the option to have a dedicated venv for the stuff. Not much more. I really could have just done it in the main python env.

## Also made a github repo
https://github.com/MichaTarlton/SBFA-experiment
on my local machine at: `C:\Users\michaelt\git\SBFA-experiment` 
and on the remote at: `~/pyvenv/sbfa/ tbd `



### [[03.03.23]]
## Catching backup with dev
Made: [[SBFA Experiment Development]]

What notebooks are current, what are they doing?




# [[12.02.23]]
## [[First python implementation - conditions and results]]
- Adding another experiment today
- I previously experimented with multiple RPs
- the last ones I only ran 10 RPs
- Trends are more obvious on the scatter chart with more RPs
	- Pull density for reward phase chart
- I know so because I did this previously, but didn’t save the results

# [[10.02.23]]
## [[SBFA - Normalized Automata Vote]]
- breaking out into it’s own thing
- Need to dictated as separate from weighted Majority Vote algo

## [[Supervision - 10.02.23]]

## Lol did I add the results from last time?
fml
[[SBFA Experiment Results 10.02.23]]

## Anis re-explained his normalized automata
Before I forget
### For active
$w_{i} = w_{i} + \alpha (1 - w_{i} / n_{active})$
### For inactive
$w_{i} = w_{i} + (1 - \alpha )$

Suggest $\alpha = 0.5$




# [[08.02.23]]
Going to write up the Algorithm for the Normalized Automata


# [[07.02.23]]
## Making my own variant on Normalized Automata
Taking the weight off of the non active weights and adding that to the active
Likewise updates the inactive by reducing their weight by

Ok tweaked and bugfixed and I think I got it
btw `//` is not division use`/`

Maybe print list of t where pulls occurred, however this would be prohibitive in higher pull densities
Maybe tie it to the t where the highest weighted agent was involved


# [[05.02.23]]
## Ok fixed everything and then added more plots
- Need to add them

## Making Anis’ Normalized Automata 
Ok I think based on book notes he wants us to:

At update steps:
For active: $w_i$
Actually it may only be penalization, but I think that would not be the intended goal.

fuck I can’t get it to plot for whatever reason

---
Ok fixed it somehow
The logic array has to match when running the update.
so use`*= weight[logic]` instead of just `weight`


# [[03.02.23]]
## Ok here we go Results

### Metahistory weights for a particular RP
![[image-20230203185420559.png]]


### Pull History for multiple epochs on a single reward phase (RP = 59)
![[image-20230203185840805.png]]



### Mean pull history (over epochs) for all RPs
![[image-20230203185402325.png]]



## Code idea
- Maybe add a qualifier for oscs that are above the starting weight
	- To clean up figures
- Time to solution will also require tts / rp
## Speaking to Tom and Trym
- Basically I could use concat, as long as I create a new axis each time(?)  
- but the “correct” way is to create the main array, and then index the values into there
	- I thought of this but was scared about my ignorance of indexing
- 

## Code suggestions
### Martin
> So this is what I have. 
> I do a 5-fold CV and store a Shap explainer type object, which has a .values Anyways, these are stored in a list.
> But, what I do is:
> 
```` python
shap_val = np.array(results['shap_values'][0].values)
  
for i in range(4):
	shap_val = np.concatenate((shap_val, np.array(results['shap_values']
	
[i].values)), axis = 0)
```` 
> Im iteratively concatenating two numpy arrays, so the 'shap_val' array's size changes with each iteration on the axis that I'm concatenating on. 
> 
> It should be possible. The docs for concatenate says "The arrays must have the same shape, except in the dimension corresponding to _axis_ (the first, by default).". 
> 
> If you have the arrays on a list already, you can list them all at once also.
- what is `shap`
- Looks like I may just be using concat wrong

### Monte






# [[30.01.23]]


## AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA
Python doesn’t support concatenation. Not real concat

## Continuing on the WMA
- So last night I basically was able to make the requested raster plot but it’s kinda useless imo
- [ ] Need to make something where I can judge the time it takes to converge on solution



# [[29.01.23]]
## Inititial testing of multiple RPs
So the below figure isn’t entirely useful. It is the average of weights across 5 different reward phase trials. So it is not particularly usefulas it is an average of those weights, weights taken from trials where the RP was different.

![[image-20230129223659104.png|400]]

---

Made a better version with the trial of pultiple RPs. This is the history of the pulls.
![[image-20230129231756888.png|400]]



---


# [[27.01.23]]
## Fixed the issue with the plot
`for i,o in enumerate(osc_sort[0:10]):`
Was returning not the index of the oscillator in the oscillator array order, but the index of the oscillator in the sorted array. Thus `ì = [0,1,2....]` instead of the correct `i = [20 0 1 2 3 4 5 6 7 8 11 9 10 12 13 14 15 16 17 18 23 19 21 22 24]`

Fixed by creating new array `osc_order = np.argsort(mhm[-1,:])[::-1] `
- Which gives an array of their index in `osc`
Where `osc_sort = osc[np.argsort(mhm[-1,:])[::-1]]` gives the actual `osc` numbers

Then in the plot I index the labels from `osc_sort` while indexing the values from `mhm` (array of mean weights across all epochs and trials) with `osc_order`

The resulting plot is better: ![[image-20230127120049461.png|400]]

I really can’t get the heatmap to work though.
Despite anything I do it looks like: ![[image-20230127122031105.png|400]]





# [[16.01.23]]
## Picking back up and adding
- `metahistory` is the array of all weights across epochs and trials for all oscillators
- `metaautoonhistory` is the array of all “pulls” across epochs and trials for all oscillators
- `mhm` is the “meta-history mean”. Meaning the average of the `metahistory` across epochs
- `mahm` is the “meta- auto-on-history mean”. Meaning the average of the `metahistory` across epochs
- `mahst` is the “meta auto-on history sum and transpose”, summed across epochs
	- this is for the heatmap

### Current run `reward_period` =173
- Seems to just highly reward the lowest oscillators 
- Each subsequently longer oscillator receiving less reward
- Something isn’t right here
	- I don’t think it’s the sort 
- It looks like there is no penalty
	- weights plateau
	- yeah looks like I removed the decay
- The heat map looks different and wrong somehow
	- It’s not even showing max value for its own max, which has to be there somewhere
	- 

### Future niceties
Once I can figure out how to do these
- Add tick marks in the plot that show where rewards were given

## Next steps
- take performance metrics of epochs with randomly selected reward-phase
- 

## review of where I left off
- Forgot to add that I split off the code into a new version called [SBF Temp Automata 12.12.22 Multiple Epochs.ipynb](https://colab.research.google.com/drive/1hwHdN0Jx6F9eHmwY_o2jzjcKz-8fihea?usp=sharing)
- This version attempted to make a raster plot as requested
- This is made from an combined average of 100 epochs
- ![[image-20230116114825691.png|400]]
	- Where Y axis is the oscillator prime 
	- and X is the timestep where reward was delivered
	- The “heat” is how often that oscillator was being pulled
		- No this can’t be right
		- I think it is instead the reward gained across epochs
		- 

- I think from here I should move onto a more probabilistic model
- Though first this should be re-run with some sort of normalization to the weights
- **Fig 2.** I think the following image is the increase in weight on the oscillators with time ![[image-20230116133935973.png]]




# [[15.12.22]]
- I think our next step is to add [[Weighted majority algorithm]]

##  Weighted Majority Algorithm
From [Weighted Majority Algorithm: A beautiful algorithm for Learning from Experts](https://ash-aldujaili.github.io/blog/2018/01/08/wma/):

> In this post, we demonstrate the theoretical gurantee on the performance of the **Weighted Majority Alogorithm** (_WMA_) with empirical validation. WMA is one of the beautiful algorithms in the framework of online learning and sequential decision making under uncertainity.
> 
> First, let’s describe a setup where WMA can be used. Assume that a friend of yours challenges to a **True or False** quiz where you’re allowed to seek help / advice from $n$ advisors throughout the game.
> 
> With this challenge at hand, WMA helps you play the game such that the number of your mistakes is upper bounded by roughly twice the number of mistakes made by your best advisor, i.e., the least number of mistakes made among your $n$ advisors. In the next paragraph, we’ll see how you can use WMA in the game.
> 
> For each advisor $i$ and question (round) $t$, WMA associates a weight $w^t_i$. With $w^1_i=1\;, \forall i=1,\ldots, n.$ Assume the game has $T$ rounds. If advisor $i$ makes a mistake at round $t$, its weight is adjusted by a multiplicative factor $1-\eta$ where $\eta\in(0,1/2)$. That is, $w^{t+1}_i= (1-\eta) w^t_i$ if $i$ makes a mistake. Otherwise, $w^{t+1}_i=w^t_i$. At each round $t$, your decision is governed by the sum of weights of advisors who think the answer is **True** versus that of those who think the answer should be **False**. Mathematically, denote your answer at round $t$ by $y^t$, and the advisors’ answers by $x^t_i$. These variables take the values $0$ and $1$ to represent _True_ and _False_ respectively.

> Let’s put WMA in action. Below, I have created $n$ advisors whose decisions at each round are based on tossing coins whose bias is sampled uniformly, $p_i\sim \mathcal{U}(0,1)$. Likewise, the game generates questions whose answers follows a Bernoulli distribution with $p_g\sim\mathcal{U}(0,1)$. We denote the correct answer at round $t$ by $z^t$. Also, let’s try to validate the theoretical bound on its performance. From [this](https://www.cs.princeton.edu/courses/archive/fall13/cos521/lecnotes/lec8.pdf), after $\hat{t}$ rounds,

See the code implemented at [[Weighted Majority Algorithm - A beautiful algorithm for Learning from Experts]]
# [[12.12.22]]
## Revisiting the supervision meeting from 2 weeks ago [[Supervision  - 29.11.22]]
### “You can simplfy to a deterministic master node” 
- What was meant by this exactly?
- Something about setting it to a threshold value
- How is the current master node woking?
	- It currently uses a probabilistic method
- Ok making a fix of it in the colab

## Initial changes to code
### Changed the probabilistic pull to a threshold pull

Changed WELL FUCK YOU TOO WINDOWS can’t fucking get rid of deadkeys making it impossible to type codeblocks here

Changed the probabilistic pull from
`if np.random.random_sample() >= prpull:`
to 
``` python
if prpull >= pull_threshold :
	pull_threshold = prpull # making this somewhat Metro-Hasting
else:
	pull_threshold = pull_threshold - 0.1
```

So that it will pull once it is above a certain threshold and then set the pull sum as the new threshold with a  decay for each time it isn’t met.

The decay adds an interesting wrinkle where the top 3 oscillators includes 2 until you hit decay of `0.0005`
as opposed to `0.001`

### Raster plot of master node activity
- Should look like [[image-20221129152622461.png]]
- Channel index (Y-ax) should correspond to:
	- First version: oscillators active
				- Heat map as a sum of times pulled at that timestep over multiple iterations
	- Second version: Thresholds?
		- Probably not this
- Time (X-ax) will be the time
- Had to swtich to a heatmap because this reflects the situation better

## Notes on Code
- I’m trying to get a plot where we can see the activation of the nodes 
- This doesn’t really work because there is some times where the nodes simply are not on
- in fact this is the majority in the low-timelength regime
- rn, everything is sort of a mess
	- as in the way I have the threshold and pull requirments set is sort of arbitrary at the moment as I am grasping to make something that matches the desired requirements
- 


```dataview
table without id
rows.file.link AS "Today's Notes",
rows.type AS "",
dateformat(rows.file.ctime, "T") as "Creation Time"
from ""
where contains(creationtag, "2022-12-12")
OR file.cday = date(2022-12-12)
group by type
sort file.ctime desc 
```
---

