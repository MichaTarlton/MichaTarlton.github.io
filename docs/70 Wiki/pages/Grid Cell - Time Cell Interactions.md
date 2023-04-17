---
aliases: []
type: wiki
status: open
priority: p4
creationtag: 2022-11-24 15:49
infotags: [Grid-Cell, Time-Cell]
---
# Statement
Investigate potential overlaps between time and spatial neural interactions. Namely the interactions between time cells and grid cells, as spoken about in [[@tekiPersistenceMemoryHow2017|S. Teki, B. Gu, W.H. Meck (2017)]].

# Queries
```tasks
not done
tags includes grid-cells
short mode
```
---
```dataview
LIST
FROM ""
WHERE contains(infotags,"grid")
WHERE contains(infotags,"time")
sort file.ctime desc
``` 
```query 
line:(Grid Cell - Time Cell Interactions) OR  line:(undefined) 
```