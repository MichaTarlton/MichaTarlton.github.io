---
aliases: 
type: project
project: Survey Paper
status: active
priority: p1
creationtag: "2022-06-01 14:24"
infotags: 
---
```dataview
table rows.file.link AS "Related",
rows.file.ctime as "Created"
FROM ""
WHERE contains(project,"Survey Paper")
OR contains(project,"survey paper")
GROUP BY type
SORT file.ctime asc 
```
## [[Survey Paper Tasks]]
# Goal
***Creating a Survey paper which looks at all timing tasks***

It is supposed to be a paper survey current research landscape, and state our intent.
# References for inspiration
[[@patonNeuralBasisTiming2018]]
[[@ponulakIntroductionSpikingNeural2011]]
- [[@melloNeuralBehavioralMechanisms2016]]
- [[@melloScalablePopulationCode2015]]

![[Pasted image 20220608152740.png]]

# Topics
- [ ] pick a topic
[[Interval Timing]]
[[70 Wiki/topics/Timing Tasks]]

Survey of SNN timing, specifically interval timing tasks

Survey of RL in Interval Timing Tasks
- perhaps the better option

Want to work in the minute to seconds range.
Anything above or below this is a different area.

I want to work on timing based tasks with SNNs


# Log

# [[11.06.22]]
## Ok need to get this back on track
So I should go back to the last meeting with gustavo and restart from there I think

Need to refocus on [[Interval Timing]]




---


## [[09.06.22]]

```dataview
table without id
file.link AS "Today's Notes",
file.ctime as "Creation Time"
from ""
where contains(creationtag, "2022-06-09")
OR file.cday = date(2022-06-09)
AND contains(project, "Survey Paper")
sort file.ctime asc 
```
---


# [[08.06.22]]
## Watching some YT videos as suggested
[How To Write A Survey Paper (or Summarize Existing Research) - YouTube](https://www.youtube.com/watch?v=at9SMlZyaVg&t=392s)

[How to write good survey paper - YouTube](https://www.youtube.com/watch?v=_NG_EdqOJSA)
- Uses example paper: Liu et al. 2017 Survey of Deep Neural Network Architectures…
- this is a bad video

[Writing the Best Paper (Vol 5) - How to Write a Survey Paper? Research Tutorials with Dr. Sourish - YouTube](https://www.youtube.com/watch?v=1mkGunK9sk8&t=1256s)
What am I writing a survey about?
![[image-20220608151041892.png]]

[How to write a Survey Paper | PhD | Research | Gaurav Soin - YouTube](https://www.youtube.com/watch?v=oN6dt0uCkio)
- this one is honestly worse
![[image-20220608232515547.png]]




## Deriviative works of [[@patonNeuralBasisTiming2018]]

Looked at this over at connected papers to pick up a few more for reading. However, I also picked up a ton of additional papers that were in the same sort of orbit. 

Going to check out the primaries first, and secondary random stuff second

zhouEncodingTimeNeural2022
tallotNeuralEncodingTime2020
hardyEncodingTimeFeedforward2018

### First up [[@zhouEncodingTimeNeural2022]]
### 2nd [[@tallotNeuralEncodingTime2020]]



![[Gustavo Meeting - 08.06.22]]
## Follow up with Gustavo later

1- watch 3 videos on how to write review, research survey or opinion papers

2- take notes on that and draft a plan of how you are going to do that

3- try to imagine yourself going through the steps and see if any information is missing. Would you be able to do it if I asked you to do it today?

4- try to find other videos up to 3, on how to do the thing you do not know how to do very clearly.

5- take notes

6- try to find more reliable (academic) sources on the matter. Check if something is missing or if there is anything that is unnecessary

7- refine your process again. Be sure that the steps are actions.

We talk contentment tomorrow

