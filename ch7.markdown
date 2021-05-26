# Chapter 7

## Command Overview
* `echo` - display a line of text

#### Expansion
ex `echo *` the shell sees `*` and expands it before the command is executed.

Arithmetic expansion: `$((expression))`. Only supports integers.

Brace expression ex `echo Number_{1..5}`.

Command Substitution: `echo $(ls)`.
Alternate syntax: `ls -l `which cp``.
