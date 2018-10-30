
# This guide is optimized for Vagrant 1.7 and above.
# Although versions 1.6.x should behave very similarly, it is recommended
# to upgrade instead of disabling the requirement below.
Vagrant.require_version ">= 1.7.0"

Vagrant.configure(2) do |config|
 config.vm.define "web01" do |web01|
  
  web01.vm.box = "bento/ubuntu-16.04"
  
  # Disable the new default behavior introduced in Vagrant 1.7, to
  # ensure that all Vagrant machines will use the same SSH key pair.
  # See https://github.com/hashicorp/vagrant/issues/5005
  config.ssh.insert_key = false
  
  web01.vm.network "private_network", ip: "192.168.33.11"
  web01.vm.hostname = "web01"
  web01.ssh.forward_agent = true
  web01.ssh.port = 2222    
  web01.vm.synced_folder ".", "/vagrant"
  web01.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
  end
  
  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "playbook.yml"
  end
end
