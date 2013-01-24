Sphinx testing environment by using Vagrant+Chef
==================================================

requirement
------------

1. vagrant
2. virtualbox
3. ruby/gem
4. librarian
5. git

preparation
------------

1. install `virtualbox` by installer.
2. install `vagrant` by installer.
3. install `ruby` and `gem`
4. `vagrant box add ubuntu-12.04-x86_64 http://dl.dropbox.com/u/1537815/precise64.box`
5. `gem install librarian`

up environment
---------------

1. `git clone https://github.com/shimizukawa/vagrant-sphinx-testing.git`
2. `cd vagrant-sphinx-testing`
3. `librarian-chef install`
4. `vagrant up`

use environment / test sphinx
------------------------------

1. `vagrant ssh`
2. `hg clone bb://birkenfeld/sphinx
3. `cd sphinx`
4. `tox`

