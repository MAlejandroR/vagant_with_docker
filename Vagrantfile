# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|
    config.vm.box = "bento/ubuntu-22.04"
    # puertos host y máquina virtualizada
    #8080 lo usaremos para web
    config.vm.network :forwarded_port, host: 8080, guest: 80
    #33306 para acceder a mysql
    config.vm.network :forwarded_port, host: 33306, guest: 3306
    #8081 por si instalamos phpmyadmin y lo queremos dejar disponible en otro puerto
    config.vm.network :forwarded_port, host: 8081, guest: 8081

    config.vagrant.plugins = "vagrant-docker-compose"
    
    # Si queremos copiar  la carpeta  dentro de la máquina.
    # Para usar rsync, tiene que estar instalado en el host
    # https://learn.microsoft.com/en-us/windows/wsl/install

#     config.vm.provision "file", source: "./web", destination: "/home/vagrant/web"
    # config.vm.synced_folder "./web", "/home/vagrant/web", type: "rsync"  #, rsync__exclude: ".git/"
    # install docker and docker-compose
    config.vm.provision :docker
    config.vm.provision :docker_compose
    # config.vm.provision :shell, path: "provision.sh"    
    # config.ssh.forward_agent = true
  end
  