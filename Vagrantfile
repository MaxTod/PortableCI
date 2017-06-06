# -*- mode: ruby -*-
# vi: set ft=ruby :

$script = <<SCRIPT

sudo apt-get update
sudo apt-get install apt-transport-https

SCRIPT

# Version(s) requise de Vagrant
Vagrant.require_version ">= 1.9.5"

# Configuration de la VM
Vagrant.configure("2") do |config|
# Temps en secondes que Vagrant attendra pour démarrer la machine et être accessible (300 par défaut)
  config.vm.boot_timeout = 180

# Temps en secondes que Vagrant attendra pour que la machine s'arrète proprement (60 par défaut)
  config.vm.graceful_halt_timeout = 120

# Box utilisée pour monter la VM, exemples de box : https://atlas.hashicorp.com/boxes/search
  config.vm.box = "ubuntu/trusty64"

# Version de la box utilisée
  config.vm.box_version = "20170602.0.0"

# Flag de vérification d'update de la box sur tout les vagrant up. true par défaut
  config.vm.box_check_update = false

# Nom de la machine. null par défaut
  config.vm.hostname = "PICVM"

# Message à afficher après le vagrant up
  config.vm.post_up_message = "VM named PICVM started !!"

# Network configuration
  config.vm.network "forwarded_port", guest: 80, host: 8080

# Configuration des providers pour Vagrant
  config.vm.provider "virtualbox" do |vb|
    vb.name = "portable-pic-box"
    vb.memory = "2048"
  end

  config.vm.provision "shell", inline: $script

end