BePROUD redmine environment by using Vagrant+Chef
==================================================

QUICK procedure
----------------

This procedure not support upgrade path, but easy.

### requirement

1. vagrant
2. virtualbox

### preparation

1. install `virtualbox` by installer.
2. install `vagrant` by installer.
3. `vagrant box add ubuntu-12.04-x64 http://files.vagrantup.com/precise64.box`

### up environment

1. `wget https://github.com/shimizukawa/vagrant-bp-redmine/archive/master.zip`
2. `tar zxf vagrant-bp-redmine-master.zip`
3. `cd vagrant-bp-redmine-master`
4. `wget https://bitbucket.org/shimizukawa/stuffs/downloads/chef-coookbook-bpredmine-20130312.tgz`
2. `tar zxf chef-cookbook-bpredmine-20130312.tgz`
4. `vagrant up`


Recipe Development proceduer
-----------------------------

### requirement

1. vagrant
2. virtualbox
3. ruby/gem
4. librarian
6. git

### preparation

1. install `virtualbox` by installer.
2. install `vagrant` by installer.
3. `vagrant box add ubuntu-12.04-x64 http://files.vagrantup.com/precise64.box`
4. install `ruby` and `gem`
5. `gem install librarian`

### up environment

1. `git clone https://github.com/shimizukawa/vagrant-bp-redmine.git`
2. `cd vagrant-bp-bpredmine`
3. `librarian-chef install`
4. `vagrant up`

### upgrade environment

1. `cd vagrant-bp-redmine`
2. `librarian-chef update`
3. `vagrant provision`

