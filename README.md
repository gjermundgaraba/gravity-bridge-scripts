# gravity-bridge-scripts
Just some scripts to more easily work with gravity-bridge locally

## full_build.sh
This scripts does the following:
- Clones and builds the ICS721 bridge smart contract
- Clones and builds cw-nfts smart contracts
- Builds Gravity Bridge (looks for this in a folder called `Gravity-Bridge` in the same directory level as this repo (i.e. `../Gravity-Bridge`))
- Builds the Gravity Bridge solidity contracts
- Builds the Gravity Bridge orchestrator

Requirements:
- Git
- Go (1.19)
- Rust
- Node and NPM
- cargo make
  - Install with: `$ cargo install --force cargo-make`
- Just (https://github.com/casey/just)

## serve.sh

The purpose of this script is to spin up everything you need to test gravity bridge locally with:
- Gravity Bridge
  - With a validator
  - And an orchestrator
- A local ethereum instance
- Stargaze
  - With a validator

Requirements:
- Gravity Bridge checked out in the same directory as this repo (i.e. on the same level, not inside it)
- Rly (also called "Go Relayer")


It will create the following directories in `/tmp` (referred to as `ROOT_DIR` in the script):
- evm-stuff
  - This is where the evm logs can be found
- relayer-stuff
  - This is where the relayer logs, config and keys will be stored
- gravity-local-1
  - This is the home directory (including the logs) of the gravity chain
- gbt-local-1
  - This is the home directory of the orchestrator
- stargaze-local-1
  - This is the home directory (including the logs) of the stargaze chain

All the folders and files will be deleted every time you run the script, so don't store anything important in there.