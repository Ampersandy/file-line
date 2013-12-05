file-line - fork
=========
This fork of https://github.com/bogado/file-line is a vim plugin that enables opening files with \<file\>:\<line_no\>:\<col_no\> syntax. Vim will open the file on the specified line and column.

However, this fork does not delete the inital file-name passed in from the buffer list, as doing so prevents Vim from opening multiple files in new tabs with the '-p' flag.  If you need a clean buffer list, this plugin is not for you.

Sample use case: a code search for 'Thinger' returns:

src/exps/Exp.php:80:3 class Thinger extends Blah {
src/exps/Map.php:30:5 new Thinger();

This plugin will let you perform magic:

```
vim -p `codesearch Thinger | cut -f1,2 -d:`
```
-> a new tab opened to the specified line for each file returned.

In the future I'll add an updated command that also uniq's on filenames and only returns the first line number match.
