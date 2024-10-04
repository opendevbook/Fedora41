# Thingsboard Build

```
# -*- mode: ruby -*-
# vi: set ft=ruby :

$script = <<-EOF
  sudo dnf update -y
  sudo firewall-cmd --permanent --add-port=8080/tcp
  sudo firewall-cmd --permanent --add-port=1883/tcp 
  sudo firewall-cmd --permanent --add-port=5432/tcp 
  sudo firewall-cmd --permanent --add-port=80/tcp 
  sudo firewall-cmd --reload

  sudo dnf -y install java-17-openjdk java-17-openjdk-devel
  sudo dnf -y install maven 

  echo ">> Java Version: "
  sudo java --version 
EOF

Vagrant.configure("2") do |config|
  config.vm.box = "generic/centos9s"
  config.vm.network "private_network", ip: "192.168.33.10"

  config.vm.provider "libvirt" do |libvirt|
     libvirt.qemu_use_session = false
     libvirt.driver="kvm"
     libvirt.memory = "8192"
     libvirt.cpus = 4
  end
  config.vm.provision "shell", inline: $script
end
```

```
sudo alternaive --config java
export JAVA_HOME=/usr/lib/jvm/java-17-openjdk-17.0.11.0.9-2.el9.x86_64/
export PATH=$PATH:$JAVA_HOME/bin
```

```
git clone -b release-3.8 https://github.com/thingsboard/thingsboard.git--depth 1
```

```
sudo dnf module reset nodejs 
sudo dnf module -y enable nodejs:18 
sudo dnf module -y install nodejs:18/common
```

```
sudo npm install -g yarn
sudo npm install -g cross-env 
sudo npm install -g webpack

cd ui-ngx
yarn install 
yarn run build:prod

cd ..
mvn clean install -DskipTests
```