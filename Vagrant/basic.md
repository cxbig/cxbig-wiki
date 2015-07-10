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

`Vagrantfile` is the core configuration for a Vagrant VM instance.  
Basically, it is under root folder. It's created after initialize.  
`Vagrantfile` is a ruby script

### Initialize config (Single VM)

```ruby
Vagrant.configure(2) do |config|
  config.vm.box = "hashicorp/precise64"
end
```

### Multiple VM config

```ruby
Vagrant.configure(2) do |config|
  config.vm.define "web" do |web|
    web.vm.box = "hashicorp/precise64"
  end
  config.vm.define "db" do |db|
    db.vm.box = "hashicorp/precise64"
  end
end
```

We also can define a primary VM

```ruby
Vagrant.configure(2) do |config|
  config.vm.define "web", primary: true do |web|
    web.vm.box = "hashicorp/precise64"
  end
  config.vm.define "db" do |db|
    db.vm.box = "hashicorp/precise64"
  end
end
```

And you can start up only one of these VMs by name.

```sh
vagrant up web
```

### SSH config

```ruby
Vagrant.configure(2) do |config|
  config.ssh.username = "cxbig"
  config.ssh.password = "P@ssw0rd"
end
```

### Provider: Virtual Box config

```ruby
Vagrant.configure(2) do |config|
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
    vb.cpus = 2
    vb.name = 'puppet'
  end
end
```
