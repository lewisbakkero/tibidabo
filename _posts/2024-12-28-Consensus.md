---
title: "Consensus"
date: 2024-12-28
tags: [transaction,consensus,work,stake]
---

<head>
<link rel="alternate" type="application/atom+xml" title="{{ site.title }}" href="/feed.xml">
</head>

[If you'd rather listen, here is a podcast of this blog entry](https://lewisbakkero.github.io/tibidabo/audios/Consensus.mp3)

[In a previous entry](https://lewisbakkero.github.io/tibidabo/audios/Mempool.mp3), we understood how the mempool serves as a staging area for transactions. Now, how do separated nodes with no central authority agree on whether a transaction is legit? 

ver tried to decide where to eat with a group of friends? Multiply that by thousands of computers scattered across the globe, and you've got the delightful problem of blockchain consensus. It's like herding cats, but with more cryptography and less fur.

In the world of blockchain, "consensus" means everyone agrees on which transactions are valid. Without it, chaos reigns, and your digital money might as well be Monopoly money (which, let's be honest, is already pretty close).

So, how do these digital cats reach an agreement? Let's break it down (with a dash of humor, of course).

Imagine a bunch of gossipy computers (we'll call them "nodes") hanging out in a digital coffee shop. Someone walks in and tries to pay for a virtual latte with a digital coin. All the nodes need to agree if that coin is real and hasn't been spent already.

This process can be formalized using some fancy math (see Appendix for the full brain-buster), but the gist is this:

    Nodes: The gossips in our coffee shop.
    Transactions: The juicy gossip (like who bought what).
    Agreement: Everyone agreeing on the latest gossip.

This agreement is reached in rounds. In each round, the nodes check if a transaction is valid. If enough nodes agree, the transaction is added to a "block," which is then chained to the existing history (hence, "blockchain"). Think of it as adding a new chapter to the gossip book.

But here's the kicker: there are many ways for these digital gossips to reach an agreement. It's like having different rules for the coffee shop:

| Family            | Consensus Protocol          | Pros                                                                                                    | Cons                                                                                                        | Cryptocurrency/Platforms |
| :---------------- | :-------------------------- | :----------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------------------- | :------------------------- |
| Proof-based       | Proof of Work (PoW)         | - High security<br>- Decentralized<br>- Battle-tested                                                  | - Energy-intensive<br>- Slow transaction speed<br>- Potential for 51% attacks                               | Bitcoin                    |
|                   | Proof of Stake (PoS)        | - Energy-efficient<br>- Faster transactions<br>- Lower entry barrier                                   | - Potential centralization<br>- "Nothing at stake" problem<br>- Less battle-tested than PoW                 | Decred, Peercoin, Ethereum (planned) |
|                   | Delegated Proof of Stake (DPoS) | - High scalability<br>- Fast transactions<br>- Energy-efficient                                       | - More centralized<br>- Potential for collusion among delegates                                              | EOS, Tron                  |
| Voting-based      | Practical Byzantine Fault Tolerance (PBFT) | - High transaction throughput<br>- Low latency<br>- No forking                                       | - Limited scalability<br>- Requires known validators                                                      | Hyperledger Fabric         |
|                   | Federated Byzantine Agreement (FBA)      | - Fast consensus<br>- Flexible trust<br>- Energy-efficient                                         | - Reliance on validator reputation<br>- Potential for centralization                                       | Stellar                    |
| Hybrid/Alternative | Proof of Authority (PoA)      | - High performance<br>- Scalability<br>- Energy-efficient                                               | - Centralized<br>- Requires trust in authorities                                                           | Ethereum (private networks) |
|                   | Proof of Elapsed Time (PoET)  | - Energy-efficient<br>- Scalable                                                                     | - Requires specialized hardware<br>- Potential for hardware vulnerabilities                                | Hyperledger Sawtooth       |
|                   | Istanbul Byzantine Fault Tolerant (IBFT) | - Immediate finality<br>- High throughput<br>- No forking                                       | - Limited scalability<br>- Requires known validators                                                      | Quorum                     |
|                   | Raft                        | - Simple implementation<br>- High performance<br>- Well-understood                                    | - Not Byzantine fault-tolerant<br>- Requires trusted network                                               | Quorum                     |

This table is like a menu at our digital coffee shop, offering different "flavors" of consensus. Some are secure but slow (like ordering a complicated pour-over), while others are fast but potentially less secure (like grabbing a quick espresso).

The 3 main flavors are: Proof-based, Voting-based, and Hybrid/Alternative, highlighting the diverse approaches to achieving consensus in distributed systems. As evident from Table \ref{tab:consensus_protocols}, each consensus protocol comes with its own set of advantages and drawbacks. Proof-based mechanisms like Proof of Work (PoW) and Proof of Stake (PoS) offer high security and decentralization but face challenges in energy efficiency and scalability. Voting-based protocols such as Practical Byzantine Fault Tolerance (PBFT) and Federated Byzantine Agreement (FBA) provide faster transaction finality but may sacrifice some degree of decentralization. The Hybrid/Alternative category showcases innovative approaches that attempt to balance the trade-offs inherent in consensus mechanisms. 

So, the next time you hear about blockchain consensus, remember the gossipy computers in the digital coffee shop, trying to agree on the latest news. It might sound complicated, but it's really just a high-tech version of deciding where to eat with friends – just with higher stakes (and hopefully less arguing).


# Appendix: The Mathy Bits (For the Truly Curious)

Here's a somewhat formal definition of the consensus framework mentioned earlier. Don't worry if it looks like alien hieroglyphics; it's just a way to express the agreement process in mathematical terms.

    N: Set of all nodes in the network.
    T: Set of all pending transactions.
    Cr​(ni​,tj​): Function that equals 1 if node ni​ accepts transaction tj​ in round r, and 0 otherwise.
    Ar​(tj​): Agreement level for transaction tj​ in round r: Ar​(tj​)=∣N∣1​∑i=1k​Cr​(ni​,tj​) (Equation 1)
    θ: Predefined consensus threshold.
    Br​: Set of transactions in the new block for round r: Br​=tj​∈T∣Ar​(tj​)≥θ (Equation 2)
    B: The blockchain. The blockchain is updated as: Br+1​=Br​∪Br​ (Equation 3)

In essence, Equation 1 calculates how many nodes agree on a transaction. Equation 2 selects the transactions that meet the agreement threshold. And Equation 3 adds the new block of agreed-upon transactions to the blockchain.