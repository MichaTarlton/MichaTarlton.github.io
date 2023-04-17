```dataview
LIST WHERE contains(file.folder, this.file.folder)
```
### Presentations in the whole Vault
```dataview
TABLE without id
file.link as "file",
dateformat(file.mtime, "ccc, LLLL d") as "Modified",
project as "Project",
priority as "Priority"
FROM "" AND -"ZZ. planning" AND -"AZ. Assets"
WHERE contains(type,"presentation")
OR contains(infotags,"presentation")
SORT file.mtime DESC
```

# How to presentations
See [[Obsidian Addons and Todos#Adding stuff for MD Slides]]
- Note: To use navigate to http://localhost:3001/#/ , you can press ‘S’ to bring up the speaker view in the browser