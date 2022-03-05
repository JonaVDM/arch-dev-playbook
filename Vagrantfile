# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "archlinux/archlinux"
  config.vm.synced_folder ".", "/vagrant_data", disabled: true
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
    vb.gui = true
  end

  config.ssh.username = 'vagrant'
  config.ssh.password = 'vagrant'

  config.vm.provision "ans", type: "ansible" do |ansible|
    ansible.playbook = "main.yml"
  end
end
