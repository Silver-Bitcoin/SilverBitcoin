# Silver Bitcoin - sBTC - Digital Silver Universal Blockchain

A revolutionary universal blockchain ecosystem that virtualizes the entire real world on a single platform, built with Rust.

## Overview

Silver Bitcoin (sBTC) is a scalable, secure, and flexible universal blockchain ecosystem that separates concerns into specialized layers. Unlike Bitcoin's limited functionality, sBTC provides a comprehensive operating system for all financial, commercial, and social activities with an attractive silver-themed brand identity.

## Architecture

The blockchain follows a modular architecture with the following layers:

1. **Consensus Layer** - Handles transaction ordering and block production
2. **Data Availability Layer** - Ensures all block data is published and available
3. **Application Layer** - Manages the state machine and business logic
4. **Execution Layer** - Processes smart contracts and transactions
5. **Networking Layer** - Manages peer-to-peer communication
6. **CLI Layer** - Provides command-line tools for node management

## Features

- **Modular Design**: Each layer can be developed, optimized, and upgraded independently
- **High Performance**: Built with Rust for maximum performance and memory safety
- **Scalability**: Data availability sampling enables horizontal scaling
- **Interoperability**: Designed to work with other modular blockchains
- **Flexibility**: Developers can choose which layers to use for their applications
- **Security**: Separation of concerns reduces the attack surface
- **Quantum Resistance**: Implements NIST-standardized CRYSTALS-Dilithium and CRYSTALS-Kyber for protection against quantum computer attacks

## Prerequisites

- Rust and Cargo (latest stable version) - https://www.rust-lang.org/tools/install
- Node.js and npm (for building the WebAssembly frontend) - https://nodejs.org/

## Building the Project

### Build All Crates

```bash
cargo build --release
```

### Build Specific Crate

```bash
cargo build -p sbtc-consensus --release
cargo build -p sbtc-data-availability --release
cargo build -p sbtc-application --release
cargo build -p sbtc-execution --release
cargo build -p sbtc-networking --release
cargo build -p sbtc-cli --release
```

## Running the Node

### Start the Node

```bash
cargo run -p sbtc-cli -- start
```

### Initialize Node Configuration

```bash
cargo run -p sbtc-cli -- init
```

### Send a Transaction

```bash
cargo run -p sbtc-cli -- send-tx --from <sender> --to <receiver> --amount <amount>
```

### Deploy a Smart Contract

```bash
cargo run -p sbtc-cli -- deploy --owner <owner> --code-file <code_file>
```

## Project Structure

```
src/
├── crates/                                # Workspace crates
│   ├── consensus/                         # Consensus layer (Tendermint-like)
│   ├── data-availability/                 # Data availability layer
│   ├── application/                       # Application layer (Cosmos SDK-like)
│   ├── execution/                         # Execution layer (smart contracts)
│   ├── networking/                        # Networking layer (P2P)
│   ├── frontend/                          # Web frontend (Yew framework)
│   └── cli/                               # Command-line interface
├── Cargo.toml                             # Workspace manifest
├── MODULAR_ARCHITECTURE.md                # Modular architecture documentation
├── Project.md                             # Project structure documentation
└── README.md                              # This file
```

## Layer Details

### Consensus Layer
Implements a Tendermint-like consensus algorithm for transaction ordering and block production. Features include:
- Block proposal and validation
- Validator selection
- ABCI++ interface

### Data Availability Layer
Ensures all block data is published and available through:
- Erasure coding (Reed-Solomon)
- Data availability sampling
- Namespace-based data ordering

### Application Layer
Provides the state machine logic with:
- Account and token management
- Transaction processing
- Event emission

### Execution Layer
Handles smart contract execution:
- WASM-based virtual machine
- Gas metering and limits
- Contract deployment and management

### Networking Layer
Manages peer-to-peer communication:
- Node discovery
- Message propagation
- Connection management

### CLI Layer
Command-line tools for node management:
- Node initialization
- Transaction submission
- Query operations

## Quantum-Resistant Cryptography

Silver Bitcoin (sBTC) implements quantum-resistant cryptography using the NIST-standardized CRYSTALS algorithms:

### CRYSTALS-Dilithium
- Used for digital signatures to protect transaction and block integrity
- Provides 128-bit security level against quantum computer attacks
- Integrated into all layers for secure operations

### CRYSTALS-Kyber
- Used for key encapsulation to secure communications
- Provides post-quantum secure key exchange
- Integrated into networking layer for secure peer-to-peer communication

This implementation ensures the blockchain remains secure even against future quantum computer attacks.

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a pull request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
