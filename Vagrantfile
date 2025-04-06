Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/jammy64"
  config.vm.network "private_network", type: "dhcp"

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y apache2
    echo "<h1>Hello, DevOps!</h1>" > /var/www/html/index.html
    systemctl enable apache2
    systemctl start apache2
  SHELL
end
