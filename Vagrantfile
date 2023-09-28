# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.network "public_network"
  config.vm.box = "centos/7"
  config.vm.disk :disk, size: "5GB"
  config.vm.define "cent1" do |cent1|
    cent1.vm.hostname = "cent1"
    cent1.vm.provider "virtualbox" do |customize|
      customize.memory = 1024
      customize.cpus = 1
    end
    cent1.vm.provision "ansible" do |ansible|
      ansible.playbook = "main.yml"
    end
    cent1.vm.provision "shell", path: "update_kernel.sh"
  end
  config.vm.define "cent2" do |cent2|
    cent2.vm.hostname = "cent2"
    cent2.vm.provider "virtualbox" do |customize|
      customize.memory = 1024
      customize.cpus = 1
    end
  end
end
