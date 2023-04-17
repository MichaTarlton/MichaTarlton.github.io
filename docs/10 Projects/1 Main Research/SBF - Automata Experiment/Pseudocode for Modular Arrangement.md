---
type: [development, pseudocode, abstract, writing]
status: active
priority: p2
project: NA
creationtag: 2023-04-03 17:47
infotags: pseudocode
people: na
date:
---

Spawned from :: [[SBFA Development Log]]


# Outline
pseudocode
Remapping model and environment

Use Current alog as the outside loop



then load the target model (how does it load a function, can I pass that in somehow?)

Model will take an action alongside env and get reward

Ok maybe make the model do decision first, then input to env



Choose current environment:

    Might be impossible to disentangle
    
    AN environment will take the timestep as input and output reward availability (perhaps expand to none/punish/kill/reward/ rew or pun values)
    Internally an env may do some calculation, say probability distributions of reward value or availability

return reward, scale,
    # Let 1 = R, 0 = none, -1 = pun
    #

How will I do RPE with this?
Might only work with gradual changing cycles


# Main loop
The conditions, trials and timesteps to run the experiment for


# Model
The model to be used in the environment

# Environment
The environment in which the model will act upon.
This will likely be inside the Model loop.