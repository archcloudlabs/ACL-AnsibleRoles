# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "archlinux/archlinux"
  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.vm.provider "libvirt" do |vb|
    vb.memory = "8192"
    #vb.disksize.size = "75GB"
  end

  config.vm.provision "shell", inline: <<-SHELL
      yes | pacman -S python3
  SHELL

  config.vm.provision "ansible" do |ansible|
    ansible.compatibility_mode = "2.0"
    ansible.playbook = "provisioning/playbook.yml"
    ansible.become = true
  end

end
