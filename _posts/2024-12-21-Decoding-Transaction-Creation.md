---
title: "Decoding Transaction Creation"
date: 2024-12-21
tags: [transactions,technology,creation,Merkle,]
---

<head>
<link rel="alternate" type="application/atom+xml" title="{{ site.title }}" href="/feed.xml">
</head>

[If you'd rather listen, here is a podcast of this blog entry](https://lewisbakkero.github.io/tibidabo/audios/Decoding_Crypto_Transaction_Creation.mp3)


[In a previous entry](https://lewisbakkero.github.io/tibidabo/audios/Cryptocurrencys_Genesis_A_Technological_History.mp3), we looked back at how blockchains have been cooking over quite some time. Here, we demistify what is going on in blockchains today. 

Let us think of cryptocurrencies like digital cash – except instead of stuffing it under your mattress (which, let's be honest, is a terrible investment strategy), it lives on a fancy, shared digital ledger called a "blockchain." This ledger is like a giant, public spreadsheet that everyone can see, making it super transparent (unless you're into shady backroom deals, in which case, this might not be for you).

This blockchain thingy is a type of Distributed Ledger Technology (DLT). Imagine a group project where everyone has a copy of the same document. If someone makes a change, everyone else's copy updates. That's DLT in a nutshell, but way more secure (and hopefully with fewer arguments than your average school parents Whatsapp group).

Here's the breakdown of what makes a crypto tick:

* Transactions: These are the actual transfers of digital value. Think of it like sending a bank payment, but with more jargon.
* Blocks: Transactions get bundled together into "blocks," like packing shipments at an Amazon warehouse.
* Consensus Mechanisms: This is how everyone agrees on what's actually in the ledger, preventing digital shenanigans. It's like having a really strict referee for a digital soccer match.
* Cryptographic Primitives: Fancy words for the security measures that keep everything safe and sound. Think digital locks and keys.

Now, let's dive into how a crypto transaction actually happens (don't worry, we'll keep the math to a minimum... mostly). There are three main phases: creation, broadcasting, and confirmation. Imagine it like ordering a pizza: you create the order, the restaurant sends it out for delivery, and then you confirm you received it (and hopefully haven't been charged for extra anchovies you didn't order).

<img src="https://lewisbakkero.github.io/tibidabo/images/transaction_stages.jpg" alt="Stages in a blockchain transatcion" width="300"/>

### The Math Part (Just a Little, I Promise)

This is where things get a tad technical, but bear with me. You use your crypto "wallet" (like a digital bank account) to start a transaction. The wallet prepares the details: who's sending it, who's receiving it, how much is being sent, and the "transaction fee" (like a delivery charge for your digital pizza).

We can represent this with a simple (yes, really!) formula:

T=(As​,Ar​,V,F)

Where:

    As​ = Sender's address (your digital mailbox)
    Ar​ = Recipient's address (their digital mailbox)
    V = Value (amount of crypto being sent)
    F = Transaction fee (the cost of doing business)

Then, your wallet uses a "private key" (like a super-secret password) to create a digital signature:

S=Sign(H(T),K_priv)

Where H(T) is the hash of the transaction data.

(Don't worry too much about the hash, it's just a way of scrambling the data to make it extra secure.)

### UTXO vs. Account-Based Models: It's Like Cash vs. Bank Accounts

There are two main ways of handling transactions:

1- UTXO (Unspent Transaction Output): Think of this like cash. Every transaction uses up previous "unspent" amounts and creates new ones. It's great for privacy and can handle lots of transactions at once.

2- Account-Based: This is more like a traditional bank account, where you have a running balance. It's simpler to understand, but can be less private and a bit slower.

Here's a handy table to compare the two:

| Feature           | UTXO-Based                                  | Account-Based                           |
|-------------------|----------------------------------------------|------------------------------------------|
| Accounting Method | Tracks individual transaction outputs         | Maintains account balances                |
| State Management  | Stateless                                    | Stateful                                   |
| Privacy           | Enhanced (generating new addresses)          | Less private                             |
| Scalability       | Supports parallel processing                  | Sequential processing                     |
| Smart Contracts   | Limited (with exceptions)                    | Well-suited                               |
| Ease of Use       | Less intuitive                             | More familiar                            |
| Microtransactions | Efficient                                    | Challenging                              |

So this is it for today, in future posts we will continue detailing steps of the lifecycle. 