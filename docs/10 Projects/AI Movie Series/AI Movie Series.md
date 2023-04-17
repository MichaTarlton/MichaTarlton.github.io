---
aliases:
type: project
project: movie-series
status: open
priority: p4
creationtag: 2023-04-03 16:52
infotags:
---

```dataview
table rows.file.link AS "Related",
file.ctime as "Created",
infotags as "Tags"
FROM ""
WHERE contains(project,"AI Movie Series")
GROUP BY type
SORT file.ctime asc 
```


# Log
## [[02.04.23]]
- Contacted mediasektion about working with a film club