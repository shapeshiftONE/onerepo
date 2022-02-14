---
title: The Power of Cryptography
description: A beginner's guide to public and private keys.
published: false
date: 2021-12-20T23:03:17.065Z
tags: library, security, bitcoin, needs-review
editor: markdown
dateCreated: 2021-12-20T23:03:17.065Z
---

# The Power of Cryptography

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fe664f01b87e59121323b_1_3VBrEt6tEGGLUrte9icrbQ.jpeg)

<br/>Whether you’re new to crypto or a long-time veteran, there are certain ideas that everyone involved in this space should understand. Today we’re going to cover one of them: public and private keys.

In our earlier post on [Crypto Storage](https://bit.ly/2UtogzI), we used these two terms extensively tohelp convey the benefits of hardware wallets. Now we’ll break them down to show how they fit into the larger ecosystem around us.

In order to do this, we need to start with the basics of cryptography, the fundamental idea that public and private keys are built upon.<br/> 

## **What is Cryptography?**

The word cryptography, like many other words in the English language, has its roots in Greek. Broken down, the word roughly translates into “hidden writing.” In an environment like the internet where privacy can seem scarce,public and private keys enable people to communicate through cryptography.

So how is this relevant to you? Let’s imagine you’re sending an important document to a friend over the internet. Maybe it’s a secret note you only want them to see; maybe it’s your lease agreement. You want to send this document to your friend, and you want to make sure that no one can read it but them. That’s where public and private keys come into play in the form of asymmetric cryptography.<br/> 

## **Asymmetric vs. Symmetric Cryptography**

Asymmetric cryptography is a method that uses one key to encrypt data (the public key) and one key to decrypt data (the private key). Conversely, symmetric cryptography uses the same key to both encrypt and decrypt the same piece of data.

As a result, asymmetric is more secure than symmetric cryptography, but the process can take *slightly* longer as you’re dealing with two keys instead of one.

Now, as asymmetric cryptography is what is used in the Bitcoin protocol, that’s what we’ll focus on.

Ok, so let’s stick with the example of sending a friend your lease agreement. If you want to ensure through cryptography that only they can read the agreement, these are the steps you would follow:

1. Obtain your friends public key
2. Encrypt the agreement with that public key
3. Send the encrypted agreement to your friend
4. Your friend receives the encrypted agreement and decrypts it with their private key

In this way, anyone can send your friend encrypted data when using that friend’s public key, while your friend is the only one who can decrypt it and read the encrypted messages. This works in the same way that anyone can send you an email, but only you are able to open your mailbox and read the messages.<br/> 

## **How It Relates to Crypto**

So how does this relate back to blockchain technology and cryptocurrencies? At a base level, the public and private keys are one of the fundamental components that make transactions on the blockchain possible.

When your keys are created, your public key is put through [a hash function](https://www.investopedia.com/terms/h/hash.asp), and the resulting random string of letters and numbers is used as your wallet address. Transactions will work like our lease agreement example above.

Let’s use Bitcoin as an example. First, someone will send bitcoin to your wallet address. By doing so, they are giving you the right to spend that bitcoin, *as long as you can prove yourself as the owner of the address*. By signing the transaction using the corresponding private key, you are given ownership of that right to spend ([Read more about UTXO’s here](https://www.investopedia.com/terms/u/utxo.asp)).

Knowing the basics of public and private keys is fundamental in understanding the Bitcoin protocol, and impressing your friends.

---

> This document was originally published on 2019-05-12 by Ari Chernoff and may have been slightly modified for translation by the Information and Globalization workstream for an ongoing archival project.
>
> Original article can be found [here](https://shapeshift.com/library/the-power-of-cryptography).
{.is-success}

---

- bounty: true
- amt: 29
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}