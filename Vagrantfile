VAGRANTFILE_API_VERSION = "2"
 
#Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
#  config.vm.box = "hashicorp/precise64"
#end

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"
  
  config.ssh.username = "vagrant"
  config.ssh.password = "vagrant"
  
  config.vm.provider "virtualbox" do |vb|
     vb.gui = true
  end
  
  #config.vm.hostname = "web.my.net"

  
  
  #config.vm.provision "shell",
  #  inline: "sudo bash -c 'echo \"deb https://get.docker.com/ubuntu docker main\" > /etc/apt/sources.list.d/docker.list' && sudo apt-get update && wget -qO- https://get.docker.com/ | sh" config.vm.provision "shell",
  #  inline: "sudo bash -c 'sudo apt-get remove docker"
  
  config.vm.provision "docker" do |d|
    d.run "tanzaho/ci-test-docker-vagrant",
      args: " -d -p 0.0.0.0:49153:8080"
  end
  
  config.vm.network :forwarded_port, host: 4567, guest: 49153


end
