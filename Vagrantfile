# -*- mode: ruby -*-
# vim: set ft=ruby :

Vagrant.configure("2") do |srv|
   srv.vm.box = "centos/7"
  
   srv.vm.provider "virtualbox" do |i|
    i.name = "vm"
    i.memory = "2048"
    i.cpus = 2
   end
   srv.vm.hostname = "vm" 
   srv.vm.network "private_network", ip: "192.168.56.10" 
   srv.vm.provision "shell", path: "update.sh"
   srv.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible/playbook.yaml"
    ansible.inventory_path = "ansible/hosts.ini"
    ansible.host_key_checking = "false"
    ansible.limit = "all"
   end
  end