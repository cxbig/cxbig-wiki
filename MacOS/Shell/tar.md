# Tar

## Package without compress

```sh
tar -cf items.tgz items
```

## Compress remote item and save to local

```sh
# basic
ssh user@host "tar -zcf - /path/to/folder_or_file" > /path/to/local.tgz

# under target folder
ssh user@host "tar -zcf - -C /path/to folders files" > /path/to/local.tgz
```
