# Searching in pdfs
## Manual
[pdfgrep - Manpage for 2.1.2]<iframe src="https://pdfgrep.org/doc.html" allow="fullscreen" allowfullscreen="" style="height: 100%; width: 100%; aspect-ratio: 1 / 1;"></iframe>

## Search stuff
``` 
pattern="fixed interval"
```
H
```
pdfgrep '$pattern' -irl -m 1 ~/Insync/m@tarlton.info/Google\ Drive/06.\ Zotero/storage/ > ~/Insync/m@tarlton.info/Google\ Drive/05.\ Obsidian/Obsidian/oslomet/50\ Reading/PDF\ Searches/$pattern.md
```

``` bash
pdfgrep '$pattern' -irl -m 1 ~/Insync/m@tarlton.info/Google\ Drive/06.\ Zotero/storage/ | pdfgrep -ic > ~/Insync/m@tarlton.info/Google\ Drive/05.\ Obsidian/Obsidian/oslomet/50\ Reading/PDF\ Searches/$pattern.md
```



```regex
[A-Z1-9]+/
```

```
cd Insync/m@tarlton.info/Google\ Drive/06.\ Zotero/storage  

pdfgrep 'pattern' *.pdf

pdfgrep --help                                                                                                                                                           
Usage: pdfgrep [OPTION]... PATTERN FILE...

Search for PATTERN in each FILE.
PATTERN is, by default, an extended regular expression.

Commonly used options:
 -i, --ignore-case              Ignore case distinctions
 -P, --pcre                     Use Perl compatible regular expressions (PCRE)
 -H, --with-filename            Print the file name for each match
 -h, --no-filename              Suppress the prefixing of file name on output
 -n, --page-number              Print page number with output lines
 -c, --count                    Print only a count of matches per file
     --color WHEN               Use colors for highlighting;
                                WHEN can be `always', `never' or `auto'
 -p, --page-count               Print only a count of matches per page
 -m, --max-count NUM            Stop reading after NUM matching lines (per file)
 -q, --quiet                    Suppress normal output
 -r, --recursive                Search directories recursively
 -R, --dereference-recursive    Likewise, but follow all symlinks
     --cache                    Use cache for faster operation
     --help                     Print this help
 -V, --version                  Show version information

The above list is only a selection of commonly used options. Please refer
to the man page for a complete list.

```


```dataview
LIST WHERE contains(file.folder, this.file.folder)
SORT file.cdate DESC
```
