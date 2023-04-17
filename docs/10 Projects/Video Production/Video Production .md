---
aliases:
type: project
project: video
status: open
priority: p4
creationtag: 2022-10-31 10:55
infotags:
---
# Statement
Make tutorial or explanatory content for the research I’m reviewing. Perhaps in the future spin out into further content development and promotion of research.

# Log
See the stuff I’ve done on OBS
## [[11.11.22]]
Takeaways from today’s experiment in [[Video - How Critical is Brain Criticality]]
- Dissect for yourself and then make a script



```dataview
table rows.file.link AS "Related",
file.ctime as "Created",
infotags as "Tags"
FROM ""
WHERE contains(project,"video")
GROUP BY type
SORT file.ctime asc 
```
