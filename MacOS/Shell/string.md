# String in shell

## Basic

### Length

```sh
# Get string length
str_length=${#your_string}

# In condition, string in variable has length
[[ -n "$your_string"]]
```

### Simple substitution

```sh
### str='a/b/c'

# L->R, Keep right side of first match : `#`
${str#*/}    # => b/c
# L->R, Keep right side of last match : `##`
${str##*/}    # => c

# R->L, Keep left side of first match : `%`
${str%/*}    # => a/b
# R->L, Keep left side of last match : `%%`
${str%%/*}    # => a
```

We can use it to get file extension

```sh
file=test.txt
echo ${file##*.}    # => txt
```

