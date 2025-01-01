---
title: "Node Validation"
date: 2024-12-23
tags: [transaction,validation,node,]
---

<head>
<link rel="alternate" type="application/atom+xml" title="{{ site.title }}" href="/feed.xml">
</head>

[If you'd rather listen, here is a podcast of this blog entry](https://lewisbakkero.github.io/tibidabo/audios/Node_Validation.mp3)

[In a previous entry](https://lewisbakkero.github.io/tibidabo/audios/Blockchain_Network_Propagation.mp3), we learned about how transactions are propagated in a network of nodes. Have you ever wondered how exactly those transactions get verified? Imagine it like a group project in college, but instead of professors, there's a whole network of computers making sure everything's legit.

Here's a breakdown of how transactions are validated on a blockchain network, explained in a way that's clear for both techies and, well, everyone else.

## The All-Seeing Eye (of the Node):

Think of a node as a computer on the blockchain network. These nodes are like meticulous accountants, checking every transaction for typos, authenticity, and, most importantly, if the sender has enough "funds" (cryptocurrency) to cover the bill.

Upon receiving a transaction, nodes perform several checks:

1- Syntax and format: Ensure the transaction adheres to the network's protocol rules.

2- Digital signature: Verify the transaction's authenticity using the sender's public key. A node performs these steps:
    a- Receive the transaction data (T) and its digital signature (S)
    b- Extract the sender's public key (Kpub​) from the transaction data
    c- Compute the hash of the transaction data: H(T)
    d- Verify the signature using the public key: V=Verify(H(T),S,Kpub​)

3- Where: V is the verification result (boolean) and Kpub​ is the sender's public key. The Verify function returns true if the signature is valid and false otherwise. If V=1, the node considers the transaction signature valid. If V=0, the transaction is rejected.

4- Input validity: Confirm that the transaction inputs (previous transaction outputs) are unspent and belong to the sender. Let UTXO be the set of all unspent transaction outputs in the blockchain. For a given transaction T, we define the input validity check as follows:

    InputValid(T)=⋀i∈dom(T.in)​IsUnspent(T.in(i))∧SignatureValid(T,i)

    where:

    IsUnspent((T′,j))=(T′,j)∈UTXO

    and

    SignatureValid(T,i)=Verify(H(T),T.wit(i),Kpub​(T.in(i)))

    Here, Kpub​(T.in(i)) represents the public key associated with the output being spent by the i-th input. The InputValid function returns true if and only if all inputs of the transaction T are unspent and have valid signatures.

5- Balance sufficiency: Check if the sender has enough funds to cover the transaction amount and fees.

## Node Verification: Different Strokes for Different Folks

There are different types of nodes, each with their own verification style. Here's a table summarizing them:

| Verification Type        | Description                                                                                                                                                                                              | Examples                                                              |
|--------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------|
| Full Node Verification   | Validates all transactions and blocks independently, storing the entire blockchain history.                                                                                                            | Bitcoin Core (BTC), Geth (ETH), Bitcoin Cash Node (BCH)                |
| Consensus-based Verification | Participates in network consensus to validate transactions and create new blocks.                                                                                                                     | Ethereum 2.0 validators, Cardano stake pool operators                  |
| Smart Contract Execution   | Verifies and executes smart contract operations.                                                                                                                                                           | Ethereum nodes running EVM, Solana validators                         |
| Specialized Verification   | Uses unique protocols or mechanisms specific to certain blockchains.                                                                                                                                  | Solana validators (PoH), Avalanche validators (Snowman)               |
| Delegated Verification   | Relies on a set of trusted nodes for validation.                                                                                                                                                         | XRP validators (UNL), EOS block producers                            |


## Full Monty vs. The Designated Hitters:

Full nodes, the ultimate overachievers, independently validate every single transaction and block, keeping a complete copy of the entire blockchain history (talk about dedication!). This is the most secure approach, but it requires serious computing power (not for the faint of heart).

Then there are consensus-based verification methods like Proof of Stake (PoS) - picture it as a democratic voting system. Nodes stake their cryptocurrency to participate in validating transactions and creating new blocks. The more "skin in the game" (staked crypto), the more influence they have.

## Smart Contracts: The Automated Dealmakers

Some blockchains like Ethereum allow for smart contracts - self-executing agreements that remove the need for intermediaries. Think of it as a vending machine - you put in the money, and the product automatically pops out. Nodes verify and execute these smart contracts, ensuring everything runs smoothly and according to the pre-defined terms.

## Specialized Verification: Thinking Outside the Block

Some blockchains employ unique verification methods. For example, Solana uses Proof of History (PoH) which is like a digital time machine, keeping track of the order in which transactions happened. This helps achieve faster transaction speeds.

## Delegation: Efficiency with a Side of Centralization

Finally, delegated verification systems rely on a set of pre-selected, trusted nodes to perform validation. Think of it as outsourcing the verification task. While this can be more efficient, it introduces a touch of centralization, which goes against the whole "decentralized" philosophy of blockchain.

## The Takeaway:

Blockchain verification is a complex dance of cryptography, consensus mechanisms, and different types of nodes. Understanding these concepts is key to appreciating the security and transparency that blockchain technology offers. So next time you hear about blockchain, remember the network of computers meticulously checking every transaction, ensuring everything is on the up and up!