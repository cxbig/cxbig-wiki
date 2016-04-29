# VIM Configuration

## Line number
- `set number` or `set nu`
- `set relativenumber` or `set rnu`

### Line number combination

```vim
" Set 'rnu' before 'nu', you will see:
" - absolute line number for current line
" - relative line number for the other lines
" Vim v7.4 above
set rnu
set nu
```

## Syntax
- `syntax on`

## Ruler
- `set ruler`

## Disable backups & logs
- `set viminfo="NONE"`
- `set nobackup`

## list can listchars

Show all whitespace characters:
```vim
set list
```

Hide all whitespace characters:
```vim
set nolist
```

Define special characters:
```vim
set listchars=eol:¬,tab:»\ ,trail:*
```

Define special characters' color:
```vim
highlight SpecialKey ctermfg=256
highlight NonText ctermfg=256
```
