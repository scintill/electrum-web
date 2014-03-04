title: Cool Storage
prev: cold-storage
next: dice
---

#### Fedora 20 LXDE

```sh
# install VirtualBox
# download Fedora 20 LXDE
# configure VirtualBox Fedora 20 LXDE instance
# launch VirtualBox Fedora 20 LXDE instance
# update system and install VBoxLinuxAdditions
sudo yum update
sudo yum install gcc kernel-devel
# reboot
# mount VBox Guest Additions ISO from VBox menu
cd /run/media/live/VBOX*
sudo ./VBoxLinuxAdditions.run

# install Electrum dependencies
sudo yum install python-pip PyQt4
curl -k -O https://pypi.python.org/packages/source/s/slowaes/slowaes-0.1a1.tar.gz
tar xvzf slowaes-0.1a1.tar.gz
cd slowaes-0.1a1
sudo python setup.py install --optimize=1
sudo pip install https://download.electrum.org/Electrum-1.9.7.tar.gz#md5=5764f38d6e4bc287a577c8d16e797882
```

#### openSUSE 13.1 KDE

```sh
# install VirtualBox
# download openSUSE 13.1 KDE
# configure VirtualBox openSUSE 13.1 KDE instance
# launch VirtualBox openSUSE 13.1 KDE instance
# update system and install VBoxLinuxAdditions
sudo zypper update
sudo zypper install gcc kernel-desktop-devel make
```
