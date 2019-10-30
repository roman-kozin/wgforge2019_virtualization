# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-18.04"
  config.vm.hostname = "wgforge2019"

  config.vm.network "forwarded_port", guest: 80, host: 80, protocol: "tcp"
  config.vm.network "forwarded_port", guest: 443, host: 443, protocol: "tcp"
  config.vm.network "forwarded_port", guest: 5900, host: 5900, protocol: "tcp"

  config.vm.box_check_update = false

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.cpus = 2
    vb.memory = "2048"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible/playbook.yaml"
    ansible.verbose = "v"
    ansible.raw_arguments = [ '--diff' ]
  end
end
