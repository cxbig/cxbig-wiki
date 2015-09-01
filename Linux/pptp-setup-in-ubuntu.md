# PPTP setup in Ubuntu


## Install

```sh
sudo apt-get install -y pptpd
```


## Setup IP range

- `/etc/pptpd.conf`

```
localip 10.0.0.1
remoteip 10.0.0.100-200
```

## Setup account

- `/etc/ppp/chap-secrets`

```ini
name1	pptpd	pass1	*
name2	pptpd	pass2	*
name3	*		pass3	*
```

## Setup DNS

- `/etc/ppp/pptpd-options`

```ini
ms-dns 8.8.8.8
ms-dns 8.8.4.4
```


## Start PPTPD and check the status

```sh
# start service
sudo service pptpd restart

# check status
netstat -alpn | grep :1723
```


## Setup IP forward

- `/etc/sysctl.conf`

```ini
net.ipv4.ip_forward=1
```

Make it active

```sh
sudo sysctl -p
```

## Setup Iptables

```sh
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE && iptables-save
```












<fin>
