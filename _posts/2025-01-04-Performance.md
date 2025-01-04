---
title: "Performance"
date: 2025-01-04
tags: [performance,overview]
---

<head>
<link rel="alternate" type="application/atom+xml" title="{{ site.title }}" href="/feed.xml">
</head>

[If you'd rather listen, here is a podcast of this blog entry](https://lewisbakkero.github.io/tibidabo/audios/Performance.mp3)

# Cryptocurrency Performance Metrics: A Comprehensive Guide

In the fast-paced world of cryptocurrencies, understanding performance metrics is crucial for investors and enthusiasts alike. Let's dive into the key dimensions that define a cryptocurrency's efficiency and effectiveness.

## Block Time: The Heartbeat of Blockchain

Block time is the average interval between the creation of new blocks in a blockchain. It's a critical metric that directly impacts transaction speed and network responsiveness.

## Transactions Per Second (TPS): Scalability in Action

TPS represents the maximum number of transactions a network can process per second. It's a theoretical measure calculated by dividing the number of transactions per block by the block time. Just for reference, the US requires a few thousand TPS for all credit card transactions nationally.

## Deposit Times: From Wallet to Exchange

Deposit times refer to how long it takes for funds to become available in an exchange account after initiating a transfer. This can vary significantly between cryptocurrencies and exchanges. See [Kraken's here](https://support.kraken.com/hc/en-us/articles/203325283-Cryptocurrency-deposit-processing-times)

## Transaction Fees: The Cost of Doing Business

Transaction fees are the costs associated with making a transaction on the network. These fees can be dynamic, often calculated based on network congestion and the complexity of the transaction.

## Initial Token Allocation: Distribution at Launch

This metric refers to how tokens were initially distributed when the cryptocurrency was launched. It includes factors like the percentage allocated to founders, early investors, and public sales.

<img src="https://lewisbakkero.github.io/tibidabo/images/initial_token_allocationjpg" alt="Initial token allocation for main Cryptocoins" width="600"/>

Image from [Messari](https://www.messari.io/) and summary from [Ryan Watkins' X post](https://twitter.com/RyanWatkins_/status/1394283802009145348)

## Percentage of Circulating Supply Sold Publicly

This metric indicates what portion of the total circulating supply was made available for public purchase, typically through initial coin offerings (ICOs) or similar events.

## Costs of Running a Node/Validator

This represents the financial investment required to participate in network validation, including hardware, electricity, and bandwidth costs. Coins can be more performing if they can run at reasonable prices (<$10k/year) on ever increasing energy costs and without needing specialized hardware.

Solana needs high spec server/instance. Throwing in its voting fees, and inflation, you need to have 65–100k SOL (~$15M) at stake to have a profitable node as the cost of consensus/vote transactions (1,1 SOL/day/validator) does not scale. Beware of the 'rule of thumb' maths. 

## Additional Performance Metrics

- **Network Hash Rate:** For proof-of-work cryptocurrencies, this measures the total computational power securing the network.
- **Active Addresses:** The number of unique addresses participating in transactions over a given period, indicating network activity and adoption.
- **Market Capitalization:** The total value of all tokens in circulation, calculated by multiplying the circulating supply by the current price.

# Comparative Analysis of Top 20 Cryptocurrencies by Market Cap

| Cryptocurrency | Block Time | TPS (Max) | Avg. Deposit Time | Avg. Transaction Fee | Node/Validator Cost (USD/year) | Hash Rate | Active Addresses | Market Cap |
|----------------|------------|-----------|-------------------|----------------------|--------------------------------|-----------|------------------|------------|
| Bitcoin (BTC)  | 10 min     | 7         | 1-6 confirmations  | Variable             | $4,500-$5,600                  | 441 EH/s   | 1M daily         | $1.1T      |
| Ethereum (ETH) | 12 sec     | 15-30     | 12 confirmations   | Variable (gas-based) | $60,000+                       | N/A       | 500K daily       | $250B      |
| Binance Coin (BNB) | 3 sec  | 1000      | 12 confirmations   | Variable             | Data not available             | N/A       | Data not available| $50B       |
| Cardano (ADA)  | 20 sec     | 250       | 24 confirmations   | Variable             | Data not available             | N/A       | Data not available| $15B       |
| Solana (SOL)   | 400-800ms  | 50,000    | 1 confirmation     | Variable             | $54,600-$63,700                | N/A       | Data not available| $30B       |
| XRP            | 3-5 sec    | 1500      | 1 confirmation     | Fixed, very low      | Data not available             | N/A       | Data not available| $120B      |
| Polkadot (DOT) | 6-12 sec   | 1000      | 2 confirmations    | Variable             | Data not available             | N/A       | Data not available| $14B       |
| Dogecoin (DOGE)| 1 min      | 33        | Variable           | Variable             | Data not available             | N/A       | Data not available| $46B       |
| Polygon (MATIC)| 2 sec      | 65,000    | 24 confirmations   | Variable             | Data not available             | N/A       | Data not available| $15B       |
| Litecoin (LTC) | 2.5 min    | 56        | Variable           | Variable             | Data not available             | N/A       | Data not available| $9B        |

Note: The table above provides a snapshot of key metrics for the top cryptocurrencies. Due to the dynamic nature of these metrics and limited data availability, some cells may contain "Variable" or "Data not available." Always refer to the most current data from official sources when making investment decisions.

Based on the performance metrics and characteristics of the top cryptocurrencies, we can broadly categorize them into three groups:

## 1. High-Security, Slower Transaction Coins

**Examples:** Bitcoin (BTC), Litecoin (LTC)

**Characteristics:**
- Longer block times (1-10 minutes)
- Lower TPS (7-56)
- High security and decentralization
- Established market presence

**Use Cases:**
These cryptocurrencies are best suited for:
- Store of value
- Large value transfers
- Long-term investments
- Situations where security is prioritized over speed

Bitcoin, often called "digital gold," excels in this category. Its widespread adoption makes it good for preserving wealth and making significant transfers where transaction speed is less critical.

## 2. Fast, High-Throughput Coins

**Examples:** Solana (SOL), Ripple (XRP), Polygon (MATIC)

**Characteristics:**
- Very short block times (milliseconds to a few seconds)
- High TPS (1,500-65,000)
- Optimized for speed and scalability
- Often sacrifice some degree of decentralization for performance

**Use Cases:**
These cryptocurrencies are well-suited for:
- Micro-transactions
- DeFi applications
- High-frequency trading
- Payment systems requiring near-instant settlements

This group, with their fast transactions, is particularly useful for decentralized applications that require high throughput, such as decentralized exchanges or gaming platforms.

## 3. Balanced, Multi-Purpose Coins

**Examples:** Ethereum (ETH), Cardano (ADA), Binance Coin (BNB)

**Characteristics:**
- Moderate block times (3-20 seconds)
- Moderate to high TPS (15-1000)
- Smart contract capabilities
- Balance between security, speed, and functionality

**Use Cases:**
These cryptocurrencies are versatile and can be used for:
- Smart contracts and dApps
- NFT creation and trading
- Tokenization of assets
- Balanced approach to transactions and decentralized applications

Ethereum, the leader in this category, provides a robust platform for a wide range of decentralized applications, from DeFi protocols to complex smart contracts, balancing functionality with reasonable transaction speeds.

Each category offers distinct advantages, and the choice of cryptocurrency depends on the specific use case, prioritizing factors such as security, speed, or versatility as needed for the application or investment strategy.



## References

1. PK An Excel Expert. (2024). Blockchain & Cryptocurrency KPI Dashboard in Excel. [https://www.pk-anexcelexpert.com/blockchain-cryptocurrency-kpi-dashboard-in-excel/](https://www.pk-anexcelexpert.com/blockchain-cryptocurrency-kpi-dashboard-in-excel/)
2. River Financial. (n.d.). Bitcoin Investment Performance Metrics. [https://river.com/learn/bitcoin-investment-performance-metrics/](https://river.com/learn/bitcoin-investment-performance-metrics/)
3. Hyperledger. (2017). Hyperledger Blockchain Performance Metrics White Paper. [https://www.lfdecentralizedtrust.org/learn/publications/blockchain-performance-metrics](https://www.lfdecentralizedtrust.org/learn/publications/blockchain-performance-metrics)
4. Zerocap. (2024). On-chain Bitcoin Metrics: The Main References. [https://zerocap.com/insights/snippets/on-chain-bitcoin-metrics/](https://zerocap.com/insights/snippets/on-chain-bitcoin-metrics/)
