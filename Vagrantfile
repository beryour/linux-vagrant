class VagrantPlugins::ProviderVirtualBox::Action::Network
  def dhcp_server_matches_config?(dhcp_server, config)
    true
  end
end
Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/bionic64"
  config.vm.box_download_insecure=true
  config.vm.box_version = "1.0.282"
  config.vm.box_url = "https://vagrantcloud.com/hashicorp/bionic64"
  config.vm.network "private_network", type: "dhcp"
  config.vm.provision "shell", inline: <<-END
apt update
apt install -y apache2
cp -r /vagrant/webcontent/* /var/www/html/
echo "Machine provisioned at $(date)! Welcome!"
END
end
