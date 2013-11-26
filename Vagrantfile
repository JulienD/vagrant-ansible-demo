# -*- mode: ruby -*-
# vi: set ft=ruby :

provision = true
# TODO fix name choice
project_name = "example"

Vagrant.configure("2") do |config|

  config.vm.box = "Precise64 "

  config.vm.hostname = project_name

  config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  config.vm.synced_folder "public_html", "/home/vagrant/public_html", nfs: true

  config.vm.network :private_network, ip: "192.168.2.40"

  config.vm.provider :virtualbox do |vb|
     vb.customize ["modifyvm", :id, "--memory", "1024"]
  end

  # Provision via ansible
  if provision
    config.vm.provision :ansible do |ansible|
      # Ansible playbook in project directory
      ansible.playbook = "provisioning/playbook.yml"    
      # If something goes wrong, you'll want Ansible to be more verbose.
      ansible.verbose = true
    end
  end
end
