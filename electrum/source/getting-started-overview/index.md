title: Documentation
next: setup
---

Before You Begin
----------------

This document will show you how to install Electrum on Windows, Mac,
Android, GNU/Linux and FreeBSD platforms.

Installation
------------

#### Requirements

None. Zero extraneous software or hardware is required to use Electrum.

#### Windows

#### Mac OS/X

#### Android

#### GNU/Linux

**Ubuntu 13.10**

```bash
sudo apt-get install python-pip python-qt4 python-slowaes
sudo pip install https://download.electrum.org/Electrum-1.9.7.tar.gz#md5=5764f38d6e4bc287a577c8d16e797882
```

**Fedora 20**

```bash
sudo yum install python-pip PyQt4
curl -k -O https://pypi.python.org/packages/source/s/slowaes/slowaes-0.1a1.tar.gz
tar xvzf slowaes-0.1a1.tar.gz
cd slowaes-0.1a1
sudo python setup.py install --optimize=1
sudo pip install https://download.electrum.org/Electrum-1.9.7.tar.gz#md5=5764f38d6e4bc287a577c8d16e797882
```

**openSUSE 13.1**

```bash
sudo zypper install python-pip python-qt4
curl -k -O https://pypi.python.org/packages/source/s/slowaes/slowaes-0.1a1.tar.gz
tar xvzf slowaes-0.1a1.tar.gz
cd slowaes-0.1a1
sudo python setup.py install --optimize=1
sudo pip install https://download.electrum.org/Electrum-1.9.7.tar.gz#md5=5764f38d6e4bc287a577c8d16e797882
```

**Arch**

```bash
# with packer
packer -S electrum
```

```bash
# with yaourt
yaourt -S electrum
```

```bash
# manually
for pkg in python2-ecdsa python2-slowaes electrum; do
  curl -k -O https://aur.archlinux.org/packages/${pkg:0:2}/$pkg/$pkg.tar.gz
  tar -xvzf ${pkg}.tar.gz --strip 1 -C $pkg
  cd $pkg
  makepkg -Acsi --noconfirm
  cd ..
done
```

**Gentoo**

```bash
emerge electrum
```

#### FreeBSD

http://ftp.freebsd.org/pub/FreeBSD/ports/packages/Latest/electrum.tbz
