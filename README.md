BePROUD redmine environment by using Vagrant+Chef
==================================================

Provided functionality
-------------------------

* Invoke redmine ready server with BePROUD settings (but not perfect).
  Apache, MySQL, unicorn, Redmine.

Server composition
-------------------------

* `Vagrantfile`: 1 server include all services.
* `Vagrantfile.multi`: 2 servers. ServerA: Redmine, Apache. ServerB MySQL.

URL and path
-------------------------

* Redmine Server named `redmine`: 192.168.30.10
* MySQL Server named `db`: 192.168.30.11

You can access to redmine with `http://192.168.30.10` by browser and
you can use redmine's default administrator account `admin` / `admin`.

If you want to change your virtual machines' IP address and redmine path,
these parameters are specified in `Vagrantfile` or `Vagrantfile.multi`.


Setup procedure
-------------------

### Normal procedure

#### requirement

1. vagrant
2. virtualbox
3. ruby/gem
4. librarian
6. git

#### preparation

1. install `virtualbox` by installer.
2. install `vagrant` by installer.
3. `vagrant box add ubuntu-12.04-x64 http://files.vagrantup.com/precise64.box`
4. install `ruby` and `gem`
5. `gem install librarian`

#### up environment

1. `git clone https://github.com/shimizukawa/vagrant-bp-redmine.git`
2. `cd vagrant-bp-bpredmine`
3. `librarian-chef install`
4. `vagrant up`

#### upgrade environment

1. `cd vagrant-bp-redmine`
2. `librarian-chef update`
3. `vagrant provision`
