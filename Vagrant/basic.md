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

## Vagrantfile

`Vagrantfile` is the core configuration for a Vagrant VM instance.  
Basically, it is under root folder. It's created after initialize.  
`Vagrantfile` is a ruby script

### Basic config after initialize

```ruby
Vagrant.configure(2) do |config|
  # ...
  config.vm.box = "hashicorp/precise64"
  # ...
end
```

### Basic virtual box provider config

```ruby
Vagrant.configure(2) do |config|
  # ...
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
    vb.cpus = 2
    vb.name = 'puppet'
  end
  # ...
end
```
