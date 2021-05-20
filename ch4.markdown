# Chapter 4: Manipulating Files and Directories Notes

## Command overview

* `cp`
* `mv`
* `mkdir`
* `rm`
* `ln` - create hard and symbolic links

## Wildcards aka globbing
Lets us select filenames based on patterns of characters

* `*` Matches any characters
* `?` Matches any single character
* `[chars]` Matches any character contained in this set
* `[!chars]` Matches any character not a member of this set
* `[[:class:]]` Matches any character that is a member of the specified class

### Commonly used character classes

* `[:alnum:]` - any alphanumeric character
* `[:alpha:]` - any alphabetic character
* `[:digit:]` - any numeral
* `[:lower:]` - any lowercase letter
* `[:upper:]` - any uppercase letter

## `mkdir`

mkdir can be used to create a single directory or any number of them like `mkdir dir1 dir2...dirn`.

## `cp`
Useful options
* `-a` - copy the files, directories, and attributes.
* `-i` - before overwriting existing file, prompt user for confirmation. Otherwise `cp` will silently overwrite
* `-r` - recursively copy directories and their contents. This option or `-a` is required when copying directories.
* `-u` - when copying files from one place to another, only copy files that don't exist or are newer than corresponding files in destination.
* `-v` - verbose messages as copy runs

## `mv`
`mv` is used for both file moving and renaming. `mv` has some of the same options as `cp` like `-i`, `-u`, and `-v`.

## `rm`
`rm` is used to delete files and directories. Be very careful when using in combination with `sudo` or wildcards. It's good practice to verify wildcards with `ls` before
running `rm` using that pattern.

### options
* `-i`
* `-r` - recursively delete directories. This must be specified to delete a directory.
* `-f` - ignore nonexistent files and do not prompt, will override `-i`. Use with care especially in combination with `sudo`
* `-v`

## `ln`
`ln` is used to create either hard or symbolic links. For example:
`ln <file> <link>` creates a hard link.

Alternatively `ln -s <item> <link>` creates a soft one. `<item>` can be a file or a directory.

Hard links have two distinctive limitations:
* A hard link cannot reference a file outside its own file system. This means it cannot reference a file on a different disk partition.
* A hard link cannot reference a directory.

A hard link is indistinguishable from the file, with no indication that it is a link unlike symbolic links.

Symbolic links can be broken if you delete the file but not the link. In many implementations the `ls` command will indicate broken symbolic links.

We can distinguish between the file and hard links using `ls -li` to see the inode number. If it matches that means they are the same file.

File operations on symbolic links are usually carried out on the links target, not the symbolic link itself. `rm` is an exception. When `rm` is used on a symbolic link
it just deletes the link and not the target.
