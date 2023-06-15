Vagrant.configure("2") do |config|
  config.vm.define "ebpf"
  config.vm.box = "ebpf"
  config.vm.box_url = "https://cloud-images.ubuntu.com/jammy/current/jammy-server-cloudimg-amd64-vagrant.box"
  config.vm.hostname = "ebpf"
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update && apt-get upgrade -y
    apt-get install -y apt-transport-https ca-certificates curl clang llvm jq
    apt-get install -y libelf-dev libpcap-dev libbfd-dev binutils-dev build-essential make 
    apt-get install -y linux-tools-common linux-tools-5.15.0-41-generic bpfcc-tools
    apt-get install -y python3-pip
    git clone https://github.com/lizrice/learning-ebpf
  SHELL
end
