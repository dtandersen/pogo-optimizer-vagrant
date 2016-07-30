# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.
  # config.vm.box = "terrywang/archlinux"
  config.vm.box = "ogarcia/archlinux-x64"
  config.vm.box_version = "2016.07.01"
  #config.vm.box = "archlinux-x86_64"
  #config.vm.box_url = "http://cloud.terry.im/vagrant/archlinux-x86_64.box"
  #config.vm.box_download_checksum = "a14db52ec1a64b5331e8fde51e1bc4b895d6189830354e96823c3de6b1c0530b"
  #config.vm.box_download_checksum_type = "sha256"

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "forwarded_port", guest: 3000, host: 3000
  config.vm.network "forwarded_port", guest: 8081, host: 8081

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    vb.gui = false
	vb.name = "Docker Host"
  #
  #   # Customize the amount of memory on the VM:
    vb.memory = 2048
	vb.cpus = 1
  end
  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Define a Vagrant Push strategy for pushing to Atlas. Other push strategies
  # such as FTP and Heroku are also available. See the documentation at
  # https://docs.vagrantup.com/v2/push/atlas.html for more information.
  # config.push.define "atlas" do |push|
  #   push.app = "YOUR_ATLAS_USERNAME/YOUR_APPLICATION_NAME"
  # end

  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
  config.vm.provision "shell", inline: <<-SHELL
	timedatectl set-local-rtc 1
	timedatectl set-timezone America/Los_Angeles
	pacman --noconfirm -Syu --ignore linux docker git
	cp /etc/iptables/empty.rules /etc/iptables/iptables.rules
	systemctl enable iptables
	systemctl start iptables
	systemctl enable docker
	systemctl start docker
	git clone -b v1.3.2 https://github.com/justinleewells/pogo-optimizer.git
	cd pogo-optimizer
	docker build -t pogo .
	docker run --restart=always -d -p 3000:3000 -p 8081:8081 -it pogo
  SHELL

end
