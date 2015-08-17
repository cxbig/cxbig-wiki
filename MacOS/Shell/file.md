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
