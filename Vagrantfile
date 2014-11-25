# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.provider :digital_ocean do | provider, override | 

    override.ssh.private_key_path = "~/.ssh/id_rsa"
    override.vm.box = "digital_ocean"
    override.vm.box_url = "https://github.com/smdahlen/vagrant-digitalocean/raw/master/box/digital_ocean.box"

    provider.token = "5c85191548dc2a47a2f381c8273b10c4e29e69ccbde29507e44ca51fe2c8072e"
    provider.image = "14.04 x64"
    provider.region = "sfo1"
    provider.size = "512mb"

  end

  config.vm.provision "bosh" do |config|

    config.manifest = nil

    config.full_stemcell_compatibility = true

    config.agent_infrastructure = "aws"
    config.agent_platform = "ubuntu"
    config.agent_configuration = {}

  end
end
