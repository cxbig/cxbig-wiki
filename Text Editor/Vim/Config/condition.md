# Vim - Config - Condition

## Version check

### Check Vim version

```vim-command
:echo v:version
```

### Syntax

```vim
if v:version < 704
    " do something
endif
```

## File existing check

```vim
if filereadable(expand("~/.vim/bundle/Vundle.vim/README.md"))
    " do something
endif
```
