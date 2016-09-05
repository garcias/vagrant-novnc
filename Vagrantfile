# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/trusty64"
  config.vm.network "private_network", ip: "10.0.12.222"
  config.ssh.forward_agent = true
  config.ssh.forward_x11 = true
  config.vm.provider :virtualbox do |v|
    v.name = "vagrant-novnc"
    v.memory = 1024
    v.cpus = 2
  end

  config.vm.provision "shell", privileged: false, inline: $SYSTEM_PREP
  config.vm.provision "shell", privileged: false, run: "always", inline: $SYSTEM_START

end

$SYSTEM_PREP = <<SCRIPT

# Update apt-get and install basic tools

sudo apt-get update -qq
sudo apt-get install -y xauth git curl

cd $HOME
git clone https://github.com/garcias/cloud9-vnc.git
cloud9-vnc/install.sh

SCRIPT

$SYSTEM_START = <<SCRIPT

cd $HOME/cloud9-vnc
./run.sh /vagrant/fluxbox.conf

SCRIPT
