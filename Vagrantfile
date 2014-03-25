# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu-12.04-x64"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  #Use this to upgrade chef version
  config.omnibus.chef_version = "11.10.4"

  #Network
  config.vm.hostname = "redmine"
  config.vm.network :private_network, :ip => "192.168.30.10"

  config.vm.provision :chef_solo do |chef|
    #chef.log_level = "debug"
    #chef.cookbooks_path = ["site-cookbooks", "cookbooks"]
    chef.roles_path = "roles"
    chef.data_bags_path = "data_bags"

    chef.add_recipe "rvm::vagrant"
    chef.add_role "common"
    chef.add_role "db"
    chef.add_role "redmine"

    chef.json.merge!({
      "rvm_redmine" => {
        "db" => {"hostname" => '192.168.30.10'},
        "url_subpath" => "/",
      }
    })
  end

end
