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
d			detach current session
```

### tmux session


### tmux window

```
c			create a new window
,			change window name
p			previous window
n			next window
w			list windows
```

### tmux pane

```
%			vertical split
"			horizontal
```












<fin>
