# Linux User


## Add new user

```sh
# Ubuntu
sudo adduser <user_name>          # add a new user
sudo adduser <user_name> sudo     # add a new user and add s/he to sudo group
```

## Add user to sudo group

```sh
# Ubuntu
sudo usermod -a -G sudo <user_name>
sudo usermod <user_name> -G sudo
```



## Non-password sudoer

### Ubuntu way

* Start to edit visudo file

```sh
# open sudo config file
sudo visudo
```

* Add a new line for a single user

```ini
user_name	ALL=(ALL) NOPASSWD:ALL
```

* Or give the whole sudo group the authority

```ini
# From
%sudo		ALL=(ALL) ALL

# To
%sudo		ALL=(ALL) NOPASSWD:ALL
```





<fin>
