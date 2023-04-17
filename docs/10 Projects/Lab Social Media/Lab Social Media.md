---
aliases:
type: project
project: lab-social
status: open
priority: p4
creationtag: 2023-03-28 12:14
infotags:
---

```dataview
table rows.file.link AS "Related",
file.ctime as "Created",
infotags as "Tags"
FROM ""
WHERE contains(project,"lab-social")
GROUP BY type
SORT file.ctime asc 
```
