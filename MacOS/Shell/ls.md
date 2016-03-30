# List file & folder command `ls`

_Mac OS based_

## Basic

```sh
ls
```

## Parameters

```sh
# List hidden files & folders
ls -a

# List mode
ls -l

# Size is human readable in list mode
ls -lh

# List with date descending order
ls -t

# List in one column (under non-list mode)
ls -1
```

## Tricks

### Get latest file

```sh
# 1. List with date descending, and one column
# 2. Get the first item
ls -t1 | head -n1
```

### Get file array without error

*Only for `ZSH`*

When trying to get a file array but no matches in scope, an error will be thrown:
```sh
for f (*.js); do echo $f; done
# => zsh: no matches found: *.js
```

Then just add `(.N)` at the end of the pattern to get an empty array if no matches:
```sh
for f (*.js(.N)); do echo $f; done
```
