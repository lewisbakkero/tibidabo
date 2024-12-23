---
title: "Network Propagation"
date: 2024-12-22
tags: [p2p,network,propagation,]
---

<head>
<link rel="alternate" type="application/atom+xml" title="{{ site.title }}" href="/feed.xml">
</head>

[If you'd rather listen, here is a podcast of this blog entry](https://lewisbakkero.github.io/tibidabo/audios/Blockchain_Network_Propagation.mp3)

[In a previous entry](https://lewisbakkero.github.io/tibidabo/audios/Decoding_Crypto_Transaction_Creation.mp3), we learned about how transactions get created. Not it is time to see how they are propagated (similar to that pizza you ordered moving from the pizzeria to your home).

## How Blockchain Transactions Spread Across the Network

When you make a transaction using a cryptocurrency, your digital wallet broadcasts that transaction to a network of computers called "nodes." These nodes, running blockchain software, verify the transaction. This process of spreading the transaction is called network propagation.
Understanding Peer-to-Peer (P2P) Networks

Blockchain networks are built on peer-to-peer (P2P) architecture. In a P2P network, computers (peers or nodes) communicate directly with each other, without relying on a central server. This decentralization is a key feature of blockchain.

There are three main ways these P2P networks are structured:

    Unstructured P2P: Think of this like a group of friends gossiping. Each person randomly shares information with others they know. This creates a mesh-like network where information spreads widely, but not always efficiently.
    Structured P2P: This is more organized, like a well-structured library. Each piece of information has a specific location, and there's a system to find it quickly. This system often uses something called a Distributed Hash Table (DHT), which is like a decentralized index.
    Hybrid/Optimized P2P: This approach combines the best of both worlds, using smart strategies to share information efficiently while maintaining resilience.

## Comparing P2P Network Types

Here's a table summarizing the key differences:

| Feature             | Unstructured P2P                               | Structured P2P                                 | Hybrid/Optimized P2P                              |
|----------------------|-----------------------------------------------|-------------------------------------------------|----------------------------------------------------|
| Peer Selection      | Random                                        | Deterministic (based on a system like DHT)       | Network-aware (chooses peers strategically)       |
| Propagation Type    | Gossip-based (like spreading rumors)            | Direct (targeted messaging)                       | Optimized gossip (efficient and strategic)        |
| Redundancy          | High (information is widely duplicated)        | Low (less duplication, more efficient routing)   | Moderate (balance between efficiency and redundancy) |
| Network Structure   | Mesh-like (interconnected but not organized) | Organized (using a specific structure like DHT) | Hybrid (combining elements of both)               |
| Routing             | Flooding (sending information to everyone)      | Key-based (finding information based on its ID) | Adaptive (adjusts based on network conditions)    |
| Examples            | Early file-sharing, Ethereum (basic P2P)       | Kadcast, TON DHT                                | Solana (Turbine), Cardano (Ouroboros), Polkadot    |

## How Transactions Propagate

    
1. Transaction Initiation: You initiate a transaction using your cryptocurrency wallet.
2. Broadcasting: Your wallet broadcasts the signed transaction to connected nodes in the network.
3. Validation: These nodes receive the transaction and perform initial checks to make sure it's valid.
4. Propagation: The nodes then spread the transaction to other nodes, using one of the P2P methods described above.


## The Importance of P2P Network Design

The choice of P2P network design has a major impact on a blockchain's performance:

    Unstructured networks are simple and resilient but can struggle with scalability as the network grows.
    Structured networks are more efficient but can be more complex to implement and maintain.
    Hybrid networks aim to strike a balance, offering both efficiency and resilience.

In conclusion, understanding how transactions propagate across a blockchain network is crucial for appreciating the technology's capabilities and limitations. The choice of P2P architecture is a critical design decision that impacts the speed, efficiency, and robustness of any blockchain system.