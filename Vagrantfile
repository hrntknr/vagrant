# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.box_check_update = false
  config.vm.network "public_network"
  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = "2048"
    vb.cpus = 2
    vb.customize ["modifyvm", :id, "--ioapic", "on"]
  end
  config.vm.provision "shell", privileged: false, inline: <<-SHELL
    curl -fsS https://raw.githubusercontent.com/hrntknr/dotfiles/master/install | sudo bash
    sudo chsh -s $(which zsh) vagrant
  SHELL
end
