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

## Find & Loop
find . -type f -print0 | while IFS= read -r -d '' item; do
	echo "$item"
done
```
