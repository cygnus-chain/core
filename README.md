## Cygnus Core

Official Golang implementation of the Cygnus EVM blockchain protocol.


Building `geth` (Cygnus fork v1.10.23) requires both a Go (version 1.16 or later) and a C compiler. You can install them using your favourite package manager. Once the dependencies are installed, run

```shell
make geth
```

or, to build the full suite of utilities:

```shell
make all
```

## Executables

The Cygnus Core project comes with several wrappers/executables found in the `cmd` directory.

| Command    | Description                                                                                                                                                                                                                             |
| ---------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **`geth`** | Main Cygnus CLI client. Entry point into the Cygnus network (main, test, or private net), capable of running as full, archive, or light node. Provides JSON-RPC endpoints over HTTP, WebSocket, and IPC. `geth --help` for CLI options. |
| `clef`     | Stand-alone signing tool used as a backend signer for `geth`.                                                                                                                                                                           |
| `devp2p`   | Utilities to interact with nodes on the networking layer without running a full blockchain.                                                                                                                                             |
| `abigen`   | Converts smart contract ABIs into compile-time type-safe Go packages for Cygnus contracts.                                                                                                                                              |
| `bootnode` | Lightweight node for peer discovery in private networks.                                                                                                                                                                                |
| `evm`      | Developer utility for running Cygnus Virtual Machine (CVM) bytecode snippets for debugging.                                                                                                                                             |
| `rlpdump`  | Converts RLP dumps into user-friendly hierarchical representations.                                                                                                                                                                     |
| `puppeth`  | CLI wizard to create new Cygnus networks.                                                                                                                                                                                               |

### Hardware Requirements

**Minimum:**

* CPU with 2+ cores
* 4GB RAM
* 1TB free storage
* 8 MBit/sec Internet

**Recommended:**

* CPU with 4+ cores
* 16GB+ RAM
* SSD with 1TB+ storage
* 25+ MBit/sec Internet

### Running a full node

```shell
$ geth console
```

Starts `geth` in snap sync mode with an interactive JavaScript console for managing accounts, sending transactions, and interacting with contracts.

### Running test networks

```shell
$ geth --testnet console
```

*Connect to Cygnus testnet for development without using real funds.*

### Configuration

```shell
$ geth --config /path/to/your_config.toml
```

Dump your configuration:

```shell
$ geth --your-flags dumpconfig
```

### Docker quick start

```shell
docker run -d --name cygnus-node -v /Users/alice/cygnus:/root \
           -p 8545:8545 -p 30303:30303 \
           cygnuschain/core
```
