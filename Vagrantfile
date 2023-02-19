# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  
  config.vm.define "master" do |master|
    master.vm.box = "ubuntu/focal64"
    master.vm.hostname = "master-ubuntu2004"
    master.vm.define "master_ubuntu2004"
    master.vm.network "private_network", ip: "192.168.56.101"

    master.vm.provider "virtualbox" do |vb|
      vb.name = "master_ubuntu2004"
      vb.memory = "2048"
    end

    master.vm.provision "ansible" do |ansible|
      ansible.playbook = "site.yml"
      ansible.inventory_path = "inventory/"
      ansible.host_key_checking = false
      ansible.limit = "vagrant"
    end
  end

end