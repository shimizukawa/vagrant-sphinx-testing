# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|
  config.vm.box = "ubuntu-12.04-x86_64"

  config.vm.provision :chef_solo do |chef|
    #chef.log_level = "debug"
    chef.cookbooks_path = "cookbooks"
    chef.add_recipe "apt"
    chef.add_recipe "git"
    chef.add_recipe "texlive"
    chef.add_recipe "python-build"
    chef.add_recipe "mercurial-env"
    chef.add_recipe "shimizukawa-env"

    chef.json.merge!({
      :python_build => {
        :versions => %w(2.5.6 2.6.8 3.1.5 3.2.3 3.3.0 2.7.3),
        :packages => %w(pip tox virtualenv),
      },
      :mercurial_env => {
        'owner' => 'vagrant',
        'group' => 'vagrant',
        'hgrc' => {
          'username' => 'shimizukawa <shimizukawa@gmail.com>',
          'bb' => {'username' => 'shimizukawa'},
        },
      },
      :texlive => {
        #:dvd_url => '/vagrant/texlive2012-20120701.iso',
      },
    })
  end

end
