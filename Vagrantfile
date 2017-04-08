Vagrant.configure("2") do |config|

  config.vm.define "master" do |master|
    master.vm.box = "centos/7"


    master.vm.network "private_network", ip: "192.168.99.9",
      virtualbox__intnet: true
    master.vm.provision "shell", inline: "ifup eth1", run: "always"





  end
  config.vm.define "minion" do |minion|
    minion.vm.box = "centos/7"
    minion.vm.network "private_network", ip: "192.168.99.91",
      virtualbox__intnet: true
    minion.vm.provision "shell", inline: "ifup eth1", run: "always"

  end
end
