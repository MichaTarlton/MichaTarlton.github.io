---
aliases: [IT, Temporal Intervals, Fixed Interval, (FI)]
type: topics
status: open
priority: p1
creationtag: 2022-06-08 10:59
infotags: [interval timing, serial fixed interval task]
project: survey paper/timing tasks
---
[[Fixed Interval (FI) procedure]]
[[Peak Interval (PI) procedure]]

atm using this to keep track of **Fixed Interval** timing but it’s not the same thing.
In fact what we are seeing here is IT referred to in most of the texts is the brain regions associated with tracking intervals of time
# Possible References
[[@liMiceInferProbabilistic2013]]
[[@zhouEncodingTimeNeural2022]]

[[@yinIntervaltimingProtocolsTheir2017|Bin Yin, Nicholas A. Lusk, Warren H. Meck 2017]]
- A book chapter writen with meck 
- Would have been a good place to start
[[@petterIntegratingModelsInterval2018]]
- On Training RL models with these in mind


# Variant: Peak Interval (PI) procedure

^834cad
## [[@hasegawaModelMultisecondTiming2015|Takayuki Hasegawa, Shogo Sakata 2015]]




## [[@balciPeakIntervalProcedure2020|Fuat Balcı, David Freestone 2020]]
or no, it’s different but rooted in that?
![[image-20220630115532239.png]]


>  ![[The Peak Interval Procedure in Rodents A Tool for Studying the Neurobiological Basis of Interval Timing and Its Alterations in Models of Human Disease - 29.06.22#^644158]] ![[The Peak Interval Procedure in Rodents A Tool for Studying the Neurobiological Basis of Interval Timing and Its Alterations in Models of Human Disease - 29.06.22#^rr6nlj]] ![[The Peak Interval Procedure in Rodents A Tool for Studying the Neurobiological Basis of Interval Timing and Its Alterations in Models of Human Disease - 29.06.22#^9al9rc]] 


## FI training

***Fixed Interval (FI) Training***
    
    7.  A trial is initiated with the presentation of the discriminative stimulus. The stimulus stays for a minimum of the FI and it is turned off contingent upon the first response following FI. The first response following the FI is reinforced (some also require that the response occur earlier than 3xFI). The experimenter might choose to present the stimulus longer than 3xFI, but this typically not necessary. After each trial, an exponentially distributed inter-trial interval (ITI) is introduced. This is important to reduce how predictable the next trial is. This training phase, including only simple Fixed Interval trials, is usually conducted daily for at least 5 sessions before introducing peak trials. Use raster plots to track their acquisition. The data should be studied on a daily basis with simple visual or statistical summaries that showcase the most raw form of the data possible. If a scalloped responding is not observed in any of the subjects, FI training can be extended. [Figure 2A](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7854006/figure/BioProtoc-10-17-3735-g002/) illustrates the typical pattern of responding observed in FI trials.
    

## PI Training
***Peak Interval (PI) Testing***
    
    8.  Peak Interval (PI) trials are randomly mixed with FI trials. In PI trials, the stimulus lasts at least three times longer than the FI and the reinforcement is omitted, regardless of the animal’s behavior. The proportion of FI to PI trials can change between 1:1 to 1:3. A lower proportion of peak trials will facilitate the acquisition of peak interval responding but because we typically focus on PI trials in analysis, this will also result in less data per session ([Kaiser, 2008](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7854006/#r36) and [2009](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7854006/#r37)). The duration of the PI trials can also be varied between trials or sessions (but at least 3xFI). [Figure 2B](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7854006/figure/BioProtoc-10-17-3735-g002/) illustrates the typical pattern of responding observed in PI trials.
        
    9.  After each session, gently remove the animal from the operant box and place it promptly either in the holding case or the home cage available nearby. Wipe the grid with a 70% ethanol solution to minimize olfactory cues between different sessions. Provide supplemental food or water about an hour after the test session.
    

What if they made the end of the interval a window, and not a hard stop?

![[@patonNeuralBasisTiming2018#^ganoui]]

## Delayed v. Immediate Reinforcement
- [ ] citation?
## variable interval reinforcement
- [ ] citation?

# Serial Fixed Interval task
see [[Fixed Interval (FI) procedure|fixed interval]]

- I feel like I should have more here on fixed interval training as from reading Tallot and Gustavo’s thesis, it seems to be an important task in respect to experimenting
- As there seems to be plenty of literature in modeling brain mechanisms in relation to this task, it may be prudent to try reproducing it in our experiments
- Though personally I’d like to lean into action policies within mixed time-frames (see below)

## [[@tallotNeuralEncodingTime2020|L. Tallot, V. Doyère 2020]]
![[@tallotNeuralEncodingTime2020#^ifi9zk]] 
![[@tallotNeuralEncodingTime2020#^v9aff4]]

![[@tallotNeuralEncodingTime2020#^28pf42]]



## [[Mello, Soares, Paton 2015]]

> *“Experimental Procedures for details) shown in Figure 2A. Some cells fired just after reward delivery, others fired in the middle of the delay, and others fired leading up to the next reward (Figures 2A, S2, and S3). This produced a slow-moving ‘‘bump’’ of activity that traversed the population during each FI.”* (p. 1115)
![[@melloScalablePopulationCode2015#^7u4fc8]]
![[melloScalablePopulationCode2015_44BX6Q7X 1.png]]


## [[@patonNeuralBasisTiming2018]]

![[patonNeuralBasisTiming2018_24TGMQX5.png]]


---

![[80 Meetings/06.22/Gustavo Meeting - 08.06.22.md#^0f65e1]]
# Suggested Authors From Gustavo
Meck
- Paton
- Names
- Warren Meck
- Armando Machado
- Dean Buonomano
- Joseph James Paton
- Peter Dayan
- Schultz
- Redderik Van Rijn
	- https://www.van-rijn.org
- Randy gallistel 
- Group in 

Meck and Gershman are talking more about RL and interval timing where they weren't previously.
# Papers relating
![[interval timing.txt]]

