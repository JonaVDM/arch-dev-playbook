# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "generic/arch"
  config.vm.synced_folder ".", "/vagrant_data", disabled: true
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "512"
  end

  config.ssh.username = 'vagrant'
  config.ssh.password = 'vagrant'

  config.vm.provision "py", type: "shell" do |s|
    s.inline = <<-SHELL
      pacman -S --noconfirm python
    SHELL
  end

  config.vm.provision "ans", type: "ansible" do |ansible|
    ansible.playbook = "main.yml"
  end
end
