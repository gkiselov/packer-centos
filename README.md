packer-centos v6 and v7
=======================

# Description

This is a simple packer script to build CentOS 6 and CentOS 7 Vagrant images for testing purposes.

## How to use it

## To build centos-6 and centos-7 image at ones, run:

```
packer build centos.json
```

## To build centos-6, run:

```
packer build -only=6 centos.json 
```

## To build centos-7, run:

```
packer build -only=7 centos.json 
```

## Register your new centos-6 image with Vagrant

```
vagrant box add centos-6 centos-6
```

## Register your new centos-7 image with Vagrant

```
vagrant box add centos-7 centos-7
```

## Vagrant file example if images are not registered to Vagrant (change the number with desire version):

```
# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "centos-7"
  config.vm.box_url = "./centos7.0.box"
end
````

## Vagrant file example if images are registered to Vagrant (change the number with desire version):

```
# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "centos-7"
end
````