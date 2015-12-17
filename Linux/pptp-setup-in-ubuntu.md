# PPTP setup in Ubuntu



## Install

```sh
sudo apt-get update
sudo apt-get upgrade -y
sudo apt-get install -y pptpd
sudo apt-get autoremove -y
```



## Setup IP range

Edit `/etc/pptpd.conf`

```conf
localip 10.0.0.1
remoteip 10.0.0.100-200
```

```sh
sed -i "s/#localip 192\.168\.0\.1/localip 10.0.0.1/;s/#remoteip 192\.168\.0\.234-238,192\.168\.0\.245/remoteip 10.0.0.100-200/" /etc/pptpd.conf
```



## Setup account

Edit `/etc/ppp/chap-secrets`

```ini
name1	pptpd	pass1	*
name2	pptpd	pass2	*
name3	*		pass3	*
```



## Setup PPTP DNS

Edit `/etc/ppp/pptpd-options`

```ini
ms-dns 8.8.8.8
ms-dns 8.8.4.4
```

```sh
#1
sed -i "s/^#ms-dns 10\.0\.0\.1/ms-dns 8.8.8.8/;s/^#ms-dns 10\.0\.0\.2/ms-dns 8.8.4.4/" /etc/ppp/pptpd-options
```



## Start PPTPD and check the status

```sh
# start service
sudo service pptpd restart

# check status
netstat -alpn | grep :1723
```



## Setup IP forward

1. Edit `/etc/sysctl.conf`

	```ini
net.ipv4.ip_forward=1
```

	```sh
sed -i "s/^#net\.ipv4\.ip_forward=1/net.ipv4.ip_forward=1/" /etc/sysctl.conf
```

2. Make it active

	```sh
sudo sysctl -p
```



## Setup Iptables

```sh
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE && iptables-save
```
