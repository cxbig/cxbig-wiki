# Vim - Config - Visual

## Scheme

### Basic scheme config

```vimrc
colorscheme desert
```


### List all available scheme

```vim
:colorscheme [Ctrl+d]
```

```
default   blue      darkblue  delek     desert    elflord   evening
industry  koehler   macvim    morning   murphy    pablo     peachpuff
ron       shine     slate     torte     zellner
```


### Extend scheme

Put all downloaded `*.vim` scheme under : `~/.vim/colors/`



## Color

### Config syntax

```
highlight [type] [key=value] ...
hi [type] [key=value] ...
```


### Teminal color

```vimrc
set t_CO=256                            " force terminal use 256 colors
```


### Element color keys

```
ctermfg                                 " terminal color
ctermbg                                 " terminal background color

guifg                                   " GUI color
guibg                                   " GUI background color
```



## Elements

### Fold column

_Fold Column is the left border of edit area (it's in the left side of line number)_

**Key : `foldcolumn`**

```vimrc
set foldcolumn=2                        " set fold column with 2 characters width
hi foldcolumn guibg=bg                  " set fold column background color as the same of edit area background
```


### Line Number

**Key : `LineNr`**

```vimrc
hi LineNr guifg=grey
```


### Line Space

```vimrc
set linespace=4                         " default : 0
```


### Scroll Bar

Hide scroll bar for both side always

```vimrc
set guioptions-=l
set guioptions-=L
set guioptions-=r
set guioptions-=R
```


### Split

**Vertical Key : `vertsplit`**

```vimrc
hi vertsplit guifg=gb guibg=yellow
```
