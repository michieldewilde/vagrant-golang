# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "puphpet/debian75-x64"

  # Configure A Private Network IP
  config.vm.network :private_network, ip: "192.168.10.10"

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  config.vm.network :forwarded_port, host: 8080, guest: 8080

  config.vm.provision :puppet do |puppet|
    puppet.environment      = "development"
    puppet.environment_path = "environments"
  end
end
