# Contract Deployment Instructions

## Local Network Deployment

The contract has been deployed to the local Hardhat node at:

**Contract Address**: `0x5FbDB2315678afecb367f032d93F642f64180aa3`

### To Redeploy:

1. Make sure Hardhat node is running:
   ```bash
   npx hardhat node
   ```

2. Deploy the contract:
   ```bash
   npx hardhat deploy --network localhost
   ```

3. Update the contract address in:
   - `frontend/components/InheritanceCheckDemo.tsx` (default address)
   - Or create `frontend/.env.local` with:
     ```
     NEXT_PUBLIC_CONTRACT_ADDRESS=<deployed_address>
     ```

## Environment Variables

To use a different contract address, create `frontend/.env.local`:

```env
NEXT_PUBLIC_CONTRACT_ADDRESS=0x5FbDB2315678afecb367f032d93F642f64180aa3
```

## Current Deployment

- **Network**: Localhost (Chain ID: 31337)
- **Contract**: InheritanceRuleCheck
- **Address**: `0x5FbDB2315678afecb367f032d93F642f64180aa3`
- **Deployment File**: `deployments/localhost/InheritanceRuleCheck.json`

