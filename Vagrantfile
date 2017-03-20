Vagrant.configure("2") do |config|
  config.vm.define "dev" do |dev|
    dev.vm.box = "ubuntu/trusty64"
    dev.vm.hostname = "dev"

    dev.vm.network :private_network, ip: "192.168.50.50"

    dev.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 1024]
      v.customize ["modifyvm", :id, "--name", "dev"]
    end
  end

  config.vm.define "prod" do |prod|
    prod.vm.box = "ubuntu/trusty64"
    prod.vm.hostname = "prod"
    prod.vm.network :private_network, ip: "192.168.50.100"

    prod.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 1024]
      v.customize ["modifyvm", :id, "--name", "prod"]
    end
  end
end