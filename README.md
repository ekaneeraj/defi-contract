# Getting Started

## Deployed contract address:
1. Address: 0x8255b0DCa09Ca31dA7E6F2f625933Bad594604e4
2. Explorer link: [Link](https://sepolia.etherscan.io/address/0x8255b0DCa09Ca31dA7E6F2f625933Bad594604e4)

## Requirements

- [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
  - You'll know you did it right if you can run `git --version` and you see a response like `git version x.x.x`
- [foundry](https://getfoundry.sh/)
  - You'll know you did it right if you can run `forge --version` 


## Quickstart

```
git clone https://github.com/ekaneeraj/defi-contract
cd defi-contract
forge build
```

# Usage

## Deploy:

```
forge script script/DeployDSC.s.sol
```

## Testing

Out of 5 test tiers.

1. Unit
2. Integration
3. Forked
4. Staging
5. Fuzz

This repo have Unit testing, Forked, and Fuzz testing. 

```
forge test
```

or 

```
// Only run test functions matching the specified regex pattern.
forge test --match-test testFunctionName
```

or

```
forge test --fork-url $SEPOLIA_RPC_URL
```

### Test Coverage

```
forge coverage
```


# Deployment to a testnet or mainnet

1. Setup environment variables

You'll want to set your `SEPOLIA_RPC_URL` and `PRIVATE_KEY` as environment variables. You can add them to a `.env` file, similar to what you see in `.env.example`.

- `PRIVATE_KEY`: The private key of your account (like from [metamask](https://metamask.io/)). **NOTE:** FOR DEVELOPMENT, PLEASE USE A KEY THAT DOESN'T HAVE ANY REAL FUNDS ASSOCIATED WITH IT.
  - You can [learn how to export it here](https://metamask.zendesk.com/hc/en-us/articles/360015289632-How-to-Export-an-Account-Private-Key).
- `SEPOLIA_RPC_URL`: This is url of the sepolia testnet node you're working with. You can get setup with one for free from [Alchemy](https://alchemy.com/)

Optionally, add your `ETHERSCAN_API_KEY` if you want to verify your contract on [Etherscan](https://etherscan.io/).


Also, you can also store private key by creating a keystore wallet to avoid adding private key in .env file. To create keystore wallet you can following steps: 

1. Run script to create new wallet and import your priavte key

```bash
cast wallet import defaultKey --interactive
```
here, defaultKey is wallet name

2. verify if wallet added
```bash
cast wallet list
```

1. Get testnet ETH

Head over to [faucets.chain.link](https://faucets.chain.link/) and get some testnet ETH. You should see the ETH show up in your metamask.

3. Deploy

```
forge script script/DeployDSC.s.sol --rpc-url $SEPOLIA_RPC_URL --private-key $PRIVATE_KEY --broadcast --verify --etherscan-api-key $ETHERSCAN_API_KEY
```

or

 deploy using keystore
```bash
forge script script/DeployDSC.s.sol --rpc-url $SEPOLIA_RPC_URL --account defaultKey --sender <Wallet Address> --broadcast`
```

## Estimate gas

You can estimate how much gas things cost by running:

```
forge snapshot
```

And you'll see an output file called `.gas-snapshot`


# Formatting


To run code formatting:
```
forge fmt
```


# Thank you!

If you appreciated this, feel free to follow me or donate!

ETH/Arbitrum/Optimism/Polygon/etc Address: 0xA5bBdb3C44e451e07e358d86e2168e280df95e35

[![Neeraj Singh Instagram](https://img.shields.io/badge/Instagram-FF0000?style=for-the-badge&logo=instagram&logoColor=white)](https://instagram.com/ekaneeraj)
[![Neeraj Singh Linkedin](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ekaneeraj/)
[![Neeraj Singh Twitter](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/ekaneeraj)