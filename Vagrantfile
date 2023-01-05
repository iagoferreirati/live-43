Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.network "public_network"
  config.vm.synced_folder "./ansible", "/ansible"
  config.vm.provider "virtualbox" do |vb|
    vb.name = "servidor-web"
    vb.memory = "2048"
    vb.cpus = 2
  end
  config.vm.provision "shell", inline: <<-SHELL
    apt update
    apt install ansible -y
    ansible-playbook --connection=local /ansible/playbook.yml
  SHELL
end
