ELECTRUM 1.9.7 "JANUARY 2014" Linux "User Manuals"
==================================================

NAME
----

electrum - Bitcoin thin client ("wallet")

SYNOPSIS
--------

`electrum` [`-w` *wallet* ] [`-p` *proxy* ] [`-s` *server* ] [`-g` *gui* ] [`-1`] [`-o`] [`-C`]  
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

`-w` *path/to/wallet.dat*, `--wallet`=*WALLET_PATH*
  Load the wallet file *path/to/wallet.dat* instead of the default,
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

`-v`, `--verbose`
  Verbose mode. Shows debugging information.

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

The command name should have been chosen more carefully to reflect
its purpose.

AUTHOR
------

This manual page was written by Andy Weidenbaum
<archbaum@gmail.com>. Permission is granted to copy, distribute and/or
modify this document under the terms of the GNU General Public License,
Version 3 or any later version published by the Free Software Foundation.

SEE ALSO
--------

electrum-server(1), bitcoind(1)
