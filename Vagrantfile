# -*- mode: ruby -*-
# vi: set ft=ruby :

CFG_TZ = "UTC"     # timezone, like US/Pacific, US/Eastern, UTC, Europe/Warsaw, etc.
CFG_IP = "10.254.254.150"   # private IP address

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "ubuntu/trusty64"
  config.vm.network :forwarded_port, guest: 6379, host: 6379
  config.vm.network :private_network, ip: CFG_IP

  config.vm.provider :virtualbox do |vbox|
    vbox.customize ["modifyvm", :id, "--memory", 256]
  end

  config.vm.provision :shell, :path => "init.sh"
end
