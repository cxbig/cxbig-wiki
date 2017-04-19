# Self-Signed SSL Certification

## Generate command

```sh
sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout self-signed.key -out self-signed.crt
```

## Default certificate path for Ubuntu

_Or you can put them in where you want._

```
/etc/ssl/private/self-signed.key
/etc/ssl/certs/self-signed.crt
```
