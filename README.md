# thebabalola-stacks-helpers-deploy

Deploy, verify, and manage Stacks L2 smart contracts.

## Install

```bash
npm install thebabalola-stacks-helpers-deploy
```

## Usage

```typescript
import { deployContract, getContractInfo, isContractDeployed } from "thebabalola-stacks-helpers-deploy";

// Deploy a contract
const result = await deployContract({
  contractName: "my-contract",
  codeBody: "(define-public (hello) (ok \"world\"))",
  senderKey: "your-private-key",
});

// Check if a contract is deployed
const exists = await isContractDeployed("SP...", "contract-name");

// Get contract info
const info = await getContractInfo("SP...", "contract-name");
// Returns: { source, publishHeight, clarityVersion, txId }
```

## API

### `deployContract(options)`
Deploy a Clarity contract to mainnet/testnet. Options:
- `contractName` — Name of the contract
- `codeBody` — Clarity source code
- `senderKey` — Deployer's private key
- `network?` — Stacks network
- `nonce?` — Transaction nonce
- `fee?` — Transaction fee

### `getContractInfo(contractAddress, contractName, networkUrl?)`
Fetch deployed contract information.

### `isContractDeployed(contractAddress, contractName, networkUrl?)`
Check if a contract exists on-chain.

## License

MIT

## Author

thebabalola
