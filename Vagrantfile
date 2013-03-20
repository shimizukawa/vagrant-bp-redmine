# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|
  # config.vm.box_url = "http://files.vagrantup.com/precise64.box"
  config.vm.box = "ubuntu-12.04-x64"

  config.vm.forward_port 80, 8081
  config.vm.forward_port 3000, 3000

  config.vm.provision :chef_solo do |chef|
    #chef.log_level = "debug"
    chef.cookbooks_path = "cookbooks"
    chef.add_recipe "apt"
    chef.add_recipe "git"
    chef.add_recipe "mercurial"
    chef.add_recipe "openssl"  #need by mysql::server
    chef.add_recipe "mysql"
    chef.add_recipe "mysql::server"
    chef.add_recipe "rvm::vagrant"
    chef.add_recipe "bp-redmine"
    chef.add_recipe "bp-redmine::restructuredtext"

    chef.json.merge!({
      :mysql => {
        :server_root_password => "mysql",
        :server_repl_password => "mysql",
        :server_debian_password => "mysql",
      },
      :rvm => {
        :default_ruby => 'ruby-1.8.7-p371',
        #:user_default_ruby => 'ruby-1.8.7-p371',
        :gems => {
          'ruby-1.8.7-p371@redmine' => [
            {'name' => 'net-ldap'}, # TODO: page was not setup
          ],
        },
      },
      :rvm_redmine => {
        :rvm_name => 'ruby-1.8.7-p371@redmine',
        :dl_id => '76718',
        :name => 'redmine-1.4.7',
        #:user => 'www-data',
        #:group => 'www-data',
        :install_prefix => '/var/www/vhosts',
        :db => {
          :type => "mysql",
          :user => "root",
          :password => 'mysql',
        },
        :plugins => [
          #"git://github.com/suer/redmine_export_with_journals.git",
        ],
        :unicorn_port => '10080',
        :hostname => 'localhost',
        :hostname_aliases => ['127.0.0.1'],
      },
    })
  end

end
