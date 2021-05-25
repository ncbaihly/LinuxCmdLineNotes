# Chapter 6 Redirection

## Commands
* `cat` - concatenate files
* `sort` - sort lines of text
* `uniq` - report or omit repeated lines
* `grep` - print lines matching a pattern
* `wc` - print newline, word, and byte counts for each file
* `head` - output first part of a file
* `tail` - output last part of a file
* `tee` - read from standard input and write to standard output and files

## Redirecting Standard output
* `>` - redirect output
* `>>` - redirect output but append, not overwrite

Redirection always rewrites target before attempting, so even on failure target file will be rewritten. Also allows us to create files like `> file-name`.

We can also use file descriptors to choose what to redirect.

#### File Descriptors
* stdin - 0
* stdout - 1
* sterr - 2

ex `2>`

Also can redirect to file descriptor like stderr to stdout like `2>&1`. Keep in mind order of redirection matters.
More modern systems can use `&>`. Can combine with append `&>>`.

We can redirect output to `/dev/null` if we want to suppress output.

Difference between `>` and `|`, the redirection operator connects a command with a file and the pipeline operator connects the ouput of one command
with the input of a second command.

The redirection operator should be treated with respect since it silently overwrites files.
