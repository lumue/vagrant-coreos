# -*- mode: ruby -*-
# vi: set ft=ruby :



Vagrant.configure(2) do |config|

  

  $update_channel = "stable"

  config.vm.box = "coreos-%s" % $update_channel
  config.vm.box_version = ">= 308.0.1"
  config.vm.box_url = "http://%s.release.core-os.net/amd64-usr/current/coreos_production_vagrant.json" % $update_channel
  config.vm.network "private_network",ip: "172.12.8.150"
  
  config.vm.provider "virtualbox" do |v|
     v.memory = 4096
     v.cpus = 2
  end

  # This will require sudo access when using "vagrant up"
#  config.vm.synced_folder ".", "/home/core/share",
#      id: "core",
#      :nfs => true,
#      :mount_options => ['nolock,vers=3,udp']
  
  # plugin conflict
  if Vagrant.has_plugin?("vagrant-vbguest") then
      config.vbguest.auto_update = false
  end
  
end
