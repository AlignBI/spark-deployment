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
  #Run the spark playbook to test deployment.
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "spark.yml"
  end
  #Forward ports for spark
  config.vm.network "forwarded_port", guest: 7077, host: 7077

end
