---
aliases:
type: project
project: SBF-Model
status: active
priority: p2
creationtag: 2022-08-05 11:41
infotags: sbf
---

```dataview
table rows.file.link AS "Related",
file.ctime as "Created",
infotags as "Tags"
FROM ""
WHERE contains(infotags,"SBF")
OR contains(infotags,"sbf")
OR contains(project,"SBF-Model")
GROUP BY type
SORT file.ctime asc 
```
Ok so the goal of this is to implement the SBF, or pulse accumulator model in code so that I can try to make a spiking implementation of it.

I’m going to look up the original paper, Matell and Meck 2000, and see if that lays out the algo in particular.

# Reading
## [[@matellNeuropsychologicalMechanismsInterval2000|Matell & Meck 2000]]
Can’t import due to issue with plugin. Uncertain as to cause and not wasting more time troubleshooting. nvm fixed it too late.

## [[@melloNeuralBehavioralMechanisms2016|Gustavo Borges Moreno e Mello 2016]]

[[@tallotNeuralEncodingTime2020|L. Tallot, V. Doyère 2020]]

[[@yinOscillationCoincidenceDetectionModels2022]][[Outline of SBF Model]]
