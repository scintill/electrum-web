ELECTRUM 1.9.7 "JANUARY 2014" Linux "User Manuals"
==================================================

NAME
----

Electrum - Bitcoin thin client

SYNOPSIS
--------

`electrum` [`-w` *wallet* ] [`-p` *proxy* ] [`-s` *server* ] [`-g` *gui* ] [`-o`] [`-C`]

DESCRIPTION
-----------

`Electrum` is an easy to use Bitcoin wallet. It protects you from
losing coins in a backup mistake or computer failure, because your
wallet can be recovered from a secret phrase you can write on paper
or learn by heart. There's no waiting time when you start Electrum,
because it doesn't download the Bitcoin blockchain.

OPTIONS
-------

`-w` */path/to/wallet.dat*
  Load the wallet file */path/to/wallet.dat* instead of the default,
  *~/.electrum/wallets/default_wallet*.

`-p` *[type:]host[:port]*
  Use the proxy [type:]host[:port] to connect to an Electrum server,
  where type is either `socks4`, `socks5` or `http`.

`-s` *host:port:protocol*
  Connect to the Electrum server at `host:port`, where protocol is either
  `t` or `h`. Port should be 8081 for HTTP, 8082 for HTTPS, 50001 for TCP,
  or 50002 for SSL.

`-g` *[gui]*
  Use the selected GUI, where gui is either `qt`, `lite`, `gtk`, `stdio`
  or `text`.
  The default GUI is qt.

`-o`
  Operate in offline mode, useful when no Internet connection is present.

`-C`
  Don't echo seed to console, useful when running on potentially
  untrusted hosts.

`-v`
  Verbose mode. Shows debugging information.

FILES
-----

*~/.electrum/config*
  Per user configuration file. See foo(5) for further details.

ENVIRONMENT
-----------

`FOOCONF`
  If non-null the full pathname for an alternate system wide */etc/foo.conf*.
  Overridden by the `-c` option.

DIAGNOSTICS
-----------

The following diagnostics may be issued on stderr:

**Bad magic number.**
  The input file does not look like an archive file.

**Old style baz segments.**
  `foo` can only handle new style baz segments. COBOL object libraries are not
  supported in this version.

BUGS
----

The command name should have been chosen more carefully to reflect its
purpose.

AUTHOR
------

Andy Weidenbaum <archbaum@gmail.com>

SEE ALSO
--------

bar(1), foo(5), xyzzy(1), [Linux Man Page Howto](
http://www.schweikhardt.net/man_page_howto.html)
