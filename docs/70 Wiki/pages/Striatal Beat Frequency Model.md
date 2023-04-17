---
aliases: [SBF, Beat Frequency]
type:  wiki
status: open
priority: p4
creationtag: 2022-11-16 14:55
infotags: [Striatal Beat Frequency, SBF,]
---
---
# Notes
## PA and BF are mutually exclusive
- PA has pulses that accumulate
	- [ ] Sort of like a elgibility trace in three-factor hebbian? #q 
	- 
- BF doesn’t use an accumulator but examines which oscillators are in phases at a moment of recall
	- I think
# Main
- Originally proposed by [[@matellNeuropsychologicalMechanismsInterval2000|Matell & Meck (2000)]], 
- the SBF is a type of [[pacemaker accumulator models (PA)]]
## Explanation
From [[@hartcher-obrienSingleMechanismAccount2016|J. Hartcher-O'Brien, C. Brighouse, C.A. Levitan (2016)]]
> **Ensembles of oscillating neurons code the incoming signal duration**. 
**These neurons reset and synchronize at the onset of the “to be timed” stimulus**. 

> At the criterion time ‘d<sub>t</sub>’ (dotted vertical line), the phases of all oscillators are stored in reference memory, for later comparison. 
> 
> Given a collection of neurons oscillating at different frequencies, as time passes there will be instants at which sub-ensembles will be in phase (grey dotted line). 
> 
> **The frequency at which a sub-ensemble is in phase is its “beat frequency”**. 
> 
> These sub-ensembles code for the duration of an interval, the “beat period”, the interval marked by the time between consecutive instants at which they are in phase. 
> 
> The many sub-ensembles of a collection can code numerous durations, and durations of lengths considerably longer than the frequency of any single oscillator in the ensemble. ^zcwzc3





# Reading
20. Miall C. The storage of time Intervals using oscillating neurons. Neural Comput. 1989;1:359–371. [Google Scholar](https://scholar.google.com/scholar_lookup?journal=Neural+Comput&title=The+storage+of+time+Intervals+using+oscillating+neurons&author=C+Miall&volume=1&publication_year=1989&pages=359-371&)

# Internal References
```dataview
LIST
FROM ""
WHERE contains(infotags,"SBF")
sort file.ctime desc
``` 
```query 
line:(Striatal Beat Frequency) OR  line:(SBF) 
```