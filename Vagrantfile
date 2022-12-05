# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "ansible" do |ansible|
    #ansible.vm.box = "bento/rockylinux-9.0"
    #ansible.vm.box_version = "202207.20.0"
    ansible.vm.box = "generic/rocky9"
    ansible.vm.network "forwarded_port", guest: 9090, host: 9090

    ansible.vm.hostname = "ansible.local"

    ansible.vm.provider "virtualbox" do |v|
      v.memory = 2048
      v.cpus = 2
      v.default_nic_type = "virtio"
    end

    ansible.vm.provision "ansible",  playbook: "recipes/playbook.yml"
  end
end
