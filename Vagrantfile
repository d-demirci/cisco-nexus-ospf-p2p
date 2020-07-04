# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.provider :libvirt do |lv|
    lv.memory = 6144
    lv.suspend_mode = "managedsave"
  end

  config.vm.box = "cisco-nexus9300v"

  config.vm.define "nx01" do |node|
    node.vm.provider :libvirt do |domain|
      # mgmt_ip: 192.168.121.31
      domain.management_network_mac = "52:54:00:00:00:31"
      domain.qemuargs :value => "-serial"
      domain.qemuargs :value => "telnet:127.0.0.1:52001,server,nowait"
    end
    node.vm.network :private_network,
      :libvirt__iface_name => "e1/1",
      :libvirt__tunnel_type => "udp",
      :libvirt__tunnel_local_ip => "127.1.1.1",
      :libvirt__tunnel_local_port => "10001",
      :libvirt__tunnel_ip => "127.1.2.1",
      :libvirt__tunnel_port => "10001",
      auto_config: false
    node.vm.network :private_network,
      :libvirt__iface_name => "e1/2",
      :libvirt__tunnel_type => "udp",
      :libvirt__tunnel_local_ip => "127.1.1.2",
      :libvirt__tunnel_local_port => "10001",
      :libvirt__tunnel_ip => "127.1.3.1",
      :libvirt__tunnel_port => "10001",
      auto_config: false
  end

  config.vm.define "nx02" do |node|
    node.vm.provider :libvirt do |domain|
      # mgmt_ip: 192.168.121.32
      domain.management_network_mac = "52:54:00:00:00:32"
      domain.qemuargs :value => "-serial"
      domain.qemuargs :value => "telnet:127.0.0.1:52002,server,nowait"
    end
    node.vm.network :private_network,
      :libvirt__iface_name => "e1/1",
      :libvirt__tunnel_type => "udp",
      :libvirt__tunnel_local_ip => "127.1.2.1",
      :libvirt__tunnel_local_port => "10001",
      :libvirt__tunnel_ip => "127.1.1.1",
      :libvirt__tunnel_port => "10001",
      auto_config: false
    node.vm.network :private_network,
      :libvirt__iface_name => "e1/2",
      :libvirt__tunnel_type => "udp",
      :libvirt__tunnel_local_ip => "127.1.2.2",
      :libvirt__tunnel_local_port => "10001",
      :libvirt__tunnel_ip => "127.1.3.2",
      :libvirt__tunnel_port => "10001",
      auto_config: false
  end

  config.vm.define "nx03" do |node|
    node.vm.provider :libvirt do |domain|
      # mgmt_ip: 192.168.121.33
      domain.management_network_mac = "52:54:00:00:00:33"
      domain.qemuargs :value => "-serial"
      domain.qemuargs :value => "telnet:127.0.0.1:52003,server,nowait"
    end
    node.vm.network :private_network,
      :libvirt__iface_name => "e1/1",
      :libvirt__tunnel_type => "udp",
      :libvirt__tunnel_local_ip => "127.1.3.1",
      :libvirt__tunnel_local_port => "10001",
      :libvirt__tunnel_ip => "127.1.1.2",
      :libvirt__tunnel_port => "10001",
      auto_config: false
    node.vm.network :private_network,
      :libvirt__iface_name => "e1/2",
      :libvirt__tunnel_type => "udp",
      :libvirt__tunnel_local_ip => "127.1.3.2",
      :libvirt__tunnel_local_port => "10001",
      :libvirt__tunnel_ip => "127.1.2.2",
      :libvirt__tunnel_port => "10001",
      auto_config: false
  end
end
