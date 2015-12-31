# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/trusty64"
  config.vm.hostname = "hemr-backend"
  config.vm.network "private_network", ip: "192.168.33.22"

  config.vm.synced_folder "./app", "/home/vagrant/hemr_backend"

  config.vm.provision :shell, path: "./vagrant-setup/mysql-setup.sh"
  config.vm.provision :shell, path: "./vagrant-setup/install-rvm.sh", args: "stable", privileged: false
  config.vm.provision :shell, path: "./vagrant-setup/install-ruby.sh", args: "1.9.3", privileged: false
  config.vm.provision :shell, path: "./vagrant-setup/install-ruby.sh", args: "2.2.3 rails haml", privileged: false
  config.vm.provision :shell, path: "./vagrant-setup/install-git.sh", privileged: false

end
