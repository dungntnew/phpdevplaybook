# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "kirito/centos65"

  config.vm.box_check_update = false

  #config.vm.network "forwarded_port", guest: 8080, host: 8080
  config.vm.network "private_network", ip: "192.168.33.15"

  config.vm.synced_folder ".", "/home/vagrant/dev"
  # config.vm.synced_folder ".", "/vagrant", disabled: true
  # config.vm.synced_folder ".", "/home/vagrant/develop", nfs: true

  config.vm.provider "virtualbox" do |vb|
     vb.customize ["modifyvm", :id, "--memory", "1024"]
  end

  $script =<<-SCRIPT
     yum update -y
     yum install -y wget ansible gcc-c++
  SCRIPT

  config.vm.provision "shell", inline: $script
end
