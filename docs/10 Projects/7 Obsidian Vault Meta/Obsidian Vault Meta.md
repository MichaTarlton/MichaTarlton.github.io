---
aliases:
type: project
project: obsidian
status: open
priority: p4
creationtag: 2022-10-18 15:32
infotags:
---

Need to work on a better dashboard
[[Obsidian web browsing -12.01.23]]


# Statement 

# Needs
- I need a way to tag projects in a task 
	- A separate tag like todoist does
	- It would be nice if it just linked directly to todoist and created projects there as necessary
- 
- Footlinks as inline comments?
	- Let me see if possible already
- Better integration python notebooks especially since they are mostly using md already
- Plenty of fixes to be had with regards to e-reader and zotero
- Add recently modified logs to main log to get around below issue
- To make entries in one log, with a tag that will make the entry also appear in a relevant project log
- Need to set up quickadd templates to auto add metadata when creating from a certain note
	- See this: [Reading frontmatter of other notes, like Dataview can · Issue #344 · SilentVoid13/Templater · GitHub](https://github.com/SilentVoid13/Templater/issues/344)
- DV needs a better tracking of tags
- So say I want to show all sub-projects with a project
- As seen here:![[00 AI-Lab Log#Organizing projects]]
## Maybe add an organization class?
- possibly alongside people class
- Some sort of contacts / networks 


```dataview
table rows.file.link AS "Related",
file.ctime as "Created",
infotags as "Tags"
FROM ""
WHERE contains(project,"obsidian")
GROUP BY type
SORT file.ctime asc 
```
