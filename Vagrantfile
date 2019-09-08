Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"

  # Add 4GB RAM
  config.vm.provider :virtualbox do |vb|
    vb.customize [
      "modifyvm", :id,
      "--name", "ucp",
      "--memory", "8192"
    ]
  end

  config.vm.hostname = "ucp"
  config.vm.network "private_network", ip: "192.168.5.134"
  config.vm.network "forwarded_port", guest: 443, host: 443

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "docker.yml"
  end

end
