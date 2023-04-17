---
type: review
status: active
priority: p1
project: MLSS^N 2022 Krakow
creationtag: 2022-08-03 16:08
infotags:
people:
date:
---

The school ran from 27.06 - 02.07
[[Rianne Van Den Berg Lecture]]
[[Andrew Saxe]]
[[Ewa Szczurek]]
[[Joao Henriques]]
[[Andrea Tagliasacchi]]
[[Poster Session notes]]
[[Our Contribution to Continual Learning]]


See the list of all related pages on the main page

# Tasks
```tasks
not done
path includes MLSS^N 2022 Krakow
(tags do not include #reading) AND (tags do not include #rd) AND (tags do not include #topic) AND (tags do not include #tp)

```
## Tasks
```
dataview 
TABLE WITHOUT ID 
Tasks.text AS Task,
Tasks.section AS "link"
FROM "10 Projects/MLSS^N 2022 Krakow"
WHERE !completed
AND !contains(text,"#topics")
AND !contains(text,"#tp")
AND !contains(text,"#reading")
AND !contains(text,"#rd")
SORT file.mtime DESC
FLATTEN file.tasks AS Tasks
```
## Topics
```dataview 
TASK 
FROM "10 Projects/MLSS^N 2022 Krakow"
WHERE !completed
AND contains(text,"#topics")
OR contains(text,"#tp")
SORT file.mtime DESC
```
## Reading
```dataview 
TASK 
FROM "10 Projects/MLSS^N 2022 Krakow"
WHERE !completed
AND contains(text,"#reading")
OR contains(text,"#rd")
SORT file.mtime DESC
```

# Adding Talks that were only on tablet


# List of Reading and Topics
insert dataview for reading
insert dataview for topics
- see if you can attach contextual tags from the frontmatter

# Unknown Note
Topic: Conceptor

