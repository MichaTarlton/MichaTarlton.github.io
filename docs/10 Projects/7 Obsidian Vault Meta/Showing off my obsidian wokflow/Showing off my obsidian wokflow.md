---
aliases: []
type: project
project: obsidian/wokflow
status: open
priority: p4
creationtag: 2022-06-07 13:27
infotags:
---

```dataview
table rows.file.link AS "Related",
file.ctime as "Created",
infotags as "Tags"
FROM ""
WHERE contains(project,"obsidian")
GROUP BY type
SORT file.ctime asc 
```
# [[08.08.22]]
- Had  a small meeting where I presented what I was working on and that kinda solidified some concepts of my workflow
- Wrote about the theory of my note taking on my boox. see there

# Notes
## Zotero
- When linking a new zotero db for a new academic project (such as PHD)
	- Create a new zotero library entirely and link that to the specific Obsidian vault
	- Not sure how to do multiple zotero libraries rn
	- But let’s just focus on one for now

# The scope
- The idea of research is sort of an extraction of information reformation and then reintegration into something new
- A sort of convolutional network almost
