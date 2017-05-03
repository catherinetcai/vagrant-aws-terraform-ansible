# -*- mode: ruby -*-
# # vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/xenial64"
  config.ssh.insert_key = true

  config.vm.provider :virtualbox do |v|
    v.name = "terraform"
    v.memory = 512
    v.cpus = 1 
  end

  config.vm.hostname = "terraform"
  config.vm.network :private_network, type: "dhcp"

  # Set the name of the VM
  config.vm.define :terraform do |terraform|
  end

  config.vm.provision "ansible_local" do |ansible|
    ansible.verbose = 'vvvv'
    ansible.playbook = "provision/playbook.yml"
    ansible.sudo = true
  end
end
