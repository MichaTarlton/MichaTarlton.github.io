---
aliases:
type: project
project: ai-lab-wiki
status: open
priority: p4
creationtag: 2022-12-14 13:48
infotags: [wiki, ai-lab]
---
# Statement
To create a lab-wide collaboration and knowledge sharing platform to passively increase our lab’s ability to interact, collaborate, publish, and outreach publically.


# Loose Ideas
- Using Notion for collaborating
- 


# Queries

```dataview
table rows.file.link AS "Related",
file.ctime as "Created",
infotags as "Tags"
FROM ""
WHERE contains(project,"ai-lab-wiki")
GROUP BY type
SORT file.ctime asc 
```
```query 
line:("wiki")
```