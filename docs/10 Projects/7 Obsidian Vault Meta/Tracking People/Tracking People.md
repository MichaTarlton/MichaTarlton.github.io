---
aliases: []
type: project
project: obsidian/contacts
status: open
priority: p4
creationtag: 2022-05-27 15:54
infotags:
---

```dataview
table rows.file.link AS "Related",
file.ctime as "Created",
infotags as "Tags"
FROM ""
WHERE contains(people,"Tracking People
")
GROUP BY type
SORT file.ctime asc 
```

Add `authors` as a key since that’s what mdnotes uses.