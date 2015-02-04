# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.define 'wordpress-php52', primary: true do |node|
    node.vm.box = 'tierra/wordpress-php52'
    node.vm.hostname = 'wordpress.local'
    node.vm.network :private_network, ip: '192.168.167.9'
    node.vm.provision "shell", path: "https://gist.githubusercontent.com/easterncoder/608bc255eab9a57cd204/raw/vagrant-tierra-wp-php52-vhost-alias-provisioner.sh"

    node.vm.provider :virtualbox do |vb|
      vb.customize [
        'modifyvm', :id,
        '--memory', '512',
      ]
    end
  end
end