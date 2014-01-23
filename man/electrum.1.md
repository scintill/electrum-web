ELECTRUM 1.9.7 "JANUARY 2014" Linux "User Manuals"
==================================================

NAME
----

electrum - Bitcoin thin client ("wallet")

SYNOPSIS
--------

`electrum` [*options*] *command* [*args*] [*options*]  
`electrum` [`-w` *wallet* ] [`-p` *proxy* ] [`-s` *server* ] [`-g` *gui* ] *command* [`-1`] [`-o`] [`-C`]  
`electrum -v`

DESCRIPTION
-----------

`Electrum` is an easy to use Bitcoin wallet. It protects you from  
losing coins in a backup mistake or computer failure, because your  
wallet can be recovered from a secret phrase you can write on paper  
or learn by heart. There's no waiting time when you start Electrum,  
because it doesn't download the Bitcoin blockchain.

OPTIONS
-------

`-w` *path/to/wallet*, `--wallet`=*WALLET_PATH*

Load the wallet file *path/to/wallet* instead of the default,  
*~/.electrum/wallets/default_wallet*.

`-p` *type*:*host*:*port*, `--proxy`=*PROXY*

Use the proxy type:host:port to connect to an Electrum server,  
where type is either *socks4*, *socks5* or *http*.

`-s` *host:port:protocol*, `--server`=*SERVER*

Connect to the Electrum server at host:port, where protocol is either  
*t* (tcp), *h* (http), *s* (tcp+ssl), or *g* (https). Port should be  
8081 for http, 8082 for https, 50001 for tcp, or 50002 for ssl.

`-g` [*gui*], `--gui`=*GUI*

Use the selected GUI, where gui is either *qt*, *lite*, *gtk*, *text*  
or *stdio*. The default GUI is qt.

`-1`, `--oneserver`

Connect to one server only, useful when connecting to a private instance  
of electrum-server.

`-o`, `--offline`

Operate in offline mode, useful when no Internet connection is present.

`-C`, `--concealed`

Don't echo seed to console, useful when restoring from seed on  
untrusted hosts.

`-h`, `--help`

Display help and exit.

`-v`, `--verbose`

Verbose mode. Shows debugging information.

COMMANDS
--------

`contacts`: Show your list of contacts.

  $ electrum contacts

`create`: Create a new wallet.

  $ electrum create

`createmultisig`: Create a multisignature transaction.

  $ electrum createmultisig ...

`createrawtransaction`: Create a raw transaction.

  $ electrum createrawtransaction ...

`decoderawtransaction`: Decode a raw transaction.

  $ electrum decoderawtransaction ...

`deseed`: Remove seed from wallet, creating a seedless, watching-only wallet.

  $ electrum deseed

`dumpprivkey`: Dump private key for specified address.

  $ electrum dumpprivkey *ADDRESS*

`dumpprivkeys`: Dump all private keys.

  $ electrum dumpprivkeys

`freeze`: Freeze the funds at one of your wallet's addresses.

  $ electrum freeze *ADDRESS*

`getaddressbalance`: Return the balance of an address.

  $ electrum getaddressbalance *ADDRESS*

`getaddresshistory`: Return the transaction history of a wallet address.

  $ electrum getaddresshistory *ADDRESS*

`getbalance`: Return the balance of your wallet, or of one account.

  $ electrum getbalance *ACCOUNT*

`getconfig`: Return a configuration variable.

  $ electrum getconfig *NAME*

`getmpk`: Return your wallet's master public key.

  $ electrum getmpk

`getpubkeys`: Return the pubkeys for a wallet address.

  $ electrum getpubkeys *ADDRESS*

`getrawtransaction`: Retrieve a transaction.

  $ electrum getrawtransaction *TX_HASH* *HEIGHT*

`getseed`: Print the generation seed of your wallet.

  $ electrum getseed

`getservers`: Return the list of available servers.

  $ electrum getservers

`getversion`: Return the version of your Electrum client.

  $ electrum getversion

`help`: Print help message.

  $ electrum help

`history`: Return the transaction history of your wallet.

  $ electrum history

`importprivkey`: Import a private key into your wallet.

  $ electrum importprivkey *PRIVATE_KEY*

