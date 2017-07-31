# -*- mode: ruby -*-
# vi: set ft=ruby :

hosts = {
  "staging" => "192.168.33.10",
#  "db" => "192.168.33.11",
}

Vagrant.configure("2") do |config|
  hosts.each do |name, ip|
    config.vm.define name do |machine|
      machine.vm.box = "ubuntu/trusty64"
      machine.vm.hostname = "%s.wagtail-staging.org" % name
      machine.vm.network :private_network, ip: ip
      machine.vm.network :forwarded_port, guest:80, host: 80 
      machine.vm.provider "virtualbox" do |v|
          v.name = name
      end
    end
  end
end