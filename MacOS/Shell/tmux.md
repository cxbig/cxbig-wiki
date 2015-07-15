# Tmux

## start to use tmux

### Simple start

```sh
# By default, it will create a new session
tmux
```

### Special start

```sh
# start with a special session name
tmux new-session -s special_name

# attach an existing session
tmux attach -t existing_session_name
tmux a -t existing_session_name
```

### Check existing session(s)

```sh
tmux list-sessions
tmux ls
```

## Under the tmux mode

### tmux prefix short cut

Any tmux action should start with this prefix shortcut, all actions below will not mention again.

`<Ctrl> + <b>`


### core function

```
:			open tmux command line (like vim)
?			list all available commands
```

### tmux session

Tmux : mode

```
new -s new-session-name
```

Shortcuts

```
ctrl + d	no prefix ! close current session
d			with prefix ! detach current session
s			list all sessions and windows. can select anyone and jump to it
```

### tmux window

```
c			create a new window
&			close current window
w			list windows
,			change window name
p			previous window
n			next window
0-9			switch to the input number window
```

### tmux pane

```
%			split - vertical
"			split - horizontal
up, down, left, right
			switch to the pane on the direction
x			close current pane (with prompt)
q			display all pane number
```












<fin>
