# Vim - Plugin - Ctags

## Install

```sh
brew install ctags
```

## Generate `tags` file

### CLI

```sh
ctags -R
```

### Vim

```vim
:!ctags -R
```


## Search tag

```vim
:tag [my_tag]                           # search tag
```

### Jump

```vim
tn                                      # jump to the next one (after search)
tp                                      # jump to the previous one (after search)
ts                                      # list all
<C-]>                                   # jump to the source (when your cursor hovering on a method)
<C-^>                                   # jump back from source (when you jumped to a source)
```
