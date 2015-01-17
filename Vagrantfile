Vagrant.configure("2") do |config|

  if Vagrant.has_plugin?("vagrant-cachier")
    config.cache.scope = :box
  end

  config.vm.define :main do |host|
    host.vm.box = "precise64"
    host.vm.box_url = "http://files.vagrantup.com/precise64.box"
    host.vm.hostname = "btsync"
    host.vm.network "private_network", ip: "192.168.33.15"

    host.vm.network :forwarded_port, guest: 8888, host: 8888
    host.vm.network :forwarded_port, guest: 5999, host: 5999

    host.vm.provider "virtualbox" do |v|
      v.name = "btsync"
      v.memory = 512
      v.cpus = 2
    end

    if Vagrant.has_plugin?("vagrant-vbguest")
      config.vbguest.auto_update = false
    end

    config.vm.provision "ansible" do |ansible|
        ansible.playbook = "playbook-vagrant.yml"
    end
  end
end

