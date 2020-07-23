# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.env.enable 
  config.vm.define "server" do |server|
    server.vm.box = ENV['BOX_NAME']
    server.vm.hostname = ENV['MASTER_NAME']
    server.vm.network "private_network", ip: ENV['IP_SERVER'], netmask:"255.255.0.0"
    #server.vm.provision "shell", path: "general.sh"
    server.vm.provider :virtualbox do |vb|
      vb.customize [ 'modifyvm', :id, '--name', ENV['MASTER_NAME'] ]
      vb.customize [ 'modifyvm', :id, '--memory', ENV['MEMORY_SERVER'] ]
      vb.customize [ 'modifyvm', :id, '--cpus', ENV['CPUS'] ]
    end
  end

end 

 