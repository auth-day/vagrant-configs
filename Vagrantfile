Vagrant.configure("2") do |config|

#  config.vm.network :public_network
#  config.vm.network :private_network, :ip =>  "10.0.5.6"
config.vm.box = "ubuntu/trusty64"
config.vm.define "iscsitarget" do |iscsitarget|
  iscsitarget.vm.provider "virtualbox" do |vb|
    vb.name = "VM NAME"
    unless File.exist?(file_to_disk)
      vb.customize ['createhd', '--filename', file_to_disk, '--variant', 'Fixed', '--size', 1 * 1024]
    end
    vb.memory = "512"
    vb.customize ['storageattach', "VM TEST",  '--storagectl', 'SATAController', '--port', 1, '--device', 0, '--type', 'hdd', '--medium', file_to_disk]
  end
end

end
