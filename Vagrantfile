# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "archlinux/archlinux"
  config.vm.provider "libvirt" do |vb|
     vb.memory = "2048"
     vb.cpus = 2
   end

   config.vm.provision "shell", inline: <<-SHELL
        sudo pacman -Syy --noconfirm;
        sudo pacman -Syu --noconfirm;
        sudo pacman --noconfirm -S -y git vim \
            tmux dhcpcd dialog iwd firefox chromium \
            emacs git rsync i3-wm;
   SHELL
end
