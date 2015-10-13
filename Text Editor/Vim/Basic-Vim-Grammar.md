# Basic VIM Grammar


## Load file

```vim
:source /path/to/file.vim
```



## Condition


### Function return TRUE or FALSE

```
empty(string)
isdirectory("/path/to/directory/")
```


### Simple IF

```vim
if <condition>
	" do something when it is true
endif
```


### IF...ELSE

```vim
if <condition>
	" do something when it is true
else
	" do something when it is false
endif
```


### IF...ELSEIF...ELSE

```vim
if <condition 1>
	" do something when C1 is true
elseif <condition 2>
	" do something when C2 is true
else
	" do something when C1 & C2 is false
endif
```
