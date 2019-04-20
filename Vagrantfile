Vagrant.configure("2") do |config|
  # https://docs.vagrantup.com.
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "ubuntu/trusty64"
  config.vm.network "private_network", ip: "192.168.33.10"
  config.vm.synced_folder ".", "/vagrant"

  config.vm.provider "virtualbox" do |vb|
     vb.memory = "1024"
  end
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    curl -sL https://deb.nodesource.com/setup_11.x -o nodesource_setup.sh
    bash nodesource_setup.sh
    apt-get install nodejs
    nodejs -v
    npm -v
    apt-get install build-essential
  SHELL
end
