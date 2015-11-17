# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.hostname = "scrapy-vm"
  
  config.ssh.forward_agent = true 
  
  config.vm.provider "virtualbox" do |vb|
    # We need at least this much for setup
    vb.memory = "1024"
    
    # Sets up internet connectivity for vagrant
    vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
  end

  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install -y build-essential libssl-dev libffi-dev python-dev python3-dev libxml2-dev libxslt1-dev git
    sudo apt-get install -y python-pip python3-pip
    pip install virtualenv 
    git clone https://github.com/PDX-Capstone-Team-C/scrapy.git 
  SHELL
end
