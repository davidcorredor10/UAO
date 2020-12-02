Vagrant.configure("2") do |config|
config.vm.define :firewall do |firewall|
 firewall.vm.box = "bento/centos-7"
 firewall.vm.network :public_network, bridge: "TP-Link Wireless USB Adapter", ip: "192.168.1.54"
 firewall.vm.network :private_network, ip: "192.168.50.2"
firewall.vm.provision "shell", path: 'firewallscript.sh'
 firewall.vm.hostname = "firewall"
 end
config.vm.define :servidorSTRM do |servidorSTRM|
 servidorSTRM.vm.box = "bento/centos-7"
 #servidorSTRM.vm.network :public_network, bridge: "TP-Link Wireless USB Adapter", ip: "192.168.1.55"
 servidorSTRM.vm.network :private_network, ip: "192.168.50.3"
servidorSTRM.vm.provision "shell", path: 'ServidorSTREAMA.sh'
 servidorSTRM.vm.hostname = "servidorSTRM"
 servidorSTRM.vm.provision "file", source: "streama.service", destination: "/etc/systemd/system/streama.service"
servidorSTRM.vm.provision "shell", path: 'ServidorSTREAMA2.sh'
 end
end