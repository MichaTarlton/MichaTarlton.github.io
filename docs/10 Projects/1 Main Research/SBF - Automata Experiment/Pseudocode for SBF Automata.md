---
type: [development, pseudocode]
status: active
priority: p1
project: SBF-automata
creationtag: 2022-11-28 11:27
infotags: [code, dev]
people:
date:
---

**This is older and probably not current as of [[21.03.23]]**

# Statement
- I can’t really code anywhere else rn (can’t do it online and my PC is unstable and not backed up)
- So I will make some pseudo code here

# Code

## Main.py
- This will be the primary

``` pseudocode
# Main.py
## Variables
t = 0 
	# timestep, from 0 to end
	# because this algo performs no operations or decay on non-reward timesteps 
	# you can accelerate it by setting t = t * rp

endtime = arbitrary end step, say we want to run to 1E5 timesteps

rp = reward-phase. oscillation phase with which the environment delivers optimal reward

osc = oscillators and phase value.
		Can also be a distribution of oscillators
		as long as they divide evenly by a single timestep
		e.g. (1,2,3,5,7,11,13,17,19,23,29)
		Could set to something like primes(1, endtime / 2) if it has that functionality

n = size(osc) # size of vector of oscillatory automatas

weights = ones(n) / n   # the vector of weights for each oscillator node
						# starts as an even distribution of contribution

alpha = learning increment control parameter. Something like 0.05
beta = decay parameter for non-learning nodes. Should be set super low
gamma = negative reinforcement. disabled for now.

# functions
env = environment(reward-phase)
auto = automata(osc, t, reward-phase)
node = mainnode(autoon, autooff)

from t to endtime

autoon = auto(osc,t,rp)

weights = mainnode(weights, autoon, alpha, beta)




end




```

## Environment.py
``` pseudocode
# Environment.py
# Actually, if we are just running everythin on a modulo we may not even need this
# set this up to be used in case of variable environments, or environment distributions

inputs(t, reward-phase)

return 
```

## Automata.py
- The oscillatory automata check to see if they receive reward on their “wake”
- Updates weights

``` pseudocode
# Automata.py
# maybe split this up a bit as oscs only need to be input once and t is each timestep
# yeah I think this will work by making automata a class, and then making a subform which acts as our actual function

## Variables

autoon = empty vector, to store oscillators that were active at timestep t with reward
autoff = oscillators which were active at time of no rewards

inputs(osc, t, reward-phase) # from main

if modulo(t, reward-phase) = 0

	autoon(modulo(t, osc) = 0) == 1
		# i.e. set the vector location of active oscillators when reward was given to "1"
end 
		# Alternatively we can add a "punish" signal to mark the active oscillators 
		# when there was no reward.
		# However I'm not to add negative reiforcement for now
		# but if I did it'd go a little somehting like:
		# autooff(modulo(t, osc) != 0) == 1
			# Note this is not negative reinforcement fo inactivity but activity with no reward
			# also just fix this to be part of the autoon except negative values are assigned	
			# and thus just one output
			# or just do it like below in the weight updates *shrug*

return autoon 
```



## mainnode.py
- Does the weighted sum of the oscillatory nodes to make its decision on the pull
- Also means I did this backward , where the automata function basically already does the check function automatically
- So basically this would come first in operations order, probably the main part 

- This should perform the weighted sum 
- Should I make

``` pseudocode

# mainnode.py

input(weights, autoon, alpha, beta)

# calculate pull probability
prpull = sum(autoon * weights) 
	# probability of pull is the sum of active nodes and their weights 

# Perform pull
if rand(0,1) >= prpull 
	# if sum(autoon) >= 1 # won't need this if prob of pull is 0.0
	weights = weights
		+ (autoon * alpha)      # Increase weights of contributing oscillators
		- ((autoon = 0) * beta) # inverse autoon to ones where no oscillator was on
								# and contribute decay
end

return weights

```

