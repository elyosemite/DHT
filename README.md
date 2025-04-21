# Distributed Hash Table (DHT) Implementation in C

A lightweight, peer-to-peer (P2P) Distributed Hash Table (DHT) implementation in C, designed to enable decentralized data storage and retrieval across distributed nodes in a network.

## Overview

This project implements a Distributed Hash Table (DHT) to facilitate efficient key-value storage and lookup in a peer-to-peer network. The DHT leverages consistent hashing to distribute data across nodes, ensuring scalability and fault tolerance. Nodes can dynamically join or leave the network, and the system automatically adjusts to maintain data consistency and availability.

## Features

- **Node Management**: Nodes can dynamically join or leave the network.
- **Key-Value Storage**: Store and retrieve data using unique keys.
- **Distributed Lookup**: Efficiently locate nodes responsible for specific keys.
- **Data Replication**: Automatic replication of data across multiple nodes for fault tolerance.
- **Fault Tolerance**: Handles node failures gracefully by redistributing data.
- **CLI Interface**: Simple command-line interface to interact with nodes.

## Installation

### Prerequisites

- A C compiler (e.g., `gcc` or `clang`)
- `make` (for building)
- Libraries: OpenSSL (for SHA-1 hashing, if used)

### Build Instructions

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/dht-implementation.git
   cd dht-implementation
   ```

2. Compile the project:
   ```bash
   make
   ```

3. The executable `dht-node` will be generated in the `bin/` directory.

## Usage

### Starting a Node

Run a node with a specified port and optional bootstrap node address:
```bash
./bin/dht-node --port 5000 --bootstrap 192.168.1.2:5000
```

### CLI Commands

Interact with a running node via the command-line interface:
- `JOIN <ip:port>`: Join the network using a bootstrap node.
- `LEAVE`: Gracefully leave the network.
- `PUT <key> <value>`: Store a key-value pair.
- `GET <key>`: Retrieve the value associated with a key.
- `INFO`: Display node information (e.g., neighbors, stored keys).

Example:
```bash
> PUT name Alice
Stored key "name" on node 192.168.1.2:5000.

> GET name
Value: Alice
```

## Configuration

Modify `config.h` or use a configuration file to adjust settings:
- `MAX_NEIGHBORS`: Maximum number of neighboring nodes.
- `REPLICATION_FACTOR`: Number of nodes to replicate data on.
- `STABILIZE_INTERVAL`: Time interval (in seconds) for network stabilization.

Example configuration file (`config.ini`):
```ini
port = 5000
bootstrap = 192.168.1.2:5000
replication = 3
```

## Contributing

Contributions are welcome! Please follow these steps:
1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/your-feature`).
3. Commit your changes (`git commit -am 'Add your feature'`).
4. Push to the branch (`git push origin feature/your-feature`).
5. Open a Pull Request.

Ensure your code adheres to the project's coding style and includes relevant tests.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

## Acknowledgments

- Inspired by the Chord Protocol and Kademlia DHT.

## Contact

For questions or feedback, contact [Your Name](mailto:your.email@example.com) or open an issue on GitHub.