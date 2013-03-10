# -*- mode: ruby -*-
# vi: set ft=ruby :

hosts = {
  :host0 => "192.168.33.10",
  :host1 => "192.168.33.11", 
  :host2 => "192.168.33.12"
}

Vagrant::Config.run do |config|
  hosts.each do |name, ip|
    config.vm.define name do |machine|
      machine.vm.box = "precise32"
      machine.vm.box_url = "http://files.vagrantup.com/precise32.box"
      machine.vm.customize ["modifyvm", :id, "--memory", 200, "--name", name]
      machine.vm.host_name = "%s.example.org" % name.to_s
      machine.vm.network :hostonly, ip
    end
  end
end
