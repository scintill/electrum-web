Overview
========

.. contents:: Contents

.. _what_is_electrum:

What is Electrum?
-----------------

Electrum is an easy to use Bitcoin client. It protects you from losing
coins in a backup mistake or computer failure, because your wallet can
be recovered from a secret phrase that you can write on paper or learn
by heart. There is no waiting time when you start the client, because
it does not download the Bitcoin blockchain.

Electrum can operate without a network connection, and it doesn't depend
on a Web browser or central server. All integral components are open
source and the source code can be verified and inspected before usage.

Electrum is simple.
^^^^^^^^^^^^^^^^^^^

    "A designer knows he has achieved perfection not when there is
    nothing left to add, but when there is nothing left to take away."
    — Antoine de Saint-Exupéry

Keeping your Bitcoin wallet safe and secure should be effortless.
It should require little to no extraneous gadgetry. Requiring users to
own inkjet printers, USB sticks and CDs is a drag. Assuming access to
a power grid or the Internet also isn't ideal. Herding users into the
hands of third party companies who hold or otherwise exert influence
over user Bitcoin private key material is absurd. There should be no
hidden costs or complexity to using Bitcoin.

Electrum features a simple user interface, and a paper-wallet-friendly
"brainwallet" security system by default. Write down the 12-word mnemonic
code Electrum generates for you on a physical sheet of paper, keep the
paper hidden, and that's all you'll ever need to do. No gadgetry and
you don't have to trust anyone.

Even its visual interface is optional. You can do it all on the command
line.

Electrum is modular.
^^^^^^^^^^^^^^^^^^^^

    "The whole is more than the sum of its parts."
    — Aristotle

The reality is that most Bitcoin users don't want to or don't need to
keep copies of the full Bitcoin blockchain on each and every computer of
theirs, especially mobile phones. Electrum's client-server architecture
allows for role specialization: most users operate the Electrum client
("wallet"), and expert users may contribute resources to a federated
network of `hot-swappable <https://en.wikipedia.org/wiki/Hot_swapping>`
servers. The client and server are decoupled.

This enables Electrum to scale from being a Bitcoin thin client,
which runs nearly everywhere with minimal dependencies, to a full
Bitcoin node.

In addition, the Electrum codebase itself is extensible. Custom
functionality may be implemented via Python plugins.

Electrum is powerful.
^^^^^^^^^^^^^^^^^^^^^

Electrum is a deterministic mnemonic Bitcoin wallet designed with
modularity, simplicity and security in mind. It gives you the full power
of the Bitcoin blockchain, with built-in support for multisignature
transactions, offline transactions, raw transactions, proxies and custom
server selection.

If you have an advanced use case for Bitcoin or are looking for the
starting point of a custom payment integration, whether it's for a
website, an ecommerce store, Bitcoin exchange, or other, Electrum can
deliver a secure, private and extensible solution.

.. _installation:

Installation
------------

.. _on_windows:

Installing on Windows
^^^^^^^^^^^^^^^^^^^^^

Windows installation instructions go here.

.. _on_mac:

Installing on Mac OS/X
^^^^^^^^^^^^^^^^^^^^^^

Mac OS/X installation instructions go here.

.. _on_android:

Installing on Android
^^^^^^^^^^^^^^^^^^^^^

Android installation instructions go here.

.. _on_debian:

Installing on Debian/Ubuntu
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Debian/Ubuntu installation instructions go here.

.. _on_fedora:

Installing on Fedora
^^^^^^^^^^^^^^^^^^^^

Fedora, CentOS, RHEL installation instructions go here.

.. _on_opensuse:

Installing on OpenSUSE
^^^^^^^^^^^^^^^^^^^^^^

OpenSUSE installation instructions go here.

.. _on_arch_linux:

Installing on Arch Linux
^^^^^^^^^^^^^^^^^^^^^^^^

Electrum is available in the AUR.

.. _on_gentoo:

Installing on Gentoo
^^^^^^^^^^^^^^^^^^^^

Gentoo installation instructions go here.

.. _on_freebsd:

Installing on FreeBSD
^^^^^^^^^^^^^^^^^^^^^

FreeBSD installation instructions go here.

.. _from_source:

Installing From Source
^^^^^^^^^^^^^^^^^^^^^^

.. _requirements:

Requirements
""""""""""""

Runtime and build dependencies are required.

Runtime dependencies:

- `Python <http://www.python.org/download/releases/2.7/>` (2.5.x or higher, 3.x not supported)
- `python2-ecdsa <https://pypi.python.org/pypi/ecdsa>`
- `python2-pyqt4 <https://pypi.python.org/pypi/PyQt4>`
- `python2-sip <https://pypi.python.org/pypi/SIP>`
- `python2-slowaes <https://pypi.python.org/pypi/slowaes>`
- `qt4 <https://qt-project.org>`
- `sip <http://riverbankcomputing.co.uk/software/sip/intro>`

Build dependencies:

- `gettext <http://www.gnu.org/software/gettext/>`
- `python2-pycurl <https://pypi.python.org/pypi/pycurl>`
- `python2-setuptools <https://pypi.python.org/pypi/setuptools>`

Optional dependencies:

- `python2-zbar <https://pypi.python.org/pypi/zbar>`
- `zbar <http://zbar.sourceforge.net/>`

.. _downloading:

Downloading
"""""""""""

Download Electrum and (optionally) verify the sources:::

  curl -O https://download.electrum.org/Electrum-1.9.7.tar.gz
  curl -O https://download.electrum.org/Electrum-1.9.7.tar.gz.asc
  gpg --recv-keys 6694D8DE7BE8EE5631BED9502BD5824B7F9470E6 # ThomasV
  gpg -v Electrum-1.9.7.tar.gz.asc

.. _building:

Building
""""""""

Extract Electrum-1.9.7.tar.gz::

  echo 'Extracting source tarball...'
  tar xvzf Electrum-1.9.7.tar.gz

Electrum is not compatible with Python 3. If your machine's default
Python interpreter is python3, you can easily adjust Electrum's python
interpreter before starting the build process as follows:::

  echo 'Fixing Python version...'
  find Electrum-1.9.7 -type f -print0 | xargs -0 sed -i 's#/usr/bin/python#/usr/bin/python2#g'
  find Electrum-1.9.7 -type f -print0 | xargs -0 sed -i 's#/usr/bin/env python#/usr/bin/env python2#g'

To build::

  echo 'Building...'
  cd Electrum-1.9.7
  python mki18n.py
  pyrcc4 icons.qrc -o gui/qt/icons_rc.py
  python setup.py build

You're finished. Electrum is now ready to run:::

  ./electrum --help

Installing
""""""""""

If you wish to install Electrum globally:::

  echo 'Installing...'
  python setup.py install --optimize=1

  echo 'Updating desktop database...' # optional
  update-desktop-database -q          # optional
