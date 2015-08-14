# Tmux Config

## Tmux config file

Create a file under the home folder : `~/.tmux.conf`. And add some configuration inside. It will be loaded when you create a new tmux session.  
If not. You can load it in tmux command line `Prefix-:`

```tmux
source-file ~/.tmux.conf
```

You also can add a shortcut to reload it.

```tmux
# bind shortcut
bind r source-file ~/.tmux.conf

# bind shortcut and show message
bind r source-file ~/.tmux.conf \; display "Config file reloaded!"
```

**Trick**: Use a shortcut without the `Prefix`

```tmux
# Use -n as a parameter
bind-key​ -n C-r ​source-file​ ~/.tmux.conf
```

## Prefix shortcut update

```tmux
# Unbind default shortcut first
unbind C-b

# Set new shortcut
set -g prefix C-a
# Or
bind C-a send-prefix
```

## Basic config

```tmux
// set window & pane index from 1, then you can easily select 1-5 by left hand only
set -g base-index 1                    // window index start from 1
set -g pane-base-index 1               // pane index start from 1

// shorten the pending time after a Tmux command.
// Then you can back to control application instantly.
set -s escape-time 1
```



<fin>
