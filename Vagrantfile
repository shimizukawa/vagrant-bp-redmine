# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|
  # config.vm.box_url = "http://files.vagrantup.com/precise64.box"
  config.vm.box = "ubuntu-12.04-x64"
  config.vm.network :hostonly, "192.168.30.10"
  config.vm.host_name = "redmine"

  config.vm.provision :chef_solo do |chef|
    #chef.log_level = "debug"
    chef.cookbooks_path = "cookbooks"
    chef.roles_path = "roles"
    chef.data_bags_path = "data_bags"

    chef.add_recipe "rvm::vagrant"
    chef.add_role "common"
    chef.add_role "db"
    chef.add_role "redmine"

    chef.json.merge!({
      "rvm_redmine" => {
        "db" => {"hostname" => '192.168.30.10'},
        "url_subpath": "/",
      }
    })
  end

end
