# Boiler-Blockchain-Project

We chose the Open Track and implemented a custom smart contract that enables collaborative expense sharing on Ethereum. Users can create shared expense bills with a funding target, and contributors can send ETH toward that target. The contract optionally issues ERC-20 “receipt tokens” to contributors and allows contributors to reclaim funds if a deadline passes without reaching the goal. Once a bill is fully funded, the designated payee can securely withdraw the collected amount. Additionally, the system includes an optional reward pool that the contract owner can seed and distribute, which further motivates participation.

## Frontend (no build step)
`frontend/index.html` is a static UI that uses the local `ethers` UMD bundle.
1) Deploy ExpenseShare + ReceiptToken and note the addresses.
2) Serve the repo root (examples: `python3 -m http.server 8000` or `npx http-server`) and open `http://localhost:8000/frontend/index.html`.
3) Click “Connect Wallet”, then “Switch to Sepolia”, paste your ExpenseShare and ReceiptToken addresses, and use the panels to create bills, contribute, withdraw/refund, and inspect token/bill info.

## Hardhat network (Sepolia)
`hardhat.config.ts` defaults to Sepolia. Add a `.env` file:
```
SEPOLIA_RPC_URL=https://sepolia.infura.io/v3/your-key
PRIVATE_KEY=0xyourprivatekey
```
Deploy against Sepolia with `npx hardhat run scripts/deploy.js --network sepolia` (or run locally with `--network hardhat`). Keep secrets out of git.
