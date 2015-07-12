# Vagrantfile

`Vagrantfile` is the core configuration for a Vagrant VM instance.  
Basically, it is under root folder. It's created after initialize.  
`Vagrantfile` is a ruby script

## Initialize config (Single VM)

```ruby
Vagrant.configure(2) do |config|
  config.vm.box = "hashicorp/precise64"
end
```

## Multiple VM config

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

## SSH config

```ruby
Vagrant.configure(2) do |config|
  config.ssh.username = "cxbig"
  config.ssh.password = "P@ssw0rd"
end
```

## Port(s) forward

```ruby
Vagrant.configure(2) do |config|
  # Standard configuration
  config.vm.network "forwarded_port", guest: 80, host: 8080

  # We can add a parameter for forwarded_port to avoid port collisions
  config.vm.network "forwarded_port", guest: 80, host: 8080, auto_correct: true
end
```

## Provider: Virtual Box config

```ruby
Vagrant.configure(2) do |config|
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"      # unit is MB
    vb.cpus = 2             # core number
    vb.name = 'puppet'      # the name of the VM
    vb.gui = true           # true or false, show GUI window when startup
  end
end
```
