# Mac OS Port

## Which application is using port X

### Idea

1. Show which process is using port X
	- `sudo lsof -i :X`
	- `sudo lsof -i :80`
2. Use pipe sed get process ID
	- `| sed -E 's/^[^ ]* +([0-9]*)[^0-9].*/\1/'`
3. Sort & Uniq
	- `| uniq | sort`
4. Use ps list all process ids
	- `ps -o pid,command -p <ids>`

### Code sample

```sh
# list pids and commands for the applications which are using the port 80
ps -o pid,command -p `sudo lsof -i :80 | sed -E 's/^[^ ]* +([0-9]*)[^0-9].*/\1/'`
```
