---
aliases: 
type: project
project: obsidian/better-reading
status: open
priority: p4
creationtag: "2022-05-31 13:36"
infotags: 
---
```dataview
table rows.file.link AS "Related",
file.ctime as "Created",
infotags as "Tags"
FROM ""
WHERE contains(project,"Better Reading ")
GROUP BY type
SORT file.ctime asc 
```
# Needs
I need to be able to track what I’ve read and extract important parts from it. 

I need this to be as simple as possible.
- so no mdnotes *and* citations

I need the tags and everything to be pulled into the main cite note the same way MD notes does it


# Notes / dissection of papers

Extracts
- latex would be nice
Annotations / comments
- best to come directly over from zotero if porting from a pdf reading of it
References / further reading
- already using a strategy of 
	- O “sounds interesting”
	- OO “Must Download / Read”
“Reference” for notation used inside the document
- another reason for latex

Topics
- concepts which need further clarification
- Typically I set the extended reading into here
- 
