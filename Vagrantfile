# -*- mode: ruby -*-
# vi: set ft=ruby :


$script = <<SCRIPT
sudo apt-get update
sudo apt-get install -y apache2
SCRIPT


Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.define "vm_apache" do |apache|
    apache.vm.hostname = "apache"
    apache.vm.network "private_network", ip: "10.0.0.155"
    apache.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
    end

    apache.vm.provision "shell", privileged: false, inline: $script
  end

end
