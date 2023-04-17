---
aliases: []
type: log
project: obsidian
status: open
priority: p4
creationtag: 2022-06-15 11:04
infotags:
---

```dataview
table rows.file.link AS "Related",
file.ctime as "Created",
infotags as "Tags"
FROM ""
WHERE contains(project,"obsidian")
GROUP BY type
SORT file.ctime asc 
```


# [[25.01.23]]
- Issue with links  having a space behind them and then not showing up even when fixed may be a folder note issue
- Found a trailing blankspace in the project creation template
	- Realized the issue only affected projects
# [[14.12.22]]
## Talked on the obsidian academia discord channel about syncing pdf annotations with tablet
My process is for android (Boox Max Lumi 2)

	Zotero does not have official support for Android (booooo) and the unofficial apps I have tried are more or less non-functional
    
    
    To get around this I sync my zotero library storage folder using Drivesync and google drive
    
    
    Whenever I wan to read a paper I have in my library, I must first find the title using my Zotero online library (in-browser) or possibly from the Obsidian citation note, and then search for the pdf using the file browser or pdf reader (edited)
    
    
    This also presumes you are using Zotfile to rename your PDFs to contain the title / authors / year
    
    
    Using your pdf reader of choice ( I have tested in Xodo and the Boox built-in Neoreader) you can add annotations as you normally would while reading (edited)
    
    
    These should auto-save and be synced back to your Zotero storage via Drivesync
    
    
    You then can open the pdf in Zotero on PC, which presumably is also synced through google drive ( I use Insync to ensure a saved copy of the file on my drive)
    
    
    Assuming all is synced and well, the annotations will be there and ready for export like normal (edited)
    

    
    Weak points: - woof - Syncing is often lagged in both directions - Requires multiple paid apps - Multiple steps to even find and open the paper you want to read - Can't export annotations directly to Obsidian on tablet, must be done on PC - Lots of setup in Zotero and sync apps (edited)
    

    
    Hopefully, Zotero will just release a decent android app and obviate all this. Honestly, it all feels sorta buggy and has a lot of friction.
    

    
    This is all part of an academic workflow / vault structure I hope to document and publish.... eventually.....

# [[15.06.22]]
Adding tab wrangler addon to keep track of metadata tags.
Ok so this doesn’t really work for my needs as it _only_ works for tags and in the metadata “infotags”does not count
- possibly consider renaming all instances of infotags to tags


Maybe do smarter Markdown at some point

---

