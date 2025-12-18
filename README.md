# Base Chronicle (Built for Base)


Base Chronicle is a browser-based tool designed to facilitate Base chain monitoring and wallet connection, providing real-time read-only access to blockchain data, including block stats and address balances using Coinbase Wallet SDK and Base tooling.

---

## Base ecosystem alignment

Built for Base.

Supported networks:
- Base Mainnet  
  chainId (decimal): 8453  
  Explorer: https://basescan.org  

- Base Sepolia  
  chainId (decimal): 84532  
  Explorer: https://sepolia.basescan.org  

The application explicitly targets Base networks by chainId and uses official Base RPC endpoints.

---

## What the script does

The app.base-chronicle.ts script provides an in-browser interface that:

1) Connects a wallet using Coinbase Wallet SDK  
2) Reads and validates the active chainId  
3) Performs read-only Base RPC queries:
   - latest block number  
   - ETH balance of the connected address  
4) Fetches detailed block stats (timestamp, gas usage)  
5) Allows ETH balance checks for arbitrary addresses  
6) Outputs Basescan links for verification  

All interactions are read-only. No transactions are broadcast.

---

## Repository structure

- app.base-chronicle.ts  
  Browser-based script that connects to a wallet, toggles Base networks, and inspects onchain data.

- contracts/  
  Solidity contracts deployed to Base Sepolia for testnet validation:
  - errors.sol  — defines custom error types to handle issues
  - AddressBookFactory.sol  — stores addresses (e.g., wallet addresses, contract addresses) in a list or mapping
  - Minimaltoken.sol — implements basic token functionality

- package.json  
  Dependency manifest including Coinbase SDKs and multiple repositories from the Base GitHub organization.

- README.md  
  Technical documentation, Base references, licensing, and testnet deployment records.

---

## Libraries used

- @coinbase/wallet-sdk  
  Wallet connection layer compatible with Coinbase tooling and Base accounts.

- viem  
  RPC client used for Base reads and block inspection.

- Coinbase GitHub repositories  
  Included as dependencies to reference the broader Coinbase open-source ecosystem.

- Base GitHub repositories  
  Included as dependencies to document linkage with Base tooling and infrastructure.

---

## Installation and execution

Install dependencies using Node.js.  
Serve the project with a modern frontend dev server and open the page in a browser.

Expected result:
- Connected address printed with Basescan link  
- Active chainId displayed (8453 or 84532)  
- Read-only Base RPC data displayed  
- Block stats available on demand  

---

## License

MIT License

Copyright (c) 2025 YOUR_NAME

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

---

## Author

GitHub: https://github.com/premix-masques

Email: ypremix.masques_0c@icloud.com 

Public contact: https://x.com/Daniel84748392

---

## Testnet Deployment (Base Sepolia)

As part of pre-production validation, one or more contracts may be deployed to the Base Sepolia test network to confirm correct behavior and tooling compatibility.

Network: Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

Contract errors.sol address:  
0xdb6098d151b455511277017eab2c4c7a37c56546

Deployment and verification:
- https://sepolia.basescan.org/address/0xdb6098d151b455511277017eab2c4c7a37c56546
- https://sepolia.basescan.org/0xdb6098d151b455511277017eab2c4c7a37c56546/0#code  

Contract AddressBookFactory.sol  address:  
0x77620565335ec23af3bdcfdbff40049e37662bc6 

Deployment and verification:
- https://sepolia.basescan.org/address/0x77620565335ec23af3bdcfdbff40049e37662bc6 
- https://sepolia.basescan.org/0x77620565335ec23af3bdcfdbff40049e37662bc6/0#code  

Contract Minimaltoken.sol address:  
0xa0b44278c3823d7f4b01c90541293c9d479854a2

Deployment and verification:
- https://sepolia.basescan.org/address/0xa0b44278c3823d7f4b01c90541293c9d479854a2
- https://sepolia.basescan.org/0xa0b44278c3823d7f4b01c90541293c9d479854a2/0#code  

These testnet deployments provide a controlled environment for validating Base tooling, account abstraction flows, and read-only onchain interactions prior to Base Mainnet usage.
