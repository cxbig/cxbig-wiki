# Jumping Host

## Config

```cnf
## ~/.ssh/config

Host jump-server
  Hostname jump-server.com
  IdentityFile ~/.ssh/id_rsa
  User cxbig

Host dest-server
  Hostname dest-server.com
  IdentityFile ~/.ssh/id_rsa
  User cxbig
  ProxyCommand ssh -W %h:%p jump-server
```
