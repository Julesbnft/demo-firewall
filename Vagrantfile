Vagrant.configure("2") do |config|
  config.vm.box = "debian/bookworm64"

  # Machine serveur
  config.vm.define "server" do |server|
    server.vm.hostname = "server"
    server.vm.network "private_network", ip: "192.168.56.10"
    server.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
      vb.cpus = 1
    end
  end

  # Machine client
  config.vm.define "client" do |client|
    client.vm.hostname = "client"
    client.vm.network "private_network", ip: "192.168.56.11"
    client.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
      vb.cpus = 1
    end
  end

  # Machine DMZ
  config.vm.define "dmz" do |dmz|
    dmz.vm.hostname = "dmz"
    dmz.vm.network "private_network", ip: "192.168.56.12"
    dmz.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
      vb.cpus = 1
    end
  end
end

