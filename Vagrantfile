Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/bionic64"
    
    # Cambia a una IP estática en lugar de DHCP
    config.vm.network "private_network", ip: "192.168.56.10"
    
    config.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
      vb.cpus = 1
    end
  
    config.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y apache2
      echo "Hola Mundo desde Apache!" | sudo tee /var/www/html/index.html
    SHELL
  
    config.vm.synced_folder ".", "/var/www/html"
  end
  