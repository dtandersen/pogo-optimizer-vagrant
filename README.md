# Vagrantfile for Pokémon GO Optimizer

## About

[Pokémon GO Optimizer](https://github.com/justinleewells/pogo-optimizer) is a proxy that intercepts traffic from the Pokémon GO app to discover the hidden IVs of Pokémon.

This Vagrantfile sets up an [Arch Linux](https://www.archlinux.org/) virtual machine (VM) on [VirtualBox](https://www.virtualbox.org/wiki/Downloads). The VM is automatically configured to run Pokémon GO Optimizer. After it is complete Pokémon GO Optimizer is running at http://localhost:3000. 

## How to use

1. Use git to clone this repository:

        git clone https://github.com/dtandersen/pogo-optimizer-vagrant.git

1. Download and install [Vagrant](https://www.vagrantup.com/). This also installs VirtualBox.
1. Launch the virtual machine:

        vagrant up

1. Go to http://localhost:3000 to see if it is running.
1. Ensure that the firewall of the computer has ports TCP/3000 and TCP/8081 open.
1. Follow the directions to [install the certificate on your phone](https://github.com/justinleewells/pogo-optimizer).
