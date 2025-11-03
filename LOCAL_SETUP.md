# Local Network Setup Guide

## Starting the Local Hardhat Node

To connect your frontend to a local blockchain, you need to start a Hardhat node first.

### Step 1: Start Hardhat Node

Open a terminal in the `pro29` directory and run:

```bash
npx hardhat node
```

This will start a local Ethereum node on `http://127.0.0.1:8545` with chainId `31337`.

The node will display a list of accounts with their private keys. You can use these accounts in MetaMask for testing.

### Step 2: Configure MetaMask

When you connect your wallet to the frontend, MetaMask will automatically prompt you to add the local network. Click "Confirm" to add it.

Alternatively, you can manually add the network in MetaMask:

1. Open MetaMask
2. Click on the network dropdown
3. Select "Add Network" → "Add a network manually"
4. Enter the following details:
   - **Network Name**: Localhost
   - **RPC URL**: http://127.0.0.1:8545
   - **Chain ID**: 31337
   - **Currency Symbol**: ETH

### Step 3: Import Test Account

You can import one of the test accounts from the Hardhat node output:

1. In MetaMask, click the account icon
2. Select "Import Account"
3. Copy one of the private keys from the Hardhat node output
4. Paste it and import

### Step 4: Deploy Contract to Local Network

After the Hardhat node is running, deploy the contract:

```bash
# In a new terminal, still in the pro29 directory
npx hardhat deploy --network anvil
```

Or if you're running `npx hardhat node`, you can use:

```bash
npx hardhat deploy --network localhost
```

Then copy the deployed contract address and update `NEXT_PUBLIC_CONTRACT_ADDRESS` in your frontend `.env.local` file.

## Troubleshooting

### Port Already in Use

If port 8545 is already in use, you can:

1. Stop the existing process using that port
2. Or configure Hardhat to use a different port in `hardhat.config.ts`

### Network Connection Issues

- Make sure the Hardhat node is running before connecting the frontend
- Check that the chainId in MetaMask matches 31337
- Verify the RPC URL is `http://127.0.0.1:8545` (not `localhost:8545`)

### Contract Not Found

- Make sure you've deployed the contract to the local network
- Update the `NEXT_PUBLIC_CONTRACT_ADDRESS` environment variable
- Restart the frontend development server after updating the address
