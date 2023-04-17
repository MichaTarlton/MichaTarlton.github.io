# In this folder 
So like individual dossiers
```dataview
LIST WHERE contains(file.folder, this.file.folder)
```

# People Mentioned
```dataview
table 
rows.file.link AS "Mentioned",
file.ctime as "Created",
infotags as "Tags"
FROM -"ZZ. planning"
WHERE people
GROUP BY people as "Person"
SORT file.ctime asc 
```
