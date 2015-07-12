# Vagrant basic

## Links

- [Vagrant](https://www.vagrantup.com/)
- [Vagrant Documents](https://docs.vagrantup.com/v2/)
- [HashiCrop (Official box library)](https://atlas.hashicorp.com/)


## Commands


### Basic

```sh
# check vagrant version
vagrant -v
```

### Boxes

```sh
vagrant box add
vagrant box list
vagrant box outdated
vagrant box remove
vagrant box repackage
vagrant box update
```

### Start a new instance

```sh
# Create and goto a new folder
cd ~/Sites/vagrant/
mkdir ubuntu
cd ubuntu

# Initial vagrant instance
vagrant init hashicorp/precise64

# Start VM
vagrant up

```

### Plugins

- [Available Vagrant Plugins (Github)](https://github.com/mitchellh/vagrant/wiki/Available-Vagrant-Plugins)

```sh
# Install plugin
vagrant plugin install [plugin-name]
vagrant plugin install omnibus
vagrant plugin install vagrant-ansible-local
vagrant plugin install vagrant-docker-compose

# Install license
vagrant plugin license [license-name]

# List existing plugins
vagrant plugin list

vagrant plugin uninstall
vagrant plugin update
```

## Vagrantfile

See [Vagrantfile](vagrantfile.md)
