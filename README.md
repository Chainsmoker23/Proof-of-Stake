# Proof of Stake Blockchain in Go

This project implements a basic Proof of Stake (PoS) blockchain written in Go. It allows validators to participate in block validation and appends validated blocks to the blockchain using a lottery system based on staked tokens. The implementation demonstrates core concepts of blockchain technology, including hashing, consensus, and data integrity.

## Features

- **Genesis Block Creation**: Automatically generates a genesis block at startup.
- **Proof of Stake Consensus**: Validators with more staked tokens have a higher chance of being selected to forge a new block.
- **Blockchain Integrity**: Ensures valid chain structure using hashing and validation mechanisms.
- **Concurrency Handling**: Safely handles concurrent requests using mutex locks.
- **TCP Server**: Operates a TCP server to allow nodes to connect and interact with the blockchain.

## Technologies Used

- **Go**: Main programming language.
- **SHA-256**: Cryptographic hash function for block hashing.
- **JSON**: Serialization for blockchain data.
- **TCP Networking**: Node communication via TCP sockets.
- **Environment Variables**: Configuration management using `.env` files.

## How It Works

1. **Genesis Block**: The blockchain starts with a genesis block containing default values.
2. **Validator Registration**: Nodes register by staking tokens, which determine their chances of winning.
3. **Candidate Blocks**: Validators propose new blocks, which are added to a temporary pool.
4. **Block Validation**: A validator is selected from a lottery pool weighted by their staked tokens, and their block is appended to the blockchain.
5. **Block Transmission**: The updated blockchain is broadcast to all connected nodes.

## Setup and Running

### Prerequisites

- Go (latest version)
- `.env` file containing the server port:
  ```env
  PORT=8080
