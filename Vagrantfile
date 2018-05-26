# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/xenial64"
  config.vm.hostname = "naodev"

  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "forwarded_port", guest: 3306, host: 3306
  config.vm.network "private_network", ip: "192.168.33.25"

  # Use "/" unstead of "\" to specify the path 
  # Exemple : D:/Documents/Code/NAO
  config.vm.synced_folder "D:/Documents/Code/NAO", "/vagrant"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
    vb.cpus = "1"
  end
  
  # Setup Basic Config
  config.vm.provision :shell, path: "bootstrap.sh"


end
