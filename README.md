# quickpoc

easy POC template generation from the command line

## features

from the command line, call `quickpoc 0x.. [folder_name]` to generate a ready-to-go sandbox for running POCs for the given address against mainnet, including:

- forge template with name mirroring contract name
- `src/` folder populated with all contracts and libraries
- test file autogenerated with contract import
- test setup with contract variable and mainnet forking
- `cd folder_name` copied to clipboard to save you 1 extra second

you can run `forge test` to confirm it's working, then go into `tests/POC.t.sol` to interact with the contract (saved in storage as `c`).

## install

on a unix machine with bash installed, make sure you have all dependencies:
- foundry ([follow instructions here](https://github.com/foundry-rs/foundry))
- jq (`brew install jq`)

clone this repo locally.

```bash
git clone https://github.com/zobront/quickpoc.git
```

set up two environment variables by calling the following from your terminal:
```bash
export ETH_RPC_URL="..."
export ETHERSCAN_API_KEY="..."
```

save quickpoc to a location you won't move it.
```bash
mkdir ~/.quickpoc && mkdir ~/.quickpoc/bin
cp quickpoc ~/.quickpoc/bin/quickpoc # from within the cloned repo
```

add the following to your bash rc file.
```bash
export PATH="$PATH:/Users/{your_name}/.quickpoc/bin
```

make sure the file is executable.
```bash
chmod +x ~/.quickpoc/bin/quickpoc
```

you should then be able to call `quickpoc 0x..` from any folder to generate the POC folder within it.

## thank yous

big thanks to [deliriusz](https://github.com/deliriusz) for adding proxy checks and professionalism. check out his fork [turbopoc](https://github.com/deliriusz/turbopoc) for a more full featured version.
