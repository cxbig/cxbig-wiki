# Loop

## Simple for loop

```sh
#!/bin/bash
for i in __RANGE__; do
	# do something
done
```

## Loop lines with while

```sh
#!/bin/bash
while IFS='' read -r line || [[ -n "$line" ]]; do
    echo "Text read from file: $line"
done < __LINE_INPUT__

## OR pipe way
__CMD_OUTPUT_LINES__ | while IFS='' read -r line || [[ -n "$line" ]]; do
    echo "Text read from file: $line"
done
```