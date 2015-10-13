# VIM - Write file with sudo permission

It's annoying that when you open a file and made some changes, and then find that you have no permission to write.  
We have an alternative command to fix it.

```vim
:w !sudo tee %
```

Or, you can define a new command in `~/.vimrc` file

```vim
command W w !sudo tee % > /dev/null
```
