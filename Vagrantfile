Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/jammy64"
  config.vm.synced_folder '.', '/vagrant', disabled: true

   config.vm.provider "virtualbox" do |vb|
     vb.gui = true
     vb.memory = "8192"
     vb.cpus = 2
     vb.customize ["modifyvm", :id, "--uartmode1","disconnected"]
     vb.customize ["modifyvm", :id, "--graphicscontroller","vmsvga"]

   end

  config.vm.provision "ansible" do |a|
    a.playbook="playbook.yml"
    a.verbose="v"
  end

end
