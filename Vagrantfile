
Vagrant.configure("2") do |config|
  
  config.vm.box = "ubuntu/bionic64"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
    vb.cpus = 2
  end

  config.vm.define "mysqlserver" do |mysqlserver|
    config.vm.network "forwarded_port", guest: 3306, host: 3306
    mysqlserver.vm.network "public_network", ip: "192.168.0.20"
    mysqlserver.vm.provider "virtualbox" do |vb|
      vb.name = "mysqlserver"
  end
    mysqlserver.vm.provision "shell", inline: "apt-get-update && apt-get install -y mysqlserver-5.7"
  end

end
