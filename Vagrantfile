Vagrant.configure("2") do |config|
  # Default network configuration
  config.vm.network "public_network"

  # Define VMs in a loop
  ["Jenkins-Master", "Jenkins-Slave"].each do |vm_name|
    config.vm.define vm_name do |vm|
      vm.vm.box = "bento/ubuntu-22.04"
      vm.vm.hostname = vm_name

      vm.vm.provider "virtualbox" do |vb|
        vb.memory = (vm_name == "Jenkins-Master") ? "2048" : "1024"
      end

      # Forward ports for Jenkins-Master
      if vm_name == "Jenkins-Master"
        vm.vm.network "forwarded_port", guest: 8080, host: 8080
        vm.vm.network "forwarded_port", guest: 50000, host: 50000
      end
    end
  end
end
