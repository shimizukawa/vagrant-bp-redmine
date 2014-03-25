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

requirement
------------

1. virtualbox 4.2.16 or later
2. vagrant 1.3.4 or later (1.3.3 is broken)
3. gcc (command line tools for Xcode)
4. some vagrant plugins: vagrant-berkshelf, vagrant-omnibus


preparation
------------

1. install `virtualbox` by installer.
2. install `vagrant` by installer.
3. install gcc by "command line tools for Xcode" installer.
4. install some plugins for vagrant


### plugin: vagrant-berkshelf

vagrant chef provisioning support tool, vagrant-berkshelf::

   $ vagrant plugin install vagrant-berkshelf

This installation requires `Command line tools for XCode`.


### plugin: vagrant-omnibus

If chef version provided in Vagrantfile, `vagrant-omnibus` plugin will update your chef version in the VM box::

   $ vagrant plugin install vagrant-omnibus


up environment
---------------

1. `git clone https://github.com/shimizukawa/vagrant-bp-redmine.git`
2. `cd vagrant-bp-bpredmine`
3. `vagrant up`

