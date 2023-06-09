Vagrant.configure(2) do |config|
  config.vm.box = "centos/7"

  config.vm.provider "qemu" do |qe|
    qe.arch = "x86_64"
    qe.machine = "q35"
    qe.cpu = "qemu64"
    qe.net_device = "virtio-net-pci"
  end

  config.vm.network "forwarded_port", id: "ssh", guest: 22, host: 2222, auto_correct: true

end
