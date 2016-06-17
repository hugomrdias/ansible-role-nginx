# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "debian/jessie64"
  config.vm.hostname = "nginx.local"
  config.vm.network "private_network", ip: "192.168.11.20"

  config.vm.provision 'ansible' do |ansible|
    ansible.playbook = 'tests/test.yml'
    ansible.inventory_path = 'tests/inventory'
    ansible.limit = 'vagrant'
    ansible.sudo = true
  end
end
