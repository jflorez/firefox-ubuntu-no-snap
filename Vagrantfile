Vagrant.configure("2") do |config|
  config.vm.box = "jflorez/ubuntu-noble-desktop"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "4096"
    vb.cpus = 2
    vb.gui = true
  end

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "ubuntu-automation-playbook.yaml"
    ansible.limit = "all,localhost"
  end
end
