# Chapter 5 Notes - Working with commands

## Command overview
* `type` - indicate how a command is interpreted
* `which` - display which executable will be used. does not apply to builtins or aliases
* `help`
* `man`
* `apropos` - display a list of related commands
* `info` - display a commands info entry
* `whatis` - display single line manual page description
* `alias` - create an alias for an operation

## Commands

Commands can be one of four things.

* An executable program
* A command built into the shell - a shell builtin supported by bash, like `cd`
* A shell function
* An alias

A note on command notation: square brackets indicate optional items while vertical bar indicates mutually exclusive options.

On most Linux systems `less` is used to display man pages.

We can chain commands by ending them with a semicolon like so: `cd /usr; ls; cd -`.

## alias

`alias name=<string>`

can remove aliases with `unalias <alias>`.

One thing to note is that aliases created with alias command disappear when the session ends.
