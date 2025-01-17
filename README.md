#project-deploy

## install
### cli usage
```sh
npm i -g @leofcoin/project-deploy
```

### module usage
```sh
npm i --save @leofcoin/project-deploy
```
## examples
### config
project-deploy.config.json
```json
{
  "deploy": {
    "contracts/TestContract.sol": ["0x4eCfe05bAe2535f13a92A16E60Be1b68BdEDEDb7"]
  },
  "autoFix": true,
  "license": "MIT",
  "networks": {
    "binance-smartchain-testnet": {
      "rpcUrl": "https://data-seed-prebsc-1-s1.binance.org:8545",
      "chainId": 97
    },
    "binance-smartchain": {
      "rpcUrl": "https://bsc-dataseed.binance.org",
      "chainId": 56
    }
  }
}
```

### .env
```
binance-smartchain-testnet_PRIVATE_KEY="...."

```

#### using config file in project folder and cli
```sh
project-deploy network binance-smartchain-testnet
```


#### using config file in project and module deployment for more advanced setups

```js
import deploy from 'project-deploy.js';

const testContract = await deploy('contracts/TestContract.sol', ["0x4eCfe05bAe2535f13a92A16E60Be1b68BdEDEDb7"])

const anotherContract = await deploy('contracts/AnotherContract.sol', [testContract.address])
```
