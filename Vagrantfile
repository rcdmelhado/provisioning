Vagrant.configure("2") do |config|

     # config.vm.box = "centos/7"
     config.vm.box = "ubuntu/focal64"

     config.vm.define "server" do |m|
          m.vm.network "private_network", ip: "172.17.177.42"
     end
  
     config.vm.provider "virtualbox" do |v|
          v.cpus = "2"
          v.memory = 1024
          v.customize ["modifyvm", :id, "--ioapic", "on"]
     end

    config.vm.provision "ansible" do |ansible|
          ansible.playbook = "provisioning.yaml"
     end

end