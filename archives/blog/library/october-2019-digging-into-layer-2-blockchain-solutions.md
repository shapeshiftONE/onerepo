---
title: Digging into Layer 2 Blockchain Solutions
description: Learn about the tech striving to solve crypto’s scaling issues.
published: false
date: 2021-12-20T23:02:33.907Z
tags: library, bitcoin, cryptocurrency, ethereum, needs-review
editor: markdown
dateCreated: 2021-12-20T23:02:33.907Z
---

# Digging into Layer 2 Blockchain Solutions

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9f294424536954b69806bd_1_L8GpHTyR1-JRyyo31JzZeQ.png)

**Blockchain** geeks and crypto enthusiasts alike often use the terms layer 2 and lightning network interchangeably when referring to blockchain scalability solutions. The truth is that these terms are ***not*** interchangeable.<br/> 

## Beyond Bitcoin: Scaling with Layer 2

The term **layer 2** refers to a second layer of coding that exists on top of a blockchain’s original coding structure. This allows a decentralized blockchain to evolve and deal with a handful of issues such as:

* Scaling payment volume and speed
* Scaling the creation and execution of smart contracts
* Performing off-chain computations

Bitcoin’s Lightning Network upgrade is specific to scaling payments, but it‘s only one of the projects dedicated to solving this problem. To further understand layer 2 solutions, you need to look beyond Bitcoin to the different blockchains that are using this technology.<br/> 

## **Why is scaling a problem?**

Scalability simply refers to a network’s ability to handle a high number of transactions per second. Increasing the number of transactions a blockchain can handle is fundamentally considered one of the biggest hurdles cryptocurrency’s and decentralized payment platforms face. Scaling is thought of as the biggest hurdle between crypto and mass adoption.

Credit cards like Visa and Mastercard can handle up to 47,000 transactions per second at any given time. In fact, it’s estimated that during China’s infamous global [Singles’ Day shopping event](https://techcrunch.com/2018/11/09/alibaba-singles-day-11-festival/), these credit card companies can process closer to 100,000 transactions per second.

In comparison, Bitcoin performs approximately [4.6 transactions](https://hackernoon.com/the-blockchain-scalability-problem-the-race-for-visa-like-transaction-speed-5cce48f9d44) per second. The reason for this large discrepancy is that Visa and MasterCard are part of the centralized banking system, which has been around for more than 100 years. Decentralized technologies must always face what is known as the ‘impossible triangle’.

**The impossible triangle** refers to the three principles that give a blockchain its utility:

1. Security
2. Scalability
3. Decentralization

At the present moment, there isn’t a single cryptocurrency on a completely public blockchain that masters all three of the above. Ripple currently handles [1,500 transactions per second](https://www.ripple.com/xrp/). The EOS blockchain has a throughput of nearly [4,000 transactions per second](https://thenextweb.com/hardfork/2018/11/01/eos-blockchain-benchmark/). It’s safe to say to this point, the triangle is still proving impossible to master. This is why layer 2 approaches are becoming more commonly known as a scaling solution.<br/> 

## **The Lightning Network**

The [Lightning Network](https://medium.com/shapeshift-stories/ride-the-lightning-ec6b8d3a086f) allows smaller transactions through payment channels. Opening a payment channel is great for smaller, reoccurring transactions like purchasing coffee every day. A big-time coffee lover might buy three cups per day, which is 21 transactions a week. The Lightning Network allows users to create a payment channel that confirms these 21 transactions, the initial balance, and the final balance of all of these transactions on the blockchain.

The Lightning Network is necessary because the [average bitcoin transaction](https://hackernoon.com/2019-blockchain-layer-2-solution-review-d00385147396#1cee) is worth around $50, with a fee of about $20. That makes keeping small transactions ‘on-chain’ impractical. Making transactions off-chain reduces the load on the blockchain. The lightning network also makes it so that a multi-signature address must be used; meaning no two parties can manipulate each other in completing a transaction. The downside is that the lightning network can’t be used off-line. It also can’t be used for large amounts, and it allows nodes to potentially become large payment hubs that hold large sums of value.

[*>>> Read more on Bitcoin’s Lightning Network <<<*](https://medium.com/shapeshift-stories/ride-the-lightning-ec6b8d3a086f)

## Payment Channels

From a coding standpoint, a payment channel is really just one iteration of a state channel layer 2 solution. A state channel implementation:

* Allows part of the blockchain’s state to be locked using multi-signature addresses or smart contracts
* Allows participants to then update the state of that part of the chain
* Submits the updated state back to the blockchain

This state channel approach is most easily understood in a monetary exchange; the exchange could be anything. It could be used to track any other kind of change to a blockchain’s state, whether the transaction is related to money, intellectual property, government identification, etc.<br/> 

## **Ethereum Scaling Solutions**

Ethereum aims to be the world’s decentralized supercomputer. Its existence gives developers a platform for building and launching decentralized applications that everyone can use. That’s what makes it different from Bitcoin. What makes the two cryptocurrencies similar is that they both use the [proof-of-work](https://medium.com/shapeshift-stories/exploring-consensus-algorithms-8403c301b2ff) consensus algorithm.

## Casper

Casper is the upgrade that will move Ethereum to the arguably more efficient proof-of-stake approach. Proof-of-stake algorithms make validating transactions more efficient, both technically speaking and in terms of energy costs.

## Plasma

Where a proof-of-stake consensus algorithm validates transactions, the Plasma upgrade applies the second layer of smart contracts to the blockchain. It will help replace server farms with a peer-to-peer network that makes running decentralized applications more scalable. As the [Plasma whitepaper](https://plasma.io/plasma-deprecated.pdf) explains, transactions can occur privately between users on private chains, and then be represented on the public chain.

## Sharding

Sharding will complement Casper and Plasma in making Ethereum’s blockchain more scalable. It allows for [data to be divided](https://www.trustnodes.com/2018/05/01/sharding-proof-concept-launches-casper-32-staking-eth-requirements-coming-says-vitalik-buterin) and hosted on multiple servers. It means the public ledger becomes fragmented, but all transactions will still be accounted for.

## Sidechain and Off-Chain Transactions

Now you know about two of the more popular approaches to scaling payments and smart contracts. There are two other noteworthy layer 2 solutions to explore.

## Sidechain

A sidechain is a separate blockchain that is attached to a parent chain using a two-way peg, which allows for exchanging assets for one another at a fixed rate. Sidechains can be used for all kinds of digital assets and need their own miners to remain secure. Projects using sidechains effectively include [OmiseGO](https://omisego.co/), [POA Network](https://poa.network/), and [Alacris](https://alacris.io/).

## **Off-Chain**

Off-chain transactions occur completely off of a blockchain. This can happen via a transfer agreement between the two parties, via a third-party guarantor (similar to what Paypal does in the fiat world), or using a coupon-based mechanism. Off-chain transactions can happen instantly with no fees and more anonymity. Projects implementing an off-chain approach include [Provable](https://provable.xyz/), [AlphaWallet](https://alphawallet.com/), and [Transmute](https://www.transmute.industries/).

## Zero-Knowledge Proofs

Did you know that the cryptographic underpinnings that enable privacy on Zcash can be leveraged to increase scalability too? This promising layer-2 approach is currently being built on Ethereum, using both STARKS and SNARKS (the two primary types of zero-knowledge proofs).

On the STARKS side, Israel’s [STARKWARE](https://starkware.co/) is building an innovative solution that can batch thousands of off-chain transactions without the need for a trusted setup. Also, keep an eye on [Matter Labs](https://matter-labs.io/) and their SNARK-based “roll-ups.”

Even though these solutions are far from perfect — the potential to take blockchain technology to the next level is there. With scaling advancements like layer 2 solutions, the mission to bring mainstream adoption to crypto seems to be just on the horizon.<br/> 

---

> This document was originally published on 2019-10-17 by ShapeShift Team and may have been slightly modified for translation by the Information and Globalization workstream for an ongoing archival project.
>
> Original article can be found [here](https://shapeshift.com/library/digging-into-layer-2-blockchain-solutions).
{.is-success}

---

- bounty: true
- amt: 54
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}