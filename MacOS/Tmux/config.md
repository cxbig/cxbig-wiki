# Tmux Config

## Tmux config file

Create a file under the home folder : `~/.tmux.conf`. And add some configuration inside. It will be loaded when you create a new tmux session.  
If not. You can load it in tmux command line `Prefix-:`

```
source-file ~/.tmux.conf
```

## Prefix shortcut update

```
unbind C-b
set -g prefix C-a
```

## Basic config

```
// set window & pane index from 1, then you can easily select 1-5 by left hand only
set -g base-index 1                    // window index start from 1
set -g pane-base-index 1               // pane index start from 1

// shorten the pending time after a Tmux command.
// Then you can back to control application instantly.
set -s escape-time 1

```



<fin>
