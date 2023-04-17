---
aliases:
type: project
project: Obsidian Addons and Todos
status: open
priority: p4
creationtag: 2023-04-11 11:21
infotags: [obsidian, presentation]
---

**Statement**:: Just making a list of stuff I think is interesting and could be added to my workflow
```dataview
table rows.file.link AS "Related",
file.ctime as "Created",
infotags as "Tags"
FROM ""
WHERE contains(project,"Obsidian Addons and Todos")
GROUP BY type
SORT file.ctime asc 
```


# [[02.04.23]]

##  Adding stuff for [[MD Slides]]

![[MD Slides#starting out]]



## Other stuff I thought was interesting
