# Voting Application via Blockchain

A secure and transparent blockchain-based voting system built with Solidity and Truffle. This smart contract serves as the **backbone infrastructure** for decentralized voting applications, ensuring immutability, transparency, and integrity in the voting process.

## Overview

This project implements a smart contract voting system that leverages blockchain technology to create a tamper-proof voting mechanism. The contract manages candidates, tracks votes, and prevents double-voting through wallet address verification.

## Features

- **Immutable Voting Records**: All votes are permanently recorded on the blockchain
- **Transparent Results**: Vote counts are publicly verifiable and auditable
- **Double-Vote Prevention**: Each wallet address can only vote once
- **Secure Candidate Management**: Only the contract owner can add candidates
- **Decentralized**: No central authority can manipulate results
- **Gas Efficient**: Optimized for minimal transaction costs

## Technology Stack

- **Solidity** `>=0.4.22 <0.9.0` - Smart contract programming language
- **Truffle** - Development framework for Ethereum
- **Ganache** - Local blockchain for development and testing
- **Web3.js** - JavaScript library for blockchain interaction
- **Node.js** - JavaScript runtime environment

## Prerequisites

Before you begin, ensure you have the following installed:

- [Node.js](https://nodejs.org/) (v14.x or higher)
- [Ganache](https://trufflesuite.com/ganache/) - Local blockchain
- [Truffle](https://trufflesuite.com/truffle/) - Development framework

```bash
# Install Truffle globally
npm install -g truffle
```

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/WhyN0t101/voting-app.git
   cd Voting-Application-via-Blockchain
   ```

2. **Install dependencies** (if any)
   ```bash
   npm install
   ```

3. **Start Ganache**
   - Open Ganache and create a new workspace
   - Set RPC Server to `HTTP://127.0.0.1:7546`
   - Save the workspace

4. **Compile the smart contract**
   ```bash
   cd blockchain
   truffle compile
   ```

5. **Deploy to local blockchain**
   ```bash
   truffle migrate --network development
   ```
   
   > **Note**: After migration, copy the deployed contract address for use in your frontend application.

## Usage

### Smart Contract Functions

#### `addCandidate(string _name)`
- **Access**: Only contract owner
- **Purpose**: Add a new candidate to the election
- **Parameters**: 
  - `_name`: Name of the candidate

#### `vote(uint _candidateId)`
- **Access**: Any address (one vote per address)
- **Purpose**: Cast a vote for a candidate
- **Parameters**: 
  - `_candidateId`: ID of the candidate (starts from 1)
- **Requirements**:
  - Address must not have voted before
  - Candidate ID must be valid

#### View Functions
- `candidates(uint _id)`: Get candidate details (id, name, voteCount)
- `voters(address _address)`: Check if an address has voted
- `candidatesCount()`: Get total number of candidates
- `owner()`: Get contract owner address

### Interacting with the Contract

Using Web3.js:

```javascript
const contractAddress = "YOUR_DEPLOYED_CONTRACT_ADDRESS";
const contractABI = require('./build/contracts/VotingSystem.json').abi;

const contract = new web3.eth.Contract(contractABI, contractAddress);

// Get all candidates
const count = await contract.methods.candidatesCount().call();
for (let i = 1; i <= count; i++) {
    const candidate = await contract.methods.candidates(i).call();
    console.log(`${candidate.name}: ${candidate.voteCount} votes`);
}

// Cast a vote
await contract.methods.vote(1).send({ from: yourWalletAddress });
```



## Security Features

- **Owner-only candidate management**: Prevents unauthorized modification of candidates
- **One vote per address**: Enforced through mapping-based tracking
- **Input validation**: All functions validate parameters before execution
- **Transparent state**: All votes and candidates are publicly readable

## Testing

Run the test suite (when tests are added):

```bash
cd blockchain
truffle test
```

## Network Configuration

The project is configured to work with:
- **Development**: Local Ganache instance on `127.0.0.1:7546`
- **Compiler**: Solidity v0.8.0

To deploy to other networks (testnet/mainnet), update `truffle-config.js` accordingly.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.


## Acknowledgments

- Built with [Truffle Suite](https://trufflesuite.com/)
- Ethereum blockchain platform
- Solidity programming language

---

**Note**: This repository contains the blockchain backbone (smart contracts) for a voting application. Frontend implementations can be built using Web3.js, React, Vue.js, or any web framework of your choice.
