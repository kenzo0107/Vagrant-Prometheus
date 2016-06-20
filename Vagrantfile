# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure(2) do |config|

	config.vm.box = "centos6.5"
	config.vm.box_url = "https://github.com/2creatives/vagrant-centos/releases/download/v6.5.1/centos65-x86_64-20131205.box"

	config.vm.define "server" do |server|
		server.vm.network "private_network", ip: "192.168.33.30"
	end

	config.vm.define "client1" do |server|
		server.vm.network "private_network", ip: "192.168.33.31"
	end

	config.vm.define "client2" do |server|
		server.vm.network "private_network", ip: "192.168.33.32"
	end
end
