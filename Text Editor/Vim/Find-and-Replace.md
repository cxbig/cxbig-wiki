# VIM find and replace

## Find

## Find a string

```vim
:/<find_string>
```

Using `n` and `N` to navigate between finds

## Replace

### Simple find and replace

```vim
:s/<find_string>/<replace_string>/
```

### Find and replace all

```vim
:s/<find_string>/<replace_string>/g
```

### Find and replace a range

```vim
:5,10s/<find_string>/<replace_string/g
```

### Find and replace two range

```vim
:5,10s/<find_string>/<replace_string/g | :15,20&&
```

### Find and replace many ranges

```vim
:for range in split('5,10 15,20 100,200 ...') | exe range 's/<find_string>/<replace_string/g' | endfor
```


<fin>
