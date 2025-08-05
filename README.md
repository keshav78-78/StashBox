📦 StashBox: A Peer-to-Peer File Storage Network in Go

A decentralized, content-addressable storage network built from the ground up in Go to demonstrate core distributed systems concepts.

────────────────────────────────────────────────────────────

Project Overview

StashBox is a peer-to-peer file storage system that allows multiple nodes to form a distributed network for storing and retrieving files. The system is built on a custom TCP transport layer and uses content-addressable storage (CAS) to ensure data integrity and eliminate duplicates.

When a file is requested from a node that doesn't have it locally, the node automatically broadcasts a request to its peers, retrieves the file, and serves it to the user.

This project showcases hands-on implementation of networking, concurrency, and distributed systems architecture in Go.

────────────────────────────────────────────────────────────

Key Features

• Decentralized P2P Network  
  Nodes can bootstrap their connection using any existing member of the network, forming a resilient mesh for data exchange.

• Content-Addressable Storage  
  Files are stored and addressed by the SHA1 hash of their content, guaranteeing data integrity and preventing duplicate storage.

• Automatic File Fetching  
  Nodes intelligently fetch files from peers. If a requested file doesn't exist locally, the node broadcasts a request and retrieves it from the network.

• Modular Architecture  
  The codebase is structured into clearly separated layers, including a `p2p` transport layer and a `store` layer for file system operations.

────────────────────────────────────────────────────────────

Running the Simulation

The `main.go` file is configured to simulate a three-node network that demonstrates core functionality.

Prerequisites

• Go 1.20 or later

Steps

1. Clone the repository

   git clone https://github.com/keshav78-78/StashBox.git  
   cd StashBox

2. Run the network simulation

   make run

This will build and launch three nodes, connect them, and run a demo where one node stores a file and another retrieves it from the network.

────────────────────────────────────────────────────────────

Architectural Components

• FileServer  
  Orchestrates high-level logic at each node: managing peer connections, local file storage, and broadcasting messages.

• TCPTransport  
  Handles raw TCP communication between peers and delivers messages to upper layers via channels.

• Store  
  Manages the content-addressable storage engine, handling file writes, reads, and SHA1-based retrieval.

────────────────────────────────────────────────────────────

Author

Keshav Kapoor  
GitHub: github.com/keshav78-78

────────────────────────────────────────────────────────────
