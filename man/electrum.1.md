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

`-p` *type:host:port*, `--port`=*PORT*
  Use the proxy type:host:port to connect to an Electrum server,
  where type is either `socks4`, `socks5` or `http`.

`-s` *host:port:protocol*, `--server`=*SERVER*
  Connect to the Electrum server at `host:port`, where protocol is either
  `t` (tcp), `h` (http), `s` (tcp+ssl), or `g` (https). Port should be
  8081 for HTTP, 8082 for HTTPS, 50001 for TCP, or 50002 for SSL.

`-g` *[gui]*, `--gui`=*GUI*
  Use the selected GUI, where gui is either `qt`, `lite`, `gtk`, `text`
  or `stdio`. The default GUI is `qt`.

`-1`, `--oneserver`
  Connect to one server only, useful when running a private instance
  of electrum-server.

`-o`, `--offline`
  Operate in offline mode, useful when no Internet connection is present.

`-C`, `--concealed`
  Don't echo seed to console, useful when running on potentially
  untrusted hosts.

`-h`, `--help`
  Display help and exit.

`-v`, `--verbose`
  Verbose mode. Shows debugging information.

COMMANDS
--------

`contacts`
  Show your list of contacts.

`create`
  Create a new wallet.

`createmultisig`
  TBD

`createrawtransaction`
  TBD

`decoderawtransaction`
  TBD

`deseed`
  Remove seed from wallet, creating a seedless, watching-only wallet.

`dumpprivkey`
  Dump private key for specified address.
    Syntax: electrum dumpprivkey {address}

`dumpprivkeys`
  Dump all private keys.

`freeze`
  Freeze the funds at one of your wallet's addresses.
    Syntax: electrum freeze {address}

`getaddressbalance`
  Return the balance of an address.
    Syntax: electrum getaddressbalance {address}

`getaddresshistory`
  Return the transaction history of a wallet address.
    Syntax: electrum getaddresshistory {address}

`getbalance`
  Return the balance of your wallet, or of one account in your wallet.
    Syntax: electrum getbalance {account}

`getconfig`
  Return a configuration variable.
    Syntax: electrum getconfig {name}

`getmpk`
  Return your wallet's master public key.
    Syntax: electrum getmpk

`getpubkeys`
  Return the pubkeys for a wallet address.
    Syntax: electrum getpubkeys {address}

`getrawtransaction`
  Retrieve a transaction.
    Syntax: electrum getrawtransaction {txhash} {height}

`getseed`
  Print the generation seed of your wallet.
    Syntax: electrum getseed

`getservers`
  Return the list of available servers.
    Syntax: electrum getservers

`getversion`
  Return the version of your client.
    Syntax: electrum getversion

`help`
  Print help.
    Syntax: electrum gethelp

`history`
  Return the transaction history of your wallet.
    Syntax: electrum history

`importprivkey`
  Import a private key into your wallet.
    Syntax: electrum importprivkey {privatekey}

`listaddresses`
  Return a list of addresses in your wallet.
    Syntax:
      electrum listaddresses
    Options:
      -a
        show all addresses, including change addresses
      -l
        include labels in results

`listunspent`
  Return the list of unspent inputs in your wallet.
    Syntax: electrum listunspent

`mksendmanytx`
  Create and broadcast a signed transaction to one or more recipients.
    Syntax:
      electrum mksendmanytx {recipient} {amount} [{recipient} {amount} ...]
    Options:
      --fee, -f
        set transaction fee
      --fromaddr, -F
        send from address {address}
      --changeaddr, -c
        send change to address

`mktx`
  Create a signed transaction.
    Syntax:
      electrum mktx {recipient} {amount} [label]
    Options:
      --fee, -f
        set transaction fee
      --fromaddr, -F
        send from address {address}
      --changeaddr, -c
        send change to address

`password`
  Change your wallet password.
    Syntax: electrum password

`payto`
  Create and broadcast a transaction.
    Syntax: payto {recipient} {amount}
      {recipient} can be a bitcoin address or a label
    Options:
      --fee, -f
        set transaction fee
      --fromaddr, -F
        send from address {address}
      --changeaddr, -c
        send change to address

`paytomany`
  Create and broadcast a transaction to one or more recipients.
    Syntax: payto {recipient} {amount} [{recipient} {amount} ...]
      {recipient} can be a bitcoin address or a label
    Options:
      --fee, -f
        set transaction fee
      --fromaddr, -F
        send from address {address}
      --changeaddr, -c
        send change to address

`restore`
  Restore a wallet. Accepts a seed or master public key.
    Syntax: electrum restore

`sendrawtransaction`
  Broadcast a signed transaction to the network.
    Syntax: electrum sendrawtransaction {tx in hexadecimal}

`setconfig`
  Set a configuration variable.
    Syntax: electrum setconfig {name} {value}

`setlabel`
  Assign a label to an item.
    Syntax: electrum setlabel {tx_hash} {label}

`signmessage`
  Sign a message with a key. If you want to lead or end a message with
  spaces, or want double spaces inside the message, make sure you surround
  the string in quotes.
    Syntax: electrum signmessage {address} {message}

`signrawtransaction`
  TBD

`unfreeze`
  Unfreeze the funds at one of your wallet's addresses.
    Syntax: electrum unfreeze {address}

`validateaddress`
  Check that the address is valid.
    Syntax: electrum validateaddress {address}

`verifymessage`
  Verifies a signature. If you want to lead or end a message with spaces,
  or want double spaces inside the message, make sure you surround the
  string in quotes.
    Syntax: electrum verifymessage {address} {signature} {message}

FILES
-----

*~/.electrum/config*
  Per user configuration file. See foo(5) for further details.

ENVIRONMENT
-----------

`FOOCONF`
  If non-null the full pathname for an alternate system wide
  */etc/foo.conf*. Overridden by the `-c` option.

DIAGNOSTICS
-----------

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
