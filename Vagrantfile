# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.box = "centos/7"

  config.vm.provider "virtualbox" do |vbox, override|
    vbox.gui = false
    vbox.cpus = "2"
    vbox.memory = "4096"
  end

  config.vm.provider "libvirt" do |libvirt, override|
    libvirt.driver = "kvm"
    libvirt.storage_pool_name = "user"
    libvirt.cpus   = "2"
    libvirt.memory = "4096"
  end

  config.vm.define :server do |server|
    server.vm.hostname = "server.example.com"
    server.vm.network "private_network", ip: "192.168.121.150", auto_config: false
    server.vm.provision "shell", run: "always", inline: "nmcli dev connect eth1 && nmcli con modify 'Wired connection 1' ipv4.addresses 192.168.121.150/24 ipv4.gateway 192.168.121.1 ipv4.dns 192.168.121.1 ipv4.route-metric 105 ipv4.method manual && nmcli con up 'Wired connection 1'"
    server.vm.provision "shell", path: "scripts/default-provision"
  end

end
