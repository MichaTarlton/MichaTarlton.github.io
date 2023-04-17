---
type: dash
status: open
priority: p0
project: research
creationtag: 2023-02-01 07:37
---

See [[Projects Table]]
See [[Active Projects Overview]]
See [[Open Projects Overview]]

# All Projects
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