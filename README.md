Sphinx testing environment by using Vagrant+Chef
==================================================

requirement
------------

1. virtualbox 4.2.16 or later
2. vagrant 1.3.4
3. some vagrant plugins: vagrant-berkshelf, vagrant-omnibus

preparation
------------

1. install `virtualbox` by installer.
2. install `vagrant` by installer.
3. install some plugins for vagrant

### plugin: vagrant-berkshelf ###

vagrant chef provisioning support tool, vagrant-berkshelf::

   $ vagrant plugin install vagrant-berkshelf

This installation requires `Command line tools for XCode`.

### plugin: vagrant-omnibus ###

If chef version provided in Vagrantfile, `vagrant-omnibus` plugin will update your chef version in the VM box::

   $ vagrant plugin install vagrant-omnibus


up environment
---------------

1. `git clone https://github.com/shimizukawa/vagrant-sphinx-testing.git`
2. `cd vagrant-sphinx-testing`
3. `vagrant up`

tip: vagrant commands

* `vagrant up` - power on & provision
* `vagrant halt` - shutdown
* `vagrant destroy` - remove VM
* `vagrant provision` - update environment

use environment / test sphinx
------------------------------

1. `vagrant ssh`
2. `hg clone bb://birkenfeld/sphinx`
3. `cd sphinx`
4. `tox`

