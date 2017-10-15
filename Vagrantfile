Vagrant.configure('2') do |config|
  config.vm.box = 'ubuntu-16.04-amd64'

  config.vm.hostname = 'sonarqube.example.com'

  config.vm.network :private_network, ip: '10.10.10.103'

  config.vm.provider :libvirt do |lv|
    lv.memory = 2048
    lv.cpus = 2
    lv.cpu_mode = 'host-passthrough'
    lv.keymap = 'pt'
  end

  config.vm.provider :virtualbox do |vb|
    vb.linked_clone = true
    vb.memory = 2048
    vb.cpus = 2
    vb.customize ['modifyvm', :id, '--cableconnected1', 'on']
  end

  config.vm.provision :shell, path: 'provision.sh'
end