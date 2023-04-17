---
type: dash
status: open
priority: p0
project: research
creationtag: 2022-05-04 15:15
---

See [[Projects Table]]
See [[Open Projects Overview]]
See [[All Projects Overview]]
# Active Projects view
Active, ranked by priority
## Priority 1
```dataview
table without id
rows.file.link AS "Projects",
rows.infotags as "Tags",
rows.project as "Project Tag",
dateformat(rows.file.cday,"dd.MM.yy") AS "Date", 
rows.status as "status"
FROM -"ZZ. planning"
WHERE contains(type,"project")
AND contains(priority, "p1")
AND contains(status,"active")
sort priority asc
Group by project
```
## Priority 2
```dataview
table without id
rows.file.link AS "Projects",
rows.infotags as "Tags",
rows.project as "Project Tag",
dateformat(rows.file.cday,"dd.MM.yy") AS "Date",
status as "status"
FROM -"ZZ. planning"
WHERE contains(type,"project")
AND contains(priority, "p2")
AND !contains(status,"closed")
sort priority asc
Group by status
```

## Priority 3
```dataview
table without id
rows.file.link AS "Projects",
rows.infotags as "Tags",
rows.project as "Project Tag",
dateformat(rows.file.cday,"dd.MM.yy") AS "Date", status as "status"
FROM -"ZZ. planning"
WHERE contains(type,"project")
AND contains(priority, "p3")
AND !contains(status,"closed")
sort priority asc
Group by status
```
---
## Priority 4
```dataview
table without id
rows.file.link AS "Projects",
rows.infotags as "Tags",
rows.project as "Project Tag",
dateformat(rows.file.cday,"yy.MM.dd") AS "Date", 
dateformat(rows.file.mday,"yy.MM.dd") AS "Modified", 
status as "status"
FROM -"ZZ. planning"
WHERE contains(type,"project")
AND contains(priority, "p4")
AND !contains(status,"closed")
sort priority asc
Group by project
```
---
## Priority 5
```dataview
table without id
rows.file.link AS "Projects",
rows.infotags as "Tags",
rows.project as "Project Tag",
dateformat(rows.file.cday,"dd.MM.yy") AS "Date", status as "status"
FROM -"ZZ. planning"
WHERE contains(type,"project")
AND contains(priority, "p5")
AND !contains(status,"closed")
sort priority asc
Group by status
```

---

‘![[All Projects Overview]]# All Projects
```dataview
table without id
priority as "Priority",
rows.file.link AS "Projects",
rows.infotags as "Tags",
rows.project as "Project Tag",
dateformat(rows.file.cday,"dd.MM.yy") AS "Date", status as "status"
FROM -"ZZ. planning"
WHERE contains(type,"project")
AND !contains(status,"closed")
sort priority asc
Group by priority
```

# Group by Master Project
```dataview
table without id
rows.project as "Project Tag",
rows.file.link AS "Projects",
dateformat(rows.file.cday,"dd.MM.yy") AS "Date", status as "status"
FROM -"ZZ. planning"
WHERE contains(type,"project")
AND !contains(status,"closed")
sort priority asc
Group by status
```

# Files in “Projects” Folder
```dataview
TABLE 
	string(Status) AS "Status"
FROM "10 Projects"

```