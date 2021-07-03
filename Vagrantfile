#######################################################################
#Example vm creation with static description blocks
Vagrant.configure("2") do |config|
  config.ssh.insert_key = false
  config.vm.define "jenkins01" do |jenkins01|
    jenkins01.vm.box = "hashicorp/bionic64"
    jenkins01.vm.hostname = "jenkins01"
    jenkins01.vm.network "private_network", ip: "192.168.255.101"
    jenkins01.vm.network :forwarded_port, guest: 5240, host: 5240
    jenkins01.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--cpus", 2]
      v.customize ["modifyvm", :id, "--memory", "4096"]
      v.customize ["modifyvm", :id, "--name", "jenkins01"]
    end
  end
  config.vm.define "jenkins02" do |jenkins02|
    jenkins02.vm.box = "hashicorp/bionic64"
    jenkins02.vm.hostname = "jenkins02"
    jenkins02.vm.network "private_network", ip: "192.168.255.102"
    jenkins02.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--cpus", 2]
      v.customize ["modifyvm", :id, "--memory", "4096"]
      v.customize ["modifyvm", :id, "--name", "jenkins02"]
    end
  end
end
##############################################################################