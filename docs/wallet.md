Electrum Wallet Documentation
=============================

*preliminary outline*


What is Electrum?
-----------------

[High level overview of Electrum](https://github.com/ecdsa/electrum-web/wiki/What-is-Electrum%3F)


Getting Started: Installation and First Steps
---------------------------------------------

### Installation

*Installation on an online computer.*

- Windows
- Mac OS/X
- Ubuntu
- Fedora
- OpenSUSE
- Arch Linux
- Gentoo
- FreeBSD
- Android

### Installation: Secure Offline Method

*Installation on an offline computer, without connecting the offline
computer to the Internet*

- Windows
- Mac OS/X
- Ubuntu
- Fedora
- OpenSUSE
- Arch Linux
- Gentoo
- FreeBSD
- Android

### First Steps

*Wallet setup*

### Updating Electrum

*How to safely update Electrum.*

- Am I safe to install it over a previous version of Electrum?

### Updating Electrum: Secure Offline Method

*How to safely update Electrum on an offline machine.*


Usage
-----

### Desktop

- Creating a Wallet
- Restoring a Wallet
- Sending Coins
- Receiving Coins
- Setting a Password
- Adding a New Account (BIP0032 support)
- Uninstalling

### Android

- Creating a Wallet
- Restoring a Wallet
- Sending Coins
- Receiving Coins
- Setting a Password
- Adding a New Account (BIP0032 Support)
- Uninstalling

### Command Line

- Creating a Wallet
- Restoring a Wallet
- Creating, Signing and Sending Raw Transactions
- Prioritize / Freeze
- PayToMany
- Multisig / Escrow
- Various Handy Scripts

### terminal

F6=network, F11=settings, F9=quit

### stdio

docs

### Python Console

Generate new receiving addresses:

    wallet.accounts[0].create_new_address(0)

Generate new change addresses:

    wallet.accounts[0].create_new_address(1)

Save your changes:

    wallet.save_accounts()

Restart Electrum.

[result](http://i.imgur.com/gfOB4Cp.png)

Import individual watching-only addresses:

    wallet.storage.put( 'imported_keys', {'1933phfhK3ZgFQNLGSDXvqCn32k2buXY8a' : '',  '17ewBhK712mY2E4uPAbinThibdY2LRyabd' : '', '1FeexV6bAHb8ybZjqQMjJrcCrHGW9sb6uF' : '' } )


FAQ
---

* Who made Electrum, and what makes it special?
* What security measures does Electrum take to protect my coins?
* What does "Restore from seed" do? What *is* a seed?
* How do I make a paper wallet with Electrum?
* What makes Electrum brain wallets categorically safer than user-generated ones (e.g. bitaddress.org, brainwallet.org)?
* How do Bitcoin addresses work with Electrum? How can I generate new ones?
* Why does Electrum give me multiple Bitcoin addresses? Does each address link to my wallet? Is it safe to use these or should I generate my own?
* What are change addresses?
* Can I use Electrum to do X?
* Why does Electrum use 128 bits of entropy for its random seed generation? How can I increase it?
* Where can I receive support for any issues I encounter?


Troubleshooting
---------------

- Unconfirmed payments
- Syncing issues
- Sending issues (and all things 'Error Type -22')
- What to do if you're locked out of your wallet
  - if you lost the password...
  - if you lost the seedphrase...
  - if you lost both...
- Electrum Support Channels


Comparisons
-----------

- How does Electrum differ from Coinbase?
- How does Electrum differ from Bitstamp or MtGox?
- How does Electrum compare with online wallets?
  - Blockchain.info
  - CarbonWallet
  - Coinpunk
  - KryptoKit
- How does Electrum compare with native wallets?
  - Armory
  - Bitcoin-QT
  - Hive
  - Multibit
- How does Electrum compare with standalone paper wallet and brainwallet generators?
  - bitaddress.org
  - brainwallet.org
- How does Electrum compare with various Android wallets?
  - Blockchain.info
  - Coinbase
  - Mycelium
  - Schildbach's Bitcoin Wallet


Guides
------

- Brain Wallets Done Right: Highly Secure Paperless, Diskless Cold Storage
- Paper Wallet Guide
- Electrum Dice: Generate a Wallet Offline Without a Computerized RNG
- Offline Wallets & Offline Transactions Guide
- How to Restore Your Wallet From Seed
- Importing Bitcoin Private Keys from Other Wallets into Electrum
  - Blockchain.info
  - Bitcoin-QT
  - Armory
  - Multibit
  - Various Paper Wallets
- Cool Storage: Lubuntu VirtualBox on Windows
- Cool Storage: ArchBang VirtualBox on Windows
- Quick & Easy Cold Storage: Ubuntu LiveCD / LiveUSB
- Quick & Easy Cold Storage: ArchBang LiveCD / LiveUSB
- Advanced Cold Storage: Arch Linux with Lightweight Window Manager and BtrFS on LUKS
- Advanced Cold Storage: ArchBSD with Lightweight Window Manager and ZFS on GELI
- Everything Windoze
- Everything Mac OS/X
- Everything Android
- Everything iOS
- Electrum for Local Small Business
- Electrum for Ecommerce
- Additional Resources
