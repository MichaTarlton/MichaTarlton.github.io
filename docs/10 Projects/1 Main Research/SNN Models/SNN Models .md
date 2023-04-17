---
aliases:
type: project
project: SNN-Models
status: active
priority: p2
creationtag: 2022-09-17 15:16
infotags: [SNN, software, dev]
---

# Statement
To understand and create models of Spiking Neural Networks

# Vault Queries
## Project Realted
```dataview
table rows.file.link AS "Related",
file.ctime as "Created",
infotags as "Tags"
FROM ""
WHERE contains(project,"SNN-Models")
GROUP BY type
SORT file.ctime asc 
```
## SNN Related
```dataview
table 
rows.file.link AS "Related",
rows.file.ctime as "Created",
rows.infotags as "Tags"
FROM ""
WHERE contains(infotags,"SNN")
GROUP BY type
SORT file.ctime asc 
FLATTEN Tags 
```
