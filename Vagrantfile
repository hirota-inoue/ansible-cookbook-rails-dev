VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.define :web do |node|
    node.vm.box = "bento/centos-6.7"
    node.vm.hostname = "dev-centos"
    node.vm.network :private_network, ip: "192.168.33.20"
    node.vm.network :forwarded_port, guest: 3000, host: 8080
    node.ssh.forward_agent = true

    node.vm.provider :vitualbox do |vb|
      vb.memory = 1024
      vb.cpus = 2
      vb.name = "ansible-centos"
    end

    node.vm.provision :ansible do |ansible|
      ansible.playbook = "playbook/site.yml"
      ansible.inventory_path = "playbook/hosts"
      ansible.limit = "all"
      ansible.verbose = "v"
    end

    if Vagrant.has_plugin?("vagrant-cachier")
      node.cache.scope = :box
    end
  end
end
