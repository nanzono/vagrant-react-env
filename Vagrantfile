# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-18.04"
  config.vm.network :private_network, ip: "192.168.33.33"
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
  end
  config.vm.provision "shell", inline: <<-EOT
  apt update -y
  apt install -y nodejs npm git
  cd /usr/local
  git clone git://github.com/creationix/nvm.git nvm
  source /usr/local/nvm/nvm.sh
  echo 'source /usr/local/nvm/nvm.sh' >> /etc/profile.d/nvm.sh
  nvm install v11.10.1
  nvm use v11.10.1
  npm install -g npx
  npm install -g create-react-app
  EOT
end
