# Tmux Pane

## Shortcut config

```tmux
bind | split-window -h                 // -h horizontal
bind - split-window -v                 // -v vertical
```

## Switch pane

```tmux
bind h select-pane -L
bind j select-pane -D
bind k select-pane -U
bind l select-pane -R
```
