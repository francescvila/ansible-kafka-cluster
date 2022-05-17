VAGRANT_API_VERSION = "2"

Vagrant.configure(VAGRANT_API_VERSION) do |config|
  # Use the same key for each machine
  config.ssh.insert_key = false

  # Provision all VMs with the same cpu and memory config
  # Otherwise, specificy inside config.vm.define
  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
    v.cpus = 1
  end  

  # Kafka servers

  config.vm.define "kafka1" do |kafka1|
    kafka1.vm.box = "debian/buster64"
    kafka1.vm.hostname = "kafka1"
    kafka1.vm.network "private_network", ip: "192.168.60.51"
    kafka1.vm.provision "ansible" do |ansible|
      ansible.inventory_path = "inventories/vagrant"
      ansible.playbook = "main.yml"
    end
  end

  config.vm.define "kafka2" do |kafka2|
    kafka2.vm.box = "debian/buster64"
    kafka2.vm.hostname = "kafka2"
    kafka2.vm.network "private_network", ip: "192.168.60.52"
    kafka2.vm.provision "ansible" do |ansible|
      ansible.inventory_path = "inventories/vagrant"
      ansible.playbook = "main.yml"
    end
  end

  config.vm.define "kafka3" do |kafka3|
    kafka3.vm.box = "debian/buster64"
    kafka3.vm.hostname = "kafka3"
    kafka3.vm.network "private_network", ip: "192.168.60.53"
    kafka3.vm.provision "ansible" do |ansible|
      ansible.inventory_path = "inventories/vagrant"
      ansible.playbook = "main.yml"
    end
  end
end