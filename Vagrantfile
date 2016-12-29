# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
SERVER_IP = "192.168.3.10"
Vagrant.configure("2") do |config|

  config.vm.box = "debian/jessie64"
  config.vm.box_check_update = false
  
  config.vm.define "openvpn-server" do |server|
    server.vm.hostname = "openvpn-server"
    server.vm.network "private_network", ip: SERVER_IP
    server.vm.provision "ansible" do |ansible|
      ansible.playbook =  "provision/openvpn-server.yml"
    end
  end
end
