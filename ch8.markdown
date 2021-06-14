# Chapter 8 Advanced Keyboard Tactics

## Command Overview
* `clear` - clear terminal screen
* `history` - display or manipulate history list

## Cursor Movement
* `ctrl + a` - move to beginning of line
* `ctrl + e` - move to end of line
* `ctrl + f` - move cursor forward one character, same as right arrow key
* `ctrl + b` - move cursor backward one character
* `alt + f` - move cursor forward one word
* `alt + b` - move cursor back one word
* `ctrl + l` - clear the screen and move the cursor to the top left corner, same as `clear`

## Text Editing Commands
* `ctrl + d` - delete the character at the cursor location
* `ctrl + t` - Transpose (exchange) the character at the cursor location with the one preceding it.
* `alt + t` - Transpose the word at the cursor location with the one preceding it
* `alt + l` - convert the characters from the cursor location to the end of the word to lowercase.
* `alt + u` - convert the characters from the cursor location to the end of the word to uppercase.

## Cutting & Pasting (killing & yanking)
* `ctrl + k` - kill text from the cursor location to the end of line.
* `ctrl + u` - kill the text from the cursor location to the beginning of the line.
* `alt + d` - kill text from the cursor location to the end of the current word.
* `alt + backspace` - kill text from the cursor location to the beginning of the current word. 
					  if the cursor is at the beginning of a word, kill the previous word.
* `ctrl + y` - yank text from the kill-ring and insert it at the cursor location.

## Completion Commands
* `alt + ?` - display list of possible completions, on most systems you can do this by pressing tab twice, which is usually easier.
* `alt + *` - insert all possible completions. this is useful when you want to use more than one possible match.


### Programmable Completion
Use `set | less` to see system info about it.


### History
By default `bash` stores the last 500 commands we have entered, though most distributions set this to 1,000.
History expansion `!<num from history>`. You can incrementally search the history using `ctrl + r`. When you
find the desired result you can press `enter` to to execute the command or press `ctrl + j` to copy the line from
the history list to the current command line. To find the next occurence press `ctrl + r` again. To quit searching,
press either `ctrl + g` or `ctrl + c`.

### History Commands
* `alt + <` - move to the beginning (top) of the history list
* `alt + >` - move to the end (bottom) of the history list, the current command line
* `alt + p` - reverse search - nonincremental, type in search string and press enter before search.
* `alt + n` - forward search non-incremental.
* `ctrl-o` - execute the current item in the history list and advance to the next one. handy for reexecuting a sequence of commands

### History Expansion Commands
* `!!` - repeat the last command
* `!number` - repeat history list item number.

use caution when using these last two unless you are absolutely sure of the contents of the history list items.
* `!string` - repeat last history list item starting with string.
* `!?string` - repeat last history list item containing string.

### Script
`script file` to record an entire shell session and store it in the specified file.
