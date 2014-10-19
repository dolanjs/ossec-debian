# -*- mode: ruby -*-
# vi: set ft=ruby :
# Added snap.rb file holds the digital ocean api token values
# # so we do not accidently check them into git

Vagrant.configure("2") do |config|

  config.vm.define 'ossec-ubuntu', primary: true do |ossec_build|
    ossec_build.vm.hostname = "ossec-ubuntu"
    ossec_build.vm.box = "trusty64"
    ossec_build.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"
#    ossec-build.vm.provision "ansible" do |ansible|
#      ansible.playbook = "install_files/ansible-base/site.yml"
#      ansible.verbose = 'v'
#    end
    ossec_build.vm.provider "virtualbox" do |v|
      v.name = "ossec-ubuntu"
      v.memory = 1024
    end
  end

  # "Quick Start" config from https://github.com/fgrehm/vagrant-cachier#quick-start
  if Vagrant.has_plugin?("vagrant-cachier")
    config.cache.scope = :box
  end
end
