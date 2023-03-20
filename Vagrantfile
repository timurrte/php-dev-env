Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/focal64"
  
    config.vm.network "private_network", ip: "192.168.33.10"
  
    config.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
    end
  
    config.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y apache2 php libapache2-mod-php php-mysql php-xdebug
      rm -rf /var/www/html
      ln -fs /vagrant/code /var/www/html
      cp /vagrant/php.ini /etc/php/7.4/apache2/php.ini
    SHELL
  end