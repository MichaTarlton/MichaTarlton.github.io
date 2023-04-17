---
type: people
people: Friedemann Zenke
aliases:
infotags: [SNN]
status: open
priority: 
project: 
creationtag: 2022-09-21 14:01
---

url::
twitter::

Uhhh addd literature search for him here

---
```dataview
TABLE without id
type as "type",
rows.file.link as "Related Files",
rows.title as "Title"
FROM ""
WHERE contains(people,"Zenke")
sort file.ctime desc
group by type
``` 

```query 
line:("Friedemann Zenke") OR  line:("Zenke") 
```