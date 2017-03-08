# How to check a port

## Use `lsof`

```sh
# mac,
lsof -i :80

# ubuntu
sudo lsof -i :80
```

## Use `ss`


```sh
# ubuntu
sudo ss -nlp | grep :80
```

## Use `netstat`

```sh
# ubuntu
sudo netstat -peant | grep :80
```
