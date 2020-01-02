Vagrant.configure("2") do |config|
  config.vm.box = "generic/ubuntu1804"
  config.vm.hostname = "CMSandPipelineTool"
  config.vm.network "public_network", ip: "192.168.43.160", bridge: "wlan0"
  #config.vm.network "public_network", ip: "192.168.88.160", bridge: "wlan0"
  config.vm.network "forwarded_port", guest: 80, host: 8083
  config.vm.provider "virtualbox" do |vb|
  	 vb.gui = false
	 vb.memory = 1500
	 vb.cpus = 1

  end
  
  config.vm.provision :shell, :path => "preInstallAnsible.sh"
  config.vm.provision "file", source: "/home/devops/iitdocker/project/vagrant/cms/ansible/", destination: "$HOME/"
end
