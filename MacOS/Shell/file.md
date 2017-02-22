# File in shell

## Basename, filename and extension

```sh
# file='/path/to/test.txt'

file_basename=$(basename "$file")
# => file_basename = test.txt

file_extension="${file_basename##*.}"
# => file_extension = txt

file_filename="${file_basename%.*}"
# => file_filename = test
```


## Get file line(s)

```sh
# Get file from line X
head -n X file_name

# Get last X line from a file
tail -n X file_name

# Get file line from X to Y (X <= Y) and sample from 5 to 20
## use sed
sed -n 'X,Yp' file_name
sed -n '5,20p' file_name
## use head & tail
head -n Y file_name | tail -n (Y-X)
head -n 20 file_name | tail -n 15
```

## General permission fixing

```sh
# Fix files permission to 644
find . -type f -exec chmod 644 {} \;

# Fix folders permission to 755
find . -type d -exec chmod 755 {} \;
```

## Get script path

```sh
# script absolute path
SCRIPT_PATH=$(readlink -f $0)

# script absolute directory
SCRIPT_DIR=`dirname $(readlink -f $0)
```

