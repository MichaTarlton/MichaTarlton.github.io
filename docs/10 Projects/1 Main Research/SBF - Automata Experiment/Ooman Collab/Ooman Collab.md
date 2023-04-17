---
aliases: "oomman collaboration"
type: project
project: sbf-automata
status: closed
priority: p5
creationtag: "2022-11-08 14:31"
infotags: [SBF, automata]
---

# Formerly the Automata Oscilllators Project

Has become part of [[SBF - Automata Experiment]]
merge it into that one
# Statement
- See notes in boox
- We want to create an automata framework which relies on cyclic oscillators as a means of deciding actions in time
- This will borrow heavily from [[Topics - Striatal Beat Frequency model (SBF)]] 
	- Thusly can be though of an extension of the [[Survey Paper]] project and its derivatives


```dataview
table rows.file.link AS "Related",
file.ctime as "Created",
infotags as "Tags"
FROM ""
WHERE contains(project,"oomman")
GROUP BY type
SORT file.ctime asc 
```

# Initial Meeting with Oomman

# Meeting with Anis
- Oscillators
- We need to use oscillators that cycle on prime timesteps
	- this way they overlap on a infrequent basis
	- not much use to have super-regular polling
- So we have oscillators that on some input from the environment 
	- take note of which oscillators are ‘on’ at that moment
	- Should it then see which oscialltors were in phase with the action
- [x] Need to expand on this algorithm (the SBF in automata) ⏫ #p1 #td [Todoist](https://todoist.com/showTask?id=6333371736) ✅ 2022-12-12
- [x] Study SBF and adapt this into here ⏫ #p1 #td [Todoist](https://todoist.com/showTask?id=6333371759) ✅ 2022-12-12
