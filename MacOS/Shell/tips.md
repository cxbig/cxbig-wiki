# Shell tips

_updating_

## Tricks


### Run command in different folder

```sh
# 1. Use CD and command in one line, just add '&&' between them.
cd /path/to/folder/ && ls -a

# 2. Command above will change folder to destination and run LS command
#    If you want to do that but do not change folder, you can add a parenthesis:
(cd /path/to/folder/ && ls -a)
```


## Config

### Edit mode

Default mode is `emacs` Set mode command

```sh
set -o emacs    # switch to emacs mode
set -o vi       # switch to vim mode
set -o          # check current mode
```



## Shortcut `emacs` mode

### Cursor move & character

```
`CTRL` + `A`			// cursor move to first column
`CTRL` + `E`			// cursor move to last column

`CTRL` + `B`			// cursor move left
`CTRL` + `F`			// cursor move right

`CTRL` + `H`			// cursor move left, remove character

`CTRL` + `I`			// horizontal table

`CTRL` + `J`			// go to the new line, command in current line will be run

`CTRL` + `K`			// remove all content after the cursor
`CTRL` + `W`			// remove a word before the cursor
`CTRL` + `U`			// remove whole line (or before the cursor?)
`CTRL` + `Y`			// return the content which is removed by other shortcuts

`CTRL` + `T`			// exchange character under cursor and the one on its left

`CTRL` + `V`			// ?

`CTRL` + `xx`			// switch cursor between first column and current position
```

### Action

```
`CTRL` + `C`			// terminate action
`CTRL` + `D`			// remove the character under the cursor
						// if there is no character, close terminal
`CTRL` + `G`			// send an alert
`CTRL` + `L`			// clean the screen
`CTRL` + `H`			// carriage return

`CTRL` + `N`			// command history, next one
`CTRL` + `P`			// command history, previous one

`CTRL` + `O`			// create a new line <return>

`CTRL` + `S`			// suspend running command
`CTRL` + `Q`			// recover suspended command

`CTRL` + `R`			// find command in history

`CTRL` + `Z`			// suspend current process, back to command line (it seems you can do something else and pick that process back later.)

`CTRL` + `\`			// quit process. ?
`CTRL` + `/`			// ?
`CTRL` + `_`			// ?
```
