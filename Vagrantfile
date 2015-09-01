# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  #I'm using 14.04 because that's a supported Azure box and spark doesn't compile
  #  correctly on RHEL at the moment.
  config.vm.box = "hashicorp/precise64"
  #config.vm.provider "vmware_fusion" do |vm, override|
  #    vm.vmx["memsize"] = "4096"
  #    vm.vmx["numvcpus"] = "2"
  #end
  config.vm.customize ["modifyvm", :id, "--memory", 2048]
  config.vm.customize ["modifyvm", :id, "--cpus", 2]

  #Run the spark playbook to test deployment.
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "spark.yml"
  end
  #Forward ports for spark
  config.vm.network "forwarded_port", guest: 7077, host: 7077
  
end
