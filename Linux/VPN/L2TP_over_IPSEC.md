# L2TP over IPSEC

## Install

[https://github.com/hwdsl2/setup-ipsec-vpn](https://github.com/hwdsl2/setup-ipsec-vpn)

## Configuration

## Restart

```sh
sudo service ipsec restart
sudo service xl2tpd restart
```


## Add new user

* `/etc/ppp/chap-secrets`

    ```
...
"USER_NAME"    l2tpd    "USER_PASS_PLAIN"    *
...
```

* `/etc/ipsec.d/passwd`

    ```
...
USER_NAME:USER_PASS_ENCRYPTED:xauth-psk
...
```

### Encrypt password

```sh
openssl passwd -1 'USER_PASS_PLAIN'
#=> USER_PASS_ENCRYPTED
```

