---
title: Unlocking the Mysteries of Private Keys
description: Private keys are critically important in the crypto industry. Learn more. 
published: false
date: 2021-12-20T23:03:19.590Z
tags: library, cryptocurrency, defi, needs-review
editor: markdown
dateCreated: 2021-12-20T23:03:19.590Z
---

# Unlocking the Mysteries of Private Keys

## ***Part One of a Three-Part Series***

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/60410f04b90eef50bdcef5fb_Paper.Port_is_-_Private_Keys.4.png)

## Private keys: An overview

In many ways, owning cryptocurrency comes down to merely holding a private key. Unlike in the “real” world, where owning physical property usually involves possessing a deed with your name on it or having a receipt of sale, **owning** **is equivalent to knowing in the crypto world.** In simpler terms, knowing a private key is equivalent to owning crypto assets, since private keys are what enable you to authorize transactions with them.

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/604110379bf86942b436399f_Owning.png)

*The statement “knowledge is power” has never been as true as it is in crypto.*<br/><br/>

In the real world, transactions are usually authorized with your signature. However, in the crypto world, only **private keys** can authorize them, cryptographically, granting access to funds**.** Although anyone can generate a transaction involving your crypto assets, only the person in possession of the private key can sign, and thus validate, the transaction.<br/>

> *Although fake signatures are a problem in the real world, the crypto world is protected by its underlying cryptography nature. As of today, no known hack allows someone to sign transactions on your assets without your key.*

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/604110c6415c80a0e6b91c39_Access.png)

*The powerful phrase, “not your keys, not your coins” comes from the fact that by having a private key, anyone can sign any transaction on these assets and thus transfer or move them as they please (making sole possession of them important).*<br/>

## What are private keys, and how are they generated?

Private keys are numbers within a specific range, usually very large. From a mathematical perspective, a private key is just a **random positive integer**. A more technical and accurate description, however, would be: *A private key is a cryptographically strong random number that has been obtained using a random number generator**given a defined positive range.* 

Most of the time, computers use **pseudorandom number generators (PRNGs)** to generate these random positive integers. (True random number generators are hard to come by; these generators often require specialized hardware and use physical sources such as thermal noise in electrical circuits or the precise timing of Geiger counter clicks.)PRNGs are cryptographically strong functions seeded with a value that has enough **entropy**. Entropy is a complex concept, but its objective is simple: to provide unpredictability to functions. By using secure entropy sources, PRNGs can create numbers that are extremely unlikely to not be random (within a given, acceptable range).

<br/>

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/604111422a65fc3b152c1bbf_Entropy.png)

*“/dev/urandom” in Linux or “rand\_s” in Microsoft Windows are commonly used entropy sources for PRNGs for safe, random number generation. In this diagram, the term “range” is used loosely to mean both the mathematical concept of range and the size of bytes a computer is given to generate a random number.*<br/><br/>

The range given to a PRNG to securely create a valid Ethereum or Bitcoin private key is **2^256–1** (imagine a combination lock of the numbers 0–9, which is 78 digits long). Due to the size of this range, the probability of generating two private keys with the same number is negligible. The set of integers your key is selected from is a [massive number](https://www.wolframalpha.com/input/?i=2%5E256)—it is **roughly the same as the total number of visible atoms in the universe**.

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/604113247ce66b0a06d760cc_Range.png)

*The range of 2^256–1 has been defined by both Bitcoin and Ethereum, and it works due to the mathematical strategies both blockchains use to create public keys. For instance, Ethereum uses elliptic curves (particularly SECP-256k1) for its public key generation. In its original* [*yellow paper*](http://gavwood.com/paper.pdf)*, Dr. Davin Wood defined a private key as a randomly selected positive integer (represented as a byte array of length 32 in a big-endian form) in the range [1, secp256k1n–1]. For all formal definitions, please refer to the actual yellow paper.*<br/>

## Public keys, addresses, and their relationship to private keys

Since private keys are meant to be kept . . . well . . . private, we need a different mechanism to allow other individuals to find our assets and for us to find theirs. As a result, all blockchains use the concept of **addresses**—unique numbers derived from your private key. These addresses are the location of your crypto assets and can be shared with whomever you need to know your crypto assets’ balance (if you want to). 

A blockchain address is created using your **public key** to ensure you are the owner of the address in question**.** In turn, this public key is generated from your private key. This process is **unidirectional**, which means you can use a private key to create an account, but not an account to guess a private key.

> *Private keys can derive public keys, and public keys can derive blockchain addresses. However, blockchain addresses cannot be used to derive their public keys, and public keys cannot be used to derive their private keys.* 

This unidirectional process is done via **cryptographic trapdoor functions**. A trapdoor function is a one-way function that can only generate its value based on a specific input, and it cannot be used to derive the original input from it. It’s like knowing how to bake a cake and having a rough idea of what is in a cake; yet it’s impossible to tell the exact ingredients of a specific cake from tasting it alone.

Depending on the blockchain ecosystem, these one-way functions vary. For instance, most popular blockchain systems use elliptic curve-based algebraic constructions to generate their public keys. Independently of these characteristics, the outcome is always **deterministic**: a public key is unique to its corresponding private key, and the private key always generates the same public key.<br/><br/>

<br/>

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/604113a0b5a6cc67e23d3750_Public%20keys.png)

*Although popular blockchains like Bitcoin or Ethereum use a fixed generator point from the elliptic curve secp256k1 over ECDSA for multiplying the private key to obtain its public key, other blockchain projects use different strategies. For instance, Monero uses Curve25519 over EdDSA, whereas Polkadot and Substrate chains use Ed25519 over sr25519. All of them generate a public key based on a given private key with a range of 2^256-1.*<br/>Blockchain addresses also use one-way functions, called [hash functions](https://en.wikipedia.org/wiki/Hash_function). Bitcoin and Ethereum addresses are created from one or more **cryptographically strong hashing functions** over your public key, in addition to specific mathematics depending on the particular blockchain.Because of how these hashing operations work, you can be confident to an almost absolute degree that your blockchain address is unique to your public key, and thus, to your private key.

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/604113ed9bbe7adeb9daed5b_Accounts.png)

*An Ethereum account is the Keccak-256 hash of a public key in addition to taking the rightmost 20 bytes of such computation. Bitcoin keys use SHA-256 and RIPEMD-160, whereas Polkadot and ZCash use Blake2b. All these hashes are collision-resistant, reducing the possibility of generating a single account from two public keys and ensuring that the only way an account can be regenerated from an input is via an economically inefficient brute force. There are no guarantees these hash functions might not be broken, but as of today, no known hash functions used in any blockchain have been proven broken.*<br/> <br/>

## The universal language of math keeps our secrets

The cryptography and mathematics behind private keys are the reason why our crypto assets are safe—as long as we keep our keys secure. As of today, it is impossible to find and brute force any blockchain address connected to your private keys due to the fact that it would cost [more energy than is stored by the sun](https://support.mycrypto.com/staying-safe/ethereum-two-people-same-private-key). <br/>

In our next blog, we will look at popular blockchain ecosystems and some of the math behind public key generation. We’ll provide some code examples for you to try calculating the keys from the process each blockchain describes and using existing libraries that make the generation process easier. Stay tuned!<br/>

---

> This document was originally published on 2021-03-05 by Jose Aguinaga and may have been slightly modified for translation by the Information and Globalization workstream for an ongoing archival project.
>
> Original article can be found [here](https://shapeshift.com/library/unlocking-the-mysteries-of-private-keys).
{.is-success}

---

- bounty: true
- amt: 63
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}