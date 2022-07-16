# cosmosia (Cosmos Infrastructure Automation)

Open solution to build a reliable infrastructure for cosmos/tendermint based chains ( see [background](https://github.com/cosmos/chain-registry/issues/214) ):
- API service: Load balancing for Rpc, Rest, Websocket, [GRPC](docs/grpc.md) and JSON-RPC with active-healthcheck, rate-limiting and ip-whitelist.
- Daily [snapshot service](https://snapshot.notional.ventures/) for goleveldb and [rocksdb](/docs/rocksdb.md)
- Monitoring tools for both [internal](docs/rpc_monitor.md) and [external](https://status.notional.ventures/) view.
- Auto [pruning](https://github.com/notional-labs/cosmprund) and rpc service with snapshot/data versioning

See [status page](https://status.notional.ventures/) of our cluster.

### Supported chains:
| No | Chain                             | GoLevelDB<br>Snapshot                                                   | [RocksDB<br>Snapshot](/docs/rocksdb.md)                                         | Public<br>RPC                                              | Public<br>API                                              | Public<br>GRPC                                              | [Statesync](docs/statesync.md) |
|---:|:----------------------------------|:-----------------------------------------------------------------------:|:-------------------------------------------------------------------------------:|:----------------------------------------------------------:|:----------------------------------------------------------:|:-----------------------------------------------------------:|:------------------------------:|
| 1  | Osmosis<br>(osmosis)              | [<sub>:link:</sub>](https://snapshot.notional.ventures/osmosis/)        |                                                                                 | [<sub>:link:</sub>](https://rpc-osmosis-ia.notional.ventures/)        | [<sub>:link:</sub>](https://api-osmosis-ia.notional.ventures/)        | [<sub>:link:</sub>](https://grpc-osmosis-ia.notional.ventures/)        | :x:                            | 
| 2  | Starname<br>(starname)            | [<sub>:link:</sub>](https://snapshot.notional.ventures/starname/)       |                                                                                 | [<sub>:link:</sub>](https://rpc-starname-ia.notional.ventures/)       | [<sub>:link:</sub>](https://api-starname-ia.notional.ventures/)       | [<sub>:link:</sub>](https://grpc-starname-ia.notional.ventures/)       | :x:                            |
| 3  | Regen<br>(regen)                  | [<sub>:link:</sub>](https://snapshot.notional.ventures/regen/)          |                                                                                 | [<sub>:link:</sub>](https://rpc-regen-ia.notional.ventures/)          | [<sub>:link:</sub>](https://api-regen-ia.notional.ventures/)          | [<sub>:link:</sub>](https://grpc-regen-ia.notional.ventures/)          | :white_check_mark:             |
| 4  | Akash<br>(akash)                  | [<sub>:link:</sub>](https://snapshot.notional.ventures/akash/)          | [<sub>:link:</sub>](https://snapshot.notional.ventures/akash/rocksdb/)          | [<sub>:link:</sub>](https://rpc-akash-ia.notional.ventures/)          | [<sub>:link:</sub>](https://api-akash-ia.notional.ventures/)          | [<sub>:link:</sub>](https://grpc-akash-ia.notional.ventures/)          | :white_check_mark:             |
| 5  | Gaia<br>(cosmoshub)               | [<sub>:link:</sub>](https://snapshot.notional.ventures/cosmoshub/)      | [<sub>:link:</sub>](https://snapshot.notional.ventures/cosmoshub/rocksdb/)      | [<sub>:link:</sub>](https://rpc-cosmoshub-ia.notional.ventures/)      | [<sub>:link:</sub>](https://api-cosmoshub-ia.notional.ventures/)      | [<sub>:link:</sub>](https://grpc-cosmoshub-ia.notional.ventures/)      | :white_check_mark:             |
| 6  | Sentinel<br>(sentinel)            | [<sub>:link:</sub>](https://snapshot.notional.ventures/sentinel/)       | [<sub>:link:</sub>](https://snapshot.notional.ventures/sentinel/rocksdb/)       | [<sub>:link:</sub>](https://rpc-sentinel-ia.notional.ventures/)       | [<sub>:link:</sub>](https://api-sentinel-ia.notional.ventures/)       | [<sub>:link:</sub>](https://grpc-sentinel-ia.notional.ventures/)       | :white_check_mark:             |
| 7  | E-Money<br>(emoney)               | [<sub>:link:</sub>](https://snapshot.notional.ventures/emoney/)         | [<sub>:link:</sub>](https://snapshot.notional.ventures/emoney/rocksdb/)         | [<sub>:link:</sub>](https://rpc-emoney-ia.notional.ventures/)         | [<sub>:link:</sub>](https://api-emoney-ia.notional.ventures/)         | [<sub>:link:</sub>](https://grpc-emoney-ia.notional.ventures/)         | :white_check_mark:             |
| 8  | Ixo<br>(ixo)                      | [<sub>:link:</sub>](https://snapshot.notional.ventures/ixo/)            | [<sub>:link:</sub>](https://snapshot.notional.ventures/ixo/rocksdb/)            | [<sub>:link:</sub>](https://rpc-ixo-ia.notional.ventures/)            | [<sub>:link:</sub>](https://api-ixo-ia.notional.ventures/)            | [<sub>:link:</sub>](https://grpc-ixo-ia.notional.ventures/)            | :white_check_mark:             |
| 9  | Juno<br>(juno)                    | [<sub>:link:</sub>](https://snapshot.notional.ventures/juno/)           |                                                                                 | [<sub>:link:</sub>](https://rpc-juno-ia.notional.ventures/)           | [<sub>:link:</sub>](https://api-juno-ia.notional.ventures/)           | [<sub>:link:</sub>](https://grpc-juno-ia.notional.ventures/)           | :x:                            |
| 10 | Sifchain<br>(sifchain)            | [<sub>:link:</sub>](https://snapshot.notional.ventures/sifchain/)       |                                                                                 | [<sub>:link:</sub>](https://rpc-sifchain-ia.notional.ventures/)       | [<sub>:link:</sub>](https://api-sifchain-ia.notional.ventures/)       | [<sub>:link:</sub>](https://grpc-sifchain-ia.notional.ventures/)       | :white_check_mark:             |
| 11 | Likecoin<br>(likecoin)            | [<sub>:link:</sub>](https://snapshot.notional.ventures/likecoin/)       | [<sub>:link:</sub>](https://snapshot.notional.ventures/likecoin/rocksdb/)       | [<sub>:link:</sub>](https://rpc-likecoin-ia.notional.ventures/)       | [<sub>:link:</sub>](https://api-likecoin-ia.notional.ventures/)       | [<sub>:link:</sub>](https://grpc-likecoin-ia.notional.ventures/)       | :white_check_mark:             |
| 12 | Ki<br>(kichain)                   | [<sub>:link:</sub>](https://snapshot.notional.ventures/kichain/)        | [<sub>:link:</sub>](https://snapshot.notional.ventures/kichain/rocksdb/)        | [<sub>:link:</sub>](https://rpc-kichain-ia.notional.ventures/)        | [<sub>:link:</sub>](https://api-kichain-ia.notional.ventures/)        | [<sub>:link:</sub>](https://grpc-kichain-ia.notional.ventures/)        | :white_check_mark:             |
| 13 | Cyber<br>(cyber)                  | [<sub>:link:</sub>](https://snapshot.notional.ventures/cyber/)          |                                                                                 | [<sub>:link:</sub>](https://rpc-cyber-ia.notional.ventures/)          | [<sub>:link:</sub>](https://api-cyber-ia.notional.ventures/)          | [<sub>:link:</sub>](https://grpc-cyber-ia.notional.ventures/)          | :x:                            |
| 14 | Cheqd<br>(cheqd)                  | [<sub>:link:</sub>](https://snapshot.notional.ventures/cheqd/)          |                                                                                 | [<sub>:link:</sub>](https://rpc-cheqd-ia.notional.ventures/)          | [<sub>:link:</sub>](https://api-cheqd-ia.notional.ventures/)          | [<sub>:link:</sub>](https://grpc-cheqd-ia.notional.ventures/)          | :x:                            |
| 15 | Stargaze<br>(stargaze)            | [<sub>:link:</sub>](https://snapshot.notional.ventures/stargaze/)       |                                                                                 | [<sub>:link:</sub>](https://rpc-stargaze-ia.notional.ventures/)       | [<sub>:link:</sub>](https://api-stargaze-ia.notional.ventures/)       | [<sub>:link:</sub>](https://grpc-stargaze-ia.notional.ventures/)       | :x:                            |
| 16 | Band<br>(bandchain)               | [<sub>:link:</sub>](https://snapshot.notional.ventures/bandchain/)      | [<sub>:link:</sub>](https://snapshot.notional.ventures/bandchain/rocksdb/)      | [<sub>:link:</sub>](https://rpc-bandchain-ia.notional.ventures/)      | [<sub>:link:</sub>](https://api-bandchain-ia.notional.ventures/)      | [<sub>:link:</sub>](https://grpc-bandchain-ia.notional.ventures/)      | :white_check_mark:             |
| 17 | Chihuahua<br>(chihuahua)          | [<sub>:link:</sub>](https://snapshot.notional.ventures/chihuahua/)      | [<sub>:link:</sub>](https://snapshot.notional.ventures/chihuahua/rocksdb/)      | [<sub>:link:</sub>](https://rpc-chihuahua-ia.notional.ventures/)      | [<sub>:link:</sub>](https://api-chihuahua-ia.notional.ventures/)      | [<sub>:link:</sub>](https://grpc-chihuahua-ia.notional.ventures/)      | :white_check_mark:             |
| 18 | Kava<br>(kava)                    | [<sub>:link:</sub>](https://snapshot.notional.ventures/kava/)           | [<sub>:link:</sub>](https://snapshot.notional.ventures/kava/rocksdb/)           | [<sub>:link:</sub>](https://rpc-kava-ia.notional.ventures/)           | [<sub>:link:</sub>](https://api-kava-ia.notional.ventures/)           | [<sub>:link:</sub>](https://grpc-kava-ia.notional.ventures/)           | :white_check_mark:             |
| 19 | BitCanna<br>(bitcanna)            | [<sub>:link:</sub>](https://snapshot.notional.ventures/bitcanna/)       | [<sub>:link:</sub>](https://snapshot.notional.ventures/bitcanna/rocksdb/)       | [<sub>:link:</sub>](https://rpc-bitcanna-ia.notional.ventures/)       | [<sub>:link:</sub>](https://api-bitcanna-ia.notional.ventures/)       | [<sub>:link:</sub>](https://grpc-bitcanna-ia.notional.ventures/)       | :white_check_mark:             |
| 20 | Konstellation<br>(konstellation)  | [<sub>:link:</sub>](https://snapshot.notional.ventures/konstellation/)  | [<sub>:link:</sub>](https://snapshot.notional.ventures/konstellation/rocksdb/)  | [<sub>:link:</sub>](https://rpc-konstellation-ia.notional.ventures/)  | [<sub>:link:</sub>](https://api-konstellation-ia.notional.ventures/)  | [<sub>:link:</sub>](https://grpc-konstellation-ia.notional.ventures/)  | :white_check_mark:             |
| 21 | Omniflix<br>(omniflixhub)         | [<sub>:link:</sub>](https://snapshot.notional.ventures/omniflixhub/)    | [<sub>:link:</sub>](https://snapshot.notional.ventures/omniflixhub/rocksdb/)    | [<sub>:link:</sub>](https://rpc-omniflixhub-ia.notional.ventures/)    | [<sub>:link:</sub>](https://api-omniflixhub-ia.notional.ventures/)    | [<sub>:link:</sub>](https://grpc-omniflixhub-ia.notional.ventures/)    | :white_check_mark:             |
| 22 | Terra<br>(terra)                  | [<sub>:link:</sub>](https://snapshot.notional.ventures/terra/)          |                                                                                 | [<sub>:link:</sub>](https://rpc-terra-ia.notional.ventures/)          | [<sub>:link:</sub>](https://api-terra-ia.notional.ventures/)          | [<sub>:link:</sub>](https://grpc-terra-ia.notional.ventures/)          | :x:                            |
| 23 | Vidulum<br>(vidulum)              | [<sub>:link:</sub>](https://snapshot.notional.ventures/vidulum/)        | [<sub>:link:</sub>](https://snapshot.notional.ventures/vidulum/rocksdb/)        | [<sub>:link:</sub>](https://rpc-vidulum-ia.notional.ventures/)        | [<sub>:link:</sub>](https://api-vidulum-ia.notional.ventures/)        | [<sub>:link:</sub>](https://grpc-vidulum-ia.notional.ventures/)        | :white_check_mark:             |
| 24 | Provenance<br>(provenance)        | [<sub>:link:</sub>](https://snapshot.notional.ventures/provenance/)     | [<sub>:link:</sub>](https://snapshot.notional.ventures/provenance/rocksdb/)     | [<sub>:link:</sub>](https://rpc-provenance-ia.notional.ventures/)     | [<sub>:link:</sub>](https://api-provenance-ia.notional.ventures/)     | [<sub>:link:</sub>](https://grpc-provenance-ia.notional.ventures/)     | :white_check_mark:             |
| 25 | Dig<br>(dig)                      | [<sub>:link:</sub>](https://snapshot.notional.ventures/dig/)            | [<sub>:link:</sub>](https://snapshot.notional.ventures/dig/rocksdb/)            | [<sub>:link:</sub>](https://rpc-dig-ia.notional.ventures/)            | [<sub>:link:</sub>](https://api-dig-ia.notional.ventures/)            | [<sub>:link:</sub>](https://grpc-dig-ia.notional.ventures/)            | :white_check_mark:             |
| 26 | Gravity-Bridge<br>(gravitybridge) | [<sub>:link:</sub>](https://snapshot.notional.ventures/gravitybridge/)  | [<sub>:link:</sub>](https://snapshot.notional.ventures/gravitybridge/rocksdb/)  | [<sub>:link:</sub>](https://rpc-gravitybridge-ia.notional.ventures/)  | [<sub>:link:</sub>](https://api-gravitybridge-ia.notional.ventures/)  | [<sub>:link:</sub>](https://grpc-gravitybridge-ia.notional.ventures/)  | :white_check_mark:             |  
| 27 | Comdex<br>(comdex)                | [<sub>:link:</sub>](https://snapshot.notional.ventures/comdex/)         | [<sub>:link:</sub>](https://snapshot.notional.ventures/comdex/rocksdb/)         | [<sub>:link:</sub>](https://rpc-comdex-ia.notional.ventures/)         | [<sub>:link:</sub>](https://api-comdex-ia.notional.ventures/)         | [<sub>:link:</sub>](https://grpc-comdex-ia.notional.ventures/)         | :white_check_mark:             |
| 28 | Cerberus<br>(cerberus)            | [<sub>:link:</sub>](https://snapshot.notional.ventures/cerberus/)       | [<sub>:link:</sub>](https://snapshot.notional.ventures/cerberus/rocksdb/)       | [<sub>:link:</sub>](https://rpc-cerberus-ia.notional.ventures/)       | [<sub>:link:</sub>](https://api-cerberus-ia.notional.ventures/)       | [<sub>:link:</sub>](https://grpc-cerberus-ia.notional.ventures/)       | :white_check_mark:             |
| 29 | BitSong<br>(bitsong)              | [<sub>:link:</sub>](https://snapshot.notional.ventures/bitsong/)        | [<sub>:link:</sub>](https://snapshot.notional.ventures/bitsong/rocksdb/)        | [<sub>:link:</sub>](https://rpc-bitsong-ia.notional.ventures/)        | [<sub>:link:</sub>](https://api-bitsong-ia.notional.ventures/)        | [<sub>:link:</sub>](https://grpc-bitsong-ia.notional.ventures/)        | :white_check_mark:             |
| 30 | ~~AssetMantle<br>(assetmantle)~~  | [<sub>:link:</sub>](https://snapshot.notional.ventures/assetmantle/)    |                                                                                 | [<sub>:link:</sub>](https://rpc-assetmantle-ia.notional.ventures/)    | [<sub>:link:</sub>](https://api-assetmantle-ia.notional.ventures/)    | [<sub>:link:</sub>](https://grpc-assetmantle-ia.notional.ventures/)    | :white_check_mark:             | 
| 31 | FetchAI<br>(fetchhub)             | [<sub>:link:</sub>](https://snapshot.notional.ventures/fetchhub/)       |                                                                                 | [<sub>:link:</sub>](https://rpc-fetchhub-ia.notional.ventures/)       | [<sub>:link:</sub>](https://api-fetchhub-ia.notional.ventures/)       | [<sub>:link:</sub>](https://grpc-fetchhub-ia.notional.ventures/)       | :x:                            |
| 32 | Evmos<br>(evmos)                  | [<sub>:link:</sub>](https://snapshot.notional.ventures/evmos/)          |                                                                                 | [<sub>:link:</sub>](https://rpc-evmos-ia.notional.ventures/)          | [<sub>:link:</sub>](https://api-evmos-ia.notional.ventures/)          | [<sub>:link:</sub>](https://grpc-evmos-ia.notional.ventures/)          | :white_check_mark:             | 
| 33 | Persistence<br>(persistent)       | [<sub>:link:</sub>](https://snapshot.notional.ventures/persistent/)     |                                                                                 | [<sub>:link:</sub>](https://rpc-persistent-ia.notional.ventures/)     | [<sub>:link:</sub>](https://api-persistent-ia.notional.ventures/)     | [<sub>:link:</sub>](https://grpc-persistent-ia.notional.ventures/)     | :white_check_mark:             |
| 34 | Crypto.org<br>(cryptoorgchain)    | [<sub>:link:</sub>](https://snapshot.notional.ventures/cryptoorgchain/) | [<sub>:link:</sub>](https://snapshot.notional.ventures/cryptoorgchain/rocksdb/) | [<sub>:link:</sub>](https://rpc-cryptoorgchain-ia.notional.ventures/) | [<sub>:link:</sub>](https://api-cryptoorgchain-ia.notional.ventures/) | [<sub>:link:</sub>](https://grpc-cryptoorgchain-ia.notional.ventures/) | :white_check_mark:             |
| 35 | IRISnet<br>(irisnet)              | [<sub>:link:</sub>](https://snapshot.notional.ventures/irisnet/)        | [<sub>:link:</sub>](https://snapshot.notional.ventures/irisnet/rocksdb/)        | [<sub>:link:</sub>](https://rpc-irisnet-ia.notional.ventures/)        | [<sub>:link:</sub>](https://api-irisnet-ia.notional.ventures/)        | [<sub>:link:</sub>](https://grpc-irisnet-ia.notional.ventures/)        | :white_check_mark:             |
| 36 | Axelar<br>(axelar)                | [<sub>:link:</sub>](https://snapshot.notional.ventures/axelar/)         |                                                                                 | [<sub>:link:</sub>](https://rpc-axelar-ia.notional.ventures/)         | [<sub>:link:</sub>](https://api-axelar-ia.notional.ventures/)         | [<sub>:link:</sub>](https://grpc-axelar-ia.notional.ventures/)         | :white_check_mark:             |
| 37 | Pylons Testnet<br>(pylons)        | [<sub>:link:</sub>](https://snapshot.notional.ventures/pylons/)         |                                                                                 | [<sub>:link:</sub>](https://rpc-pylons-ia.notional.ventures/)         | [<sub>:link:</sub>](https://api-pylons-ia.notional.ventures/)         | [<sub>:link:</sub>](https://grpc-pylons-ia.notional.ventures/)         | :white_check_mark:             |
| 38 | Umee<br>(umee)                    | [<sub>:link:</sub>](https://snapshot.notional.ventures/umee/)           |                                                                                 | [<sub>:link:</sub>](https://rpc-umee-ia.notional.ventures/)           | [<sub>:link:</sub>](https://api-umee-ia.notional.ventures/)           | [<sub>:link:</sub>](https://grpc-umee-ia.notional.ventures/)           | :white_check_mark:             |
| 39 | Sei-Chain<br>Testnet (sei)        | [<sub>:link:</sub>](https://snapshot.notional.ventures/sei/)            |                                                                                 | [<sub>:link:</sub>](https://rpc-sei-ia.notional.ventures/)            | [<sub>:link:</sub>](https://api-sei-ia.notional.ventures/)            | [<sub>:link:</sub>](https://grpc-sei-ia.notional.ventures/)            |                                |



Add a new chain? Follow this [guide](docs/new_chain.md)

### Docs
See [Docs](./docs/)
