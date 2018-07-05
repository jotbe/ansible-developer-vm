# If you don't have to change anything about the base box, do not change this file.
# Rather change the playbook.yml in the directory provisioning.

Vagrant.configure("2") do |config|
  config.vm.box = "mpbauer/ubuntu1804-desktop"

  config.vm.provider "virtualbox" do |v|
    v.gui = true
  end

  config.vm.provider "vmware_desktop" do |v|
    v.gui = true
  end

  # This is the dev VM which is going to be provisioned. Only add basic stuff here!
  # Installation and configuration is to be done via playbook
  config.vm.define "devvm" do |devvm|
    devvm.vm.network :private_network, type: "dhcp"
    devvm.vm.hostname = "developmentVM"
  end

  # Run ansible playbook
  config.vm.provision :shell,
    privileged: true,
    path: "run-ansible-playbook.sh"

end