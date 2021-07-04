# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "archlinux/archlinux"

  config.ssh.insert_key = false

  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.vm.provider :libvirt do |v|
    v.memory = 4096
  end

  # Laptop VM
  config.vm.define "laptop" do |app|
    app.vm.hostname = "laptop.test"
    app.vm.network :private_network, ip: "192.168.60.4"
  end

  # Ansible playbook
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "main.yml"
    ansible.compatibility_mode = "2.0"
  end
  # To run ansible: use the command `vagrant provision` in the shell
end
