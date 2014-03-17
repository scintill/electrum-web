title: Documentation
next: setup
---

Before You Begin
----------------

This document will show you how to install Electrum on Windows, Mac,
Android, GNU/Linux and BSD platforms.

Installation
------------

*Documented version: 1.9.8*

#### Requirements

None.

#### Windows

#### Mac OS/X

#### Android

#### GNU/Linux

**Ubuntu 13.10**

With apt-get:

```bash
sudo apt-get install python-pip python-qt4 python-slowaes
sudo pip install pbkdf2
sudo pip install https://download.electrum.org/Electrum-1.9.8.tar.gz#md5=0d9896eddc7532813b29af0bf9010e7b
```

From GitHub source:

```bash
git clone https://github.com/spesmilo/electrum
```

**Fedora 20**

```bash
sudo yum install python-pip PyQt4
curl -k -O https://pypi.python.org/packages/source/s/slowaes/slowaes-0.1a1.tar.gz
tar xvzf slowaes-0.1a1.tar.gz
cd slowaes-0.1a1
sudo python setup.py install --optimize=1
sudo pip install pbkdf2
sudo pip install https://download.electrum.org/Electrum-1.9.8.tar.gz#md5=0d9896eddc7532813b29af0bf9010e7b
```

**openSUSE 13.1**

```bash
sudo zypper install python-pip python-qt4
curl -k -O https://pypi.python.org/packages/source/s/slowaes/slowaes-0.1a1.tar.gz
tar xvzf slowaes-0.1a1.tar.gz
cd slowaes-0.1a1
sudo python setup.py install --optimize=1
sudo pip install pbkdf2
sudo pip install https://download.electrum.org/Electrum-1.9.8.tar.gz#md5=0d9896eddc7532813b29af0bf9010e7b
```

**Arch**

Install from AUR: https://aur.archlinux.org/packages/electrum

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
for pkg in python2-ecdsa python2-pbkdf2 python2-slowaes electrum; do
  rm -rf $pkg ${pkg}.tar.gz && mkdir -p $pkg
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

#### BSD

**FreeBSD**

http://ftp.freebsd.org/pub/FreeBSD/ports/packages/Latest/electrum.tbz
