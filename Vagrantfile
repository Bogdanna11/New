# -*- mode: ruby -*- vi: set ft=ruby :




  Vagrant.configure("2") do|config|

    config.vm.define "app" do  |app|
           app.vm.box = "ubuntu/xenial64"



           app.vm.network "private_network", ip: "192.168.10.100"
           app.vm.provision "shell", inline: "./provision.sh"
           app.vm.synced_folder  "." , "/home/vagrant/app"
           app.vm.provision "shell", path:"./file.sh"
           app.vm.synced_folder ".", "/home/vagrant/app"
end
     config.vm.define "db" do |db|
            db.vm.box = "ubuntu/xenial64"
            db.vm.network "private_network", ip: "192.168.10.150"
      end


  end
