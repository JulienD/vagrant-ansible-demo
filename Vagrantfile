# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "Precise64 "

  config.vm.hostname = "vagrant"

  config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  #config.vm.synced_folder "public_html", "/home/vagrant/public_html", nfs: true

  config.vm.network :private_network, ip: "192.168.2.40"

  config.vm.provider :virtualbox do |vb|
     vb.customize ["modifyvm", :id, "--memory", "1024"]
  end

  # Provision via ansible
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
    ansible.inventory_path = "provisioning/ansible_hosts"
    ansible.verbose = "v"
  end
  
end
