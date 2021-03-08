Vagrant.configure("2") do |config|

  config.vm.define "master" do |master|
    master.vm.box = "ubuntu/focal64"
    master.vm.hostname = "ubuntu-k8s-master"
    master.vm.network "private_network", ip: "192.168.33.10"
    master.vm.network "public_network", ip: "192.168.3.100", bridge: "en0: Wi-Fi (Wireless)"
    master.vm.provider "virtualbox" do |vb|
      vb.memory = "8192"
      vb.name = "k8s-master"
    end
    master.vm.provision "file", source: "labs/LFD259", destination: "$HOME"
  end

  config.vm.define "worker" do |worker|
    worker.vm.box = "ubuntu/focal64"
    worker.vm.hostname = "ubuntu-k8s-worker"
    worker.vm.network "private_network", ip: "192.168.33.11"
    worker.vm.network "public_network", ip: "192.168.3.101", bridge: "en0: Wi-Fi (Wireless)"
    worker.vm.provider "virtualbox" do |vb|
      vb.memory = "8192"
      vb.name = "k8s-worker"
    end
    worker.vm.provision "file", source: "labs/LFD259", destination: "$HOME"
  end

end
