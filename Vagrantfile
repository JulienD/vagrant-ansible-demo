# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "Precise64 "

  config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  config.vm.synced_folder "public_html", "/home/vagrant/public_html"

  config.vm.network :private_network, ip: "192.168.2.40"

  config.vm.provider :virtualbox do |vb|
     vb.customize ["modifyvm", :id, "--memory", "512"]
  end

end