`listaddresses`: Return a list of addresses in your wallet.

  $ electrum listaddresses [*options*]

      -a: show all addresses, including change addresses  
      -l: include labels in results

`listunspent`: Return the list of unspent inputs in your wallet.

  $ electrum listunspent

`mksendmanytx`: Create and broadcast a signed transaction to one or  
              more recipients.

  $ electrum mksendmanytx *RECIPIENT* *AMOUNT* [*RECIPIENT* *AMOUNT* ...] [*options*]

      --fee, -f *FEE*: set transaction fee of *FEE*  
      --fromaddr, -F *ADDRESS*: send from bitcoin address *ADDRESS*  
      --changeaddr, -c *ADDRESS*: send change to bitcoin address *ADDRESS*

`mktx`: Create a signed transaction.

  $ electrum mktx *RECIPIENT* *AMOUNT* [*LABEL*] [*options*]

      --fee, -f *FEE*: set transaction fee of *FEE*  
      --fromaddr, -F *ADDRESS*: send from bitcoin address *ADDRESS*  
      --changeaddr, -c *ADDRESS*: send change to bitcoin address *ADDRESS*

`password`: Change your wallet password.

  $ electrum password

`payto`: Create and broadcast a signed transaction.

  $ electrum payto *RECIPIENT* *AMOUNT* [*options*]

      --fee, -f *FEE*: set transaction fee of *FEE*  
      --fromaddr, -F *ADDRESS*: send from bitcoin address *ADDRESS*  
      --changeaddr, -c *ADDRESS*: send change to bitcoin address *ADDRESS*

  *RECIPIENT* can be a bitcoin address or an address label.

`paytomany`: Create and broadcast a signed transaction to one or more  
           recipients.

  $ electrum paytomany *RECIPIENT* *AMOUNT* [*RECIPIENT* *AMOUNT* ...]

      --fee, -f *FEE*: set transaction fee of *FEE*  
      --fromaddr, -F *ADDRESS*: send from bitcoin address *ADDRESS*  
      --changeaddr, -c *ADDRESS*: send change to bitcoin address *ADDRESS*

  *RECIPIENT* can be a bitcoin address or an address label.  

`restore`: Restore a wallet. Accepts a seed or master public key.

  $ electrum restore

`sendrawtransaction`: Broadcast a signed transaction to the network.

  $ electrum sendrawtransaction *TX_IN_HEXADECIMAL*

`setconfig`: Set a configuration variable.

  $ electrum setconfig *NAME* *VALUE*

`setlabel`: Assign a label to an item.

  $ electrum setlabel *TX_HASH* *LABEL*

`signmessage`: Sign a message with a key. If you want to lead or end  
             a message with spaces, or want double spaces inside the  
             message, make sure you surround the string in quotes.

  $ electrum signmessage *ADDRESS* *MESSAGE*

`signrawtransaction`: Sign a raw transaction.

  $ electrum signrawtransaction ...

`unfreeze`: Unfreeze the funds at one of your wallet's addresses.

  $ electrum unfreeze *ADDRESS*

`validateaddress`: Check that the address is valid.

  $ electrum validateaddress *ADDRESS*

`verifymessage`: Verifies a signature. If you want to lead or end a  
               message with spaces, or want double spaces inside the  
               message, make sure you surround the string in quotes.

  $ electrum verifymessage *ADDRESS* *SIGNATURE* *MESSAGE*

FILES
-----

*~/.electrum/config*
  Per user configuration file. See foo(5) for further details.

ENVIRONMENT
-----------

`FOOCONF`
  If non-null the full pathname for an alternate system wide
  */etc/foo.conf*. Overridden by the `-c` option.

EXAMPLES
--------

The following diagnostics may be issued on stderr:

**Bad magic number.**
  The input file does not look like an archive file.

**Old style baz segments.**
  `foo` can only handle new style baz segments. COBOL object libraries
  are not supported in this version.

BUGS
----

Report issues at https://github.com/spesmilo/electrum/issues.

AUTHOR
------

This manual page was written by Andy Weidenbaum
<archbaum@gmail.com>. Permission is granted to copy, distribute and/or
modify this document under the terms of the GNU General Public License,
Version 3 or any later version published by the Free Software Foundation.

SEE ALSO
--------

electrum-server(1), bitcoind(1)
