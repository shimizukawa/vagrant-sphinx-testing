# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu-12.04-x64"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  #Use this to upgrade chef version
  config.omnibus.chef_version = "latest"

  config.vm.provision :chef_solo do |chef|
    #chef.log_level = "debug"
    chef.cookbooks_path = ["site-cookbooks", "cookbooks"]
    chef.roles_path = "roles"
    chef.add_recipe "apt"
    chef.add_role "sphinx-testing"
    chef.add_role "shimizukawa"

    chef.json.merge!({
      :texlive => {
        #:dvd_url => '/vagrant/texlive2012-20120701.iso',
      },
    })
  end

end
