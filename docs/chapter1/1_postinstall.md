# Post Installation

## Gnome tweak

```
sudo dnf install gnome-tweaks
```

## Install VS code Editor

``` bash linenums="1"
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" | sudo tee /etc/yum.repos.d/vscode.repo > /dev/null
```

```
dnf check-update
sudo dnf install code
```

## Install NERD Fonts
Download or install the Nerd Fonts with the Nerd Fonts Installer script. To install Nerd Fonts, run the following script.

```
bash -c  "$(curl -fsSL https://raw.githubusercontent.com/officialrajdeepsingh/nerd-fonts-installer/main/install.sh)"
```

## Install python3

```
sudo dnf install python3 pyhon3-pip python3-devel
```

## Install NodeJs
```
sudo dnf install nodejs
```

## Install Arduino IDE2

![](../assets/images/fedora41_arduino2.png)

[https://flathub.org/apps/cc.arduino.IDE2](https://flathub.org/apps/cc.arduino.IDE2)

```
sudo pip3 install pyserial
sudo usermod -aG dialout sysadmin
```

## Arduino Esp32 Git core

[https://docs.espressif.com/projects/arduino-esp32/en/latest/installing.html](https://docs.espressif.com/projects/arduino-esp32/en/latest/installing.html)

```
https://espressif.github.io/arduino-esp32/package_esp32_index.json
```
- copy link to arduino ide preference

![](../assets/images/fedora41_arduino_esp32core.png)

## KVM and Vagrant

```
egrep -c '(vmx|svm)' /proc/cpuinfo
sudo dnf install @virtualization

sudo dnf install qemu-kvm libvirt libvirt-client virt-top virt-install virt-manager virt-viewer libguestfs-tools

sudo dnf install libvirt libvirt-daemon-kvm qemu-kvm virt-manager guestfs-browser libguestfs-tools python-libguestfs virt-top virt-install bridge-utils virt-viewer
```

```
sudo systemctl start libvirtd
sudo systemctl enable libvirtd 
sudo virsh list --all 
```

```
sudo dnf install vagrant
vagrant plugin install vagrant-libvirt
vagrant box add generic/centos9s
```

## Install Thai Language Fonts

```
sudo dnf install tlwg-*
sudo dnf install  google-noto-sans-thai-fonts ibm-plex-sans-thai-fonts thai-arundina-sans-fonts  thai-arundina-sans-mono-fonts thai-arundina-serif-fonts
```

[https://github.com/opendevbook/thai-font-collection](https://github.com/opendevbook/thai-font-collection)

install windows fonts
```
sudo dnf install curl cabextract xorg-x11-font-utils fontconfig -y
sudo rpm -i https://downloads.sourceforge.net/project/mscorefonts2/rpms/msttcore-fonts-installer-2.6-1.noarch.rpm
```

## starship
[https://starship.rs/](https://starship.rs/)

```
curl -sS https://starship.rs/install.sh | sh 
```