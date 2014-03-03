title: Architecture
prev: commands
next: create
---

Electrum is an expedient Bitcoin [front
end](https://en.wikipedia.org/wiki/Front_and_back_ends).

> In computer science, the front end is responsible for collecting input
> in various forms from the user and processing it to conform to a
> specification the back end can use. The front end is an interface
> between the user and the back end. The front and back ends may be
> distributed amongst one or more systems.

A full Electrum node consists of three parts:

> 1. [Electrum client](https://github.com/spesmilo/electrum) ("wallet")
> 2. [Electrum server](https://github.com/spesmilo/electrum-server) ("gateway")
> 3. `bitcoind`

On first run, the Electrum wallet connects to eight Electrum gateway
daemons.

> It is possible to connect to a private gateway daemon on the command
> line, see: [CLI](https://docs.electrum.org/cli).

The wallet chooses to sync blockchain headers based on the longest
chain present.

The gateway daemon manages a Patricia tree of UTXO (see: Ultimate
Blockchain Compression).

Electrum wallets generate Bitcoin ECDSA
keypairs offline. The deterministically generated
([BIP0032](https://en.bitcoin.it/wiki/BIP_0032)) public Bitcoin addresses
will contain a balance ranging from 0-21M BTC. The precise balance is
looked up in the Electrum gateway's Patricia tree.

To spend money from Electrum, the wallet creates, signs, and sends a raw
Bitcoin transaction to the Electrum gateway daemon, which proxies the
request onto `bitcoind`. `bitcoind` broadcasts the signed transaction
to the blockchain.
