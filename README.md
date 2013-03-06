BePROUD redmine environment by using Vagrant+Chef
==================================================

QUICK procedure
----------------

### requirement

1. vagrant
2. virtualbox

### preparation

1. install `virtualbox` by installer.
2. install `vagrant` by installer.
3. `vagrant box add ubuntu-12.04-x64 http://files.vagrantup.com/precise64.box`

### up environment

1. `wget http://github.com/shimizukawa/vagrant-chef-bpredmine.tgz` **[TODO] make location on github**
2. `tgz zxf vagrant-chef-bpredmine.tgz`
3. `cd vagrant-chef-bpredmine`  **[TODO] Vagrantfile referer cookbook to http://anywhere/**
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

1. `git clone https://github.com/shimizukawa/vagrant-chef-bpredmine.git` **[TODO] make location on github**
2. `cd vagrant-chef-bpredmine`
3. `librarian-chef install`
4. `vagrant up`

