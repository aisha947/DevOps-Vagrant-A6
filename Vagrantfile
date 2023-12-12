Vagrant.configure("2") do |config|
    # Default network configuration
    config.vm.network "public_network"
  
    # VM1: Jenkins-Master
    config.vm.define "Jenkins-Master" do |master|
      master.vm.box = "bento/ubuntu-22.04"
      master.vm.network "forwarded_port", guest: 8080, host: 8080
      master.vm.network "forwarded_port", guest: 50000, host: 50000
      master.vm.hostname = "Jenkins-Master"
  
      master.vm.provider "virtualbox" do |vb|
        vb.memory = "2048"
      end
    end
  
    # VM2: Jenkins-Slave
    config.vm.define "Jenkins-Slave" do |slave|
      slave.vm.box = "bento/ubuntu-22.04"
      slave.vm.hostname = "Jenkins-Slave"
  
      slave.vm.provider "virtualbox" do |vb|
        vb.memory = "1024"
      end
    end
  end
  