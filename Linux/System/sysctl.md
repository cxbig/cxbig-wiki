# sysctl

## fs.inotify.max_user_watches

### Check current amount

```sh
cat /proc/sys/fs/inotify/max_user_watches
```

### Temporarily update

```sh
sysctl fs.inotify.max_user_watches=524288
sysctl -p
```

### Permenant change

```sh
echo fs.inotify.max_user_watches=524288 | tee -a /etc/sysctl.conf
sysctl -p
```