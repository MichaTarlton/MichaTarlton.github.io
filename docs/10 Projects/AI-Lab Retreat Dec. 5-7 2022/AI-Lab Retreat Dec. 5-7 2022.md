---
aliases:
type: project
project: AI-Lab-Retreat
status: closed
priority: p4
creationtag: 2022-12-05 09:22
infotags:
---

```dataview
table rows.file.link AS "Related",
file.ctime as "Created",
infotags as "Tags"
FROM ""
WHERE contains(project,"AI-Lab-Retreat")
GROUP BY type
SORT file.ctime asc 
```
# Writing Ideas
- SNN and Criticality Theory
- [[Group collaboration for living documents]]
- Research on Eligibility Trace and 
# 5-min presentation

> So, I ask you to prepare a up to 5 minutes max presentation about one of these things:
> 
> Your most current, not published work
> The idea of a research that you are planning to submit to get funding
> One exciting ground-breaking idea that you would like to research if you had the opportunity and resources
> Again, 5 min maximum, if you can use less time, the better!
> 
> Please focus on the core high-level ideas. Try to communicate:
> 
> What is the core problem that you are attacking?
> Why is this problem worth solving?
> What did you do / or can be done / to attack the problem?
> What is the core contribution that you made /or expect to make/ to solve the problem?
> How do you know (what is the evidence) that the contribution is achieved?

## The three-headed coin 
- [[Global Trigger Local Back-Propagation]]
### Deep Reinforcement Learning
- A problem of *credit-assignment*
- RL needs deeper models
- However, because RL is typically an *online* model
- That is, an RL model by definition learns based on ongoing input from an environment
- This makes learning algorithms such Backpropagation through time impossible 
- Especially wrt to the separation in time between an action and associated reward
- Instead approximate methods are used to figure out how to assign credit for a reward to particular neurons in the model
### Neuro inspired AI
- But fret not, we have a model of credit assignment that relies on reward for learning in a live environment
- The human brain
- The brain uses several methods for how it self-organizes its structure 
- At highly granular level it does this through local plasticity
- Spike-Timing Dependent Plasticity is a well supported model of local plasticity
- This is part of a type of models called Spiking Neural Networks
- These models will form the backbone of a new form of computing called neuromorphics
### Time in Biological Models
- As STDP and SNNs natively encode timing data in their dynamics
- How do they represent time as the population scales?
- Thus we will apply this to the challenge of RL for temporal problems
- Starting specifically with interval timing
- When your bus is leaving in six minutes, how do you track that internally
- How do you know to hurry or take it slowly to the bus stop
- Do you get a little burst of joy when you arrive right on time with the bus arrival
### Laws of Neural Complexity
- Because these STDP neurons are locally plastic 
- There must be tuning of their self-org rules to ensure they are optimally efficient
- This is where we get into 




# [[05.12.22]]
## Introductions
#people

### Mohammed
- egypt
- eeg data

### Marcus

### Fabrizio

### Rabindra

### Marina

## Gustavo - Intro speech
- wants us to resolves issues with writing as well

### Writing for:
1. Funding
2. reports (?)
3. Job apps
4. Instructions
5. Documentation
6. Sci Communication
7. one other thing

- I think we should focus here on three levels:
	1. Sci communication 
		- The first level and meant to be easily communicable
		- Heavily narrative oriented
	2. Report
		- The actual main document, the article
		- Somewhat narrated, but that takes backseat to presenting the experiment and results
	3. Documentation
		- imo, same as a methodology 


### What are your weaknesses in writing
-   I’m poor
-   Sometimes poor of imagination
-   Often can’t quite remember the topics and concepts I want to illustrate
-   Thus when trying to communicate a narrative, I tend to go about it very clumsily
-   However, if I have enough time to “script” and workshop, I can use my toolset to construct a very polished product

### Inner critic
What do you say to yourself when you fail at something minute?

- Why can’t I think straight
- Why can’t I think 
- Why am I
- [[test free writing]]

### Gustavo is talking about save the cat and the monomyth
- [[Problem challenge]]
- [[Contributions Challenge]]


## Munch Museet - Henrik
#art #munch
- Want to use ML for whatever?
- Exhibition driven by DL
- Image capture prototype
	- captures something that museum visitors draw
- Take something visitors draw and convert it to something
- Or could be projected on the wall
- Two options, to compete or to run the competition 

- Apparently they have tried turning stick drawings into munch stuff with “limited results”
- Add to [[Vicente Collab]]

## Gustavo assignment
- What journal do I want to apply to
- and a second thing I missed

## Gustavo Idea
- robustness of a network
- Evolutionary algo
- developmental algo
- Learning is the fitness factor
- Systems which are stable over time
- 
- May fold into my idea

# [[06.12.22]] Day 2
[[Free writing test 2]]
## Fuck we had an assignment?
- something like choose a journal
- and have in mind a person I am writing for

I literally have no idea what he wants us to write
I am giving up a bit at this point

## Goal (for writing session)
- to attack and dethrone god
- “Just for this session”
	- We are halfway into this session already there isn’t much time for much 
- I am almost angry
- I’m just stressed out
- But the stress is completely sublimated and suppressed to the point where it leaks out of me in non-conscious ways
- I feel sick, I feel tired, and I have done nothing

Fuck it. For this. 
My goal is to be doing 



# [[07.12.22]] Day 3

## Make a Research Question
- I’m really fucking lost on what is wanted

## A. Outline one pager of C???
- bankid
- Personal ID authentication
- Identity ecosystem
- identity provider
- centralized system
- If compromised whole ecosystem is halted
- **Recovery after compromise**
- Reissue of Digital IDs
	- From a secondary non-compromised source
- How long will it take to recovery
- What is the recovery strategy
- Some measurable parameters which will give
- Metrics for maturity of recovery, risk assessment 
- Both parts, preparedness and recovery
- Security insurance
- He had several potential tests to be scored
### The actual writing

Current identity authentication services currently rely on highly centralized and tightly protected services and organizations. BankID, FEIDE, and others, depend on keeping “secrets”, a portion of these secrets they parcel out to individuals in order to verify who they are against the secrets they keep in repository. In order to protect these secret from bad actors, they must heavily fortify defenses against non-sanctioned access. The centralization, while increasing the securability of these secrets, also means that any compromise of the isolate systems will cause a large-scale failure across the entire ecosystem.

How will these organizations made responsible for securing our secrets deal with failure. What recovery plans are in place in the case of widespread failure. How can penetration and damage be inoculated against. How can we create metrics to judge the preparedness levels of these organizations. Is a perfect level of preparedness even possible, will insecurities always exist.


- information security maturity model

### Rewrite
This falls 


### Feedback



## C.  Outline B
- Performance gaps
- Bottlenecks




## B.  Outline 

### Feedback to Tom’s one-pager
- Essentially offputs the argument into a Utilitarian framework, thus necessitating arguing on Utilitarian grounds
- However, I think the problem is more interesting when constrained to an interpersonal one
	- More freedom to debate what individualism is, what boundaries of self and others are, and what is an acceptable amount of “violence” between individuals
- 