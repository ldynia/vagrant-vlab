Vagrant.configure('2') do |config|

  # Enabling  X-Forwarding
  config.ssh.forward_x11 = true
  config.ssh.forward_agent = true
  config.ssh.insert_key = false

  # Config Files
  config.vm.box = 'centos/7'

  config.vm.provider 'virtualbox' do |vb|
    vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
  end

  config.vm.define 'master' do |node1|
    node1.vm.provider 'virtualbox' do |vm|
      vm.cpus = 2
      vm.memory = 2048
      vm.name = 'node1'
    end
    node1.vm.hostname = 'node1'
    node1.vm.network "private_network", ip: '192.168.123.130'
  end

  config.vm.define 'worker' do |node2|
    node2.vm.provider 'virtualbox' do |vm|
      vm.cpus = 2
      vm.memory = 2048
      vm.name = 'node2'
    end
    node2.vm.hostname = 'node2'
    node2.vm.network "private_network", ip: '192.168.123.131'
  end

end
