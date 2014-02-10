Vagrant.configure('2') do |config|
  config.vm.hostname = 'rails-dev-box'
  config.vm.network :forwarded_port, guest: 3000, host: 3000

  config.vm.provider :virtualbox do |v, vb|
    vb.vm.box      = 'precise32'
    vb.vm.box_url  = 'http://files.vagrantup.com/precise32.box'
  end

  config.vm.provider :parallels do |v, parallels|
    parallels.vm.box = 'devbox-201312'
    parallels.vm.box_url = 'https://s3-eu-west-1.amazonaws.com/vagrant-parallels/devbox-201312.box'
  end

  config.vm.provision :puppet do |puppet|
    puppet.manifests_path = 'puppet/manifests'
    puppet.module_path    = 'puppet/modules'
  end
end
