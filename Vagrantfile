# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu-12.04-x64"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  #Use this to upgrade chef version
  config.omnibus.chef_version = "11.10.4"

  if ENV['VAGRANT_BOOT'].nil?
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
  elsif ENV['VAGRANT_BOOT'] == 'multi'
    config.vm.define :db do |cfg|
      cfg.vm.network :hostonly, "192.168.30.11"
      cfg.vm.host_name = "db"
  
      cfg.vm.provision :chef_solo do |chef|
        #chef.log_level = "debug"
        chef.cookbooks_path = "cookbooks"
        chef.roles_path = "roles"
        chef.data_bags_path = "data_bags"
  
        chef.add_role "common"
        chef.add_role "db"
      end
    end
  
    config.vm.define :redmine do |cfg|
      cfg.vm.network :hostonly, "192.168.30.10"
      cfg.vm.host_name = "redmine"
  
      cfg.vm.provision :chef_solo do |chef|
        #chef.log_level = "debug"
        chef.cookbooks_path = "cookbooks"
        chef.roles_path = "roles"
        chef.data_bags_path = "data_bags"
  
        chef.add_role "common"
        chef.add_role "redmine"
  
        chef.json.merge!({
          "rvm_redmine" => {
            "db" => {"hostname" => '192.168.30.11'},
            "url_subpath": "/",
          }
        })
      end
    end
  end

end
