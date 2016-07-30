# Vagrantfile for Pokémon GO Optimizer

## About

[Pokémon GO Optimizer](https://github.com/justinleewells/pogo-optimizer) is a proxy that intercepts traffic from the Pokémon GO app to discover the hidden IVs of Pokémon.

This Vagrantfile is used by Vagrant to set up an [Arch Linux](https://www.archlinux.org/) virtual machine (VM) on [VirtualBox](https://www.virtualbox.org/wiki/Downloads). The VM is automatically configured to run Pokémon GO Optimizer. This is probably the easiest way to get Pokémon GO Optimizer running if you aren't a software developer or sys admin.

## How to use

1. Download and install [Vagrant](https://www.vagrantup.com/). This also installs VirtualBox.
1. Open a shell (e.g. ```cmd```) and use git to clone this repository. (Windows) If you don't know how to install git try [TortoiseGit](https://tortoisegit.org/download/). It's a GUI for git.

        git clone https://github.com/dtandersen/pogo-optimizer-vagrant.git

1. Launch the virtual machine:

        cd pogo-optimizer-vagrant
        vagrant up

1. Wait for Vagrant to do its thing. Then go to [http://localhost:3000](http://localhost:3000) and verify that Pokémon GO Optimizer comes up.
1. Ensure that the firewall of the server has ports TCP/3000 and TCP/8081 open. To verify, connect to the server (e.g., http://192.168.0.100:3000) from your phone or another computer in the house. (Windows) Run ```ipconfig``` on the server to find the internal IP.
1. Follow the official instructions to [install the certificate on your phone](https://github.com/justinleewells/pogo-optimizer).
1. Go to https://www.google.com on your phone. If this works then you should be good to launch Pokémon GO.

## Tips

If you have multiple wifi networks, e.g., MyWifi and MyWifi_5G, configure MyWifi to use the proxy. Switch back to MyWifi_5G when finished with Pokémon GO.


## Legal

All product and company names are trademarks™ or registered® trademarks of their respective holders. Use of them does not imply any affiliation with or endorsement by them. 

I'm not responsible if your account get banned.
