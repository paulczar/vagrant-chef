Vagrant::Config.run do |config|

  config.vm.define :chef do |chef_config|
    # TODO REMOVE THIS WHEN WE FORCE SMP MODE IN ERCHEF
    #chef_config.vm.customize ["modifyvm", :id, "--cpus", 2]
    chef_config.vm.customize ["modifyvm", :id, "--memory", 1024]
    chef_config.vm.host_name = "chef"
    chef_config.vm.box = "precise64"
    chef_config.vm.box_url = "https://opscode-vm.s3.amazonaws.com/vagrant/boxes/opscode-ubuntu-12.04.box"
    chef_config.vm.network :hostonly, "33.33.33.50"
    chef_config.ssh.max_tries = 40
    chef_config.ssh.timeout   = 120
    chef_config.ssh.forward_agent = true
    chef_config.vm.provision :shell, :path => "extras/install_chef_server.sh"
  end

  config.vm.define :node1 do |node1_config|
    node1_config.vm.host_name = "node1"
    #node1_config.vm.customize ["modifyvm", :id, "--cpus", 2]
    node1_config.vm.customize ["modifyvm", :id, "--memory", 512]
    node1_config.vm.box = "precise64"
    node1_config.vm.box_url = "https://opscode-vm.s3.amazonaws.com/vagrant/boxes/opscode-ubuntu-12.04.box"
    node1_config.vm.network :hostonly, "33.33.33.60"
    node1_config.ssh.max_tries = 40
    node1_config.ssh.timeout   = 120
    node1_config.ssh.forward_agent = true
    node1_config.vm.provision :shell, :path => "extras/install_chef_client.sh"
    node1_config.vm.provision :shell, :inline => "ifconfig eth2 promisc"
  end

end