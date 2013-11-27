file-line - fork
=========

Plugin for vim to enabling opening a file in a given line, this plugin avoids deleting the previous listed buffers such that it's possible to use vim -p to open multiple files at once. This is extremely useful when using grep search for code samples.

E.g., a code search for Thinger returns:

src/exps/Exp.php:80:3 class Thinger extends Blah {
src/exps/Map.php:30:5 new Thinger();

This enables piping the output like so:

vim -p `codesearch Thinger | cut -f1,2 -d:`
