
# foundry-dynamicNft
It is a smart contract project written in [Solidity](https://docs.soliditylang.org/en/latest/) using [Foundry](https://book.getfoundry.sh/).
- It a smart contract I developed leveraging Foundry.
- It is a dynamic ERC-721 token (NFT) I developed using [OpenZeppline](https://github.com/OpenZeppelin/openzeppelin-contracts) library.
- It is a SVG NFT that is 100% stored on chain, hence completly decentralized.
- User can change the mood of the nft ([Happy](./img/happy.svg) / [Sad](./img/sad.svg)) by calling the "flipMood(uint256)" function.


## Getting Started

 - [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git): You'll know you did it right if you can run `git --version` and you see a response like `git version x.x.x`
 - [foundry](https://getfoundry.sh/): You'll know you did it right if you can run `forge --version` and you see a response like `forge 0.2.0 (816e00b 2023-03-16T00:05:26.396218Z)`
 - [make](https://www.gnu.org/software/make/manual/make.html) (optional - either you can install `make` or you can simply substitute the make commands with forge commands by referring to the Makefile after including your .env file): You'll know you did it right if you can run `make --version` and you will see a response like `GNU Make 3.81...`

 
## Installation

- Install foundry-dynamicNft
```bash
    git clone https://github.com/yug49/foundry-dynamicNft
    cd foundry-dynamicNft
```

- Make a .env file
```bash
    touch .env
```

- Open the .env file and fill in the details similar to:
```env
    SEPOLIA_RPC_URL=<YOUR SEPOLIA RPC URL>
    ETHERSCAN_API_KEY=<YOUR ETHERSCAN API KEY>
    SEPOLIA_PRIVATE_KEY=<YOUR PRIVATE KEY>
```
- Remove pre installed cache, unecessary or partially cloned modules modules etc.
```bash
    make clean
    make remove
```

- Install dependencies and libraries.
```bash
    make install
```

- Build Project
```bash
    make build
```



    ## Deployment

### Deploy On a Local Network (Anvil Testnet)
- To Deploy on a local network first run anvil on your local terminal in current directory by running coommmand: ` make anvil`.
- Now open another terminal and let this one run in the background
- Run the following command:
```bash
make deploy
```

### Deploy on a Sepolia or Any Other Network
- To Deploy on Sepolia, after successfully creating .env file as mentioned above.
- Get youself some Sepolia Eth and LINK tokens and then run command:
```bash
make deploy ARGS="--network sepolia"
```

## Scripts

- After deploying to a testnet or local net, you can run the scripts.

- Using cast mint yourself a mood NFT:

```bash
cast call <CONTRACT_ADDRESS> "mintNft()" --rpc-url --rpc-url $SEPOLIA_RPC_URL --private-key $PRIVATE_KEY --broadcast --verify --etherscan-api-key $ETHERSCAN_API_KEY --legacy -vvvvv
```

- After minting, you can change flip the mood by:

```bash
cash call <CONTRACT_ADDRESS> "flipMood(uint256)" <TOKEN_ID> --rpc-url $SEPOLIA_RPC_URL --private-key $PRIVATE_KEY --broadcast --verify --etherscan-api-key $ETHERSCAN_API_KEY --legacy -vvvvv
``` 

```bash



### You can also use Etherscan to interact with the contract:

- Open [sepolia.etherscan.io](https://sepolia.etherscan.io/).
- Search your deployed token contract address.
- Click on Contract tab > Read Contract / Write Contract.
- Connect your web3 wallet.


## Estimate gas
You can estimate how much gas things cost by running:
```bash
make snapshot
```

## Testing

- for local anvil
```bash
    make test
```

## Formatting
- to format all the solidity files:
```bash
    make format
```


## Coverage
- To get test coverage report.
```bash
make test-coverage
```




## 🔗 Links
Loved it? lets connect on:

[![twitter](https://img.shields.io/badge/twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://x.com/yugAgarwal29)
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/yug-agarwal-8b761b255/)

