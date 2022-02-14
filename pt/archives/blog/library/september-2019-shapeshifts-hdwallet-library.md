---
title: ShapeShift’s HDWallet Library
description: Simplify wallet integration with our new open-source library.
published: false
date: 2021-12-20T23:03:00.678Z
tags: library, bitcoin, developer, shapeshift, needs-review
editor: markdown
dateCreated: 2021-12-20T23:03:00.678Z
---

# ShapeShift’s HDWallet Library

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9f4822e79cc78c7a46d920_1_ds0x4HwcR-BDsq1MDoSCDw.png)


**Unorthodox** problems often require unorthodox solutions, and nowhere is this more prevalent than in the still nascent world of blockchain tech. The [ShapeShift](http://shapeshift.com/) team faced the issue of interfacing with wallets from a variety of vendors, as a solution we built and open-sourced it to the community.

Take a moment to read about the problem we faced that prompted this design, and how our HDWallet solution works. **We hope you enjoy.**

*Find our developer resource page here:* [*pages.shapeshift.com/developer-portal*](https://pages.shapeshift.com/developer-portal/)

## **The Problem**

Applications that want to interface with multiple wallets need to build an integration to each wallet. This means for every call you want to make, such as getting an address or signing a transaction, you have to write new code for each wallet.

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9f487c5e020326f42a1e7c_1*S73qLZhEFp_34MWa2C-L5Q.png)

## **The Solution**

To solve this problem, we built the HDWallet abstraction layer. We believe in following DRY (don’t repeat yourself) coding practices and simple design.

With HDWallet, your code can make one call to the HDWallet interface, and depending on the wallet you are connected to, HDWallet will translate that call to the specifications that each wallet type requires.

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9f487c75a6fe699a90b7f0_1*oLH61LKwuwowKgURNhWO9g.png)

[*>>> Check out our Open-Source HD Wallet Library on GitHub <<<*](https://github.com/shapeshift/HDWallet)

## **<br/>How It Works**

HDWallet has a separate module for each wallet it integrates with. You can see them in the code in the /packages directory. Each of those modules contains necessary submodules that allow communication with the wallet to occur. There is also a HDWallet-core module that contains functions you will need no matter what wallet you are connecting to.

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9f487c02aad5cdf2fb04de_1*2H75EPG9eTVxV2uh6cj-XQ.jpeg)

## **<br/>How to Get Started**

If you’re interested in learning more about HDWallet, take a look at our developer exercises [here](https://codesandbox.io/s/github/keepkeyjon/teach-hdwallet/tree/master/exercises/01-pair-device?from-embed)). We give hands-on examples for navigating the enhanced capabilities that this interface provides.

Access all of our developer resources for ShapeShift’s Open-Source HDWallet Library, ShapeShift Exchange API, and CoinCap API on our [website](https://pages.shapeshift.com/developer-portal/).<br/> 

---

> This document was originally published on 2019-09-30 by ShapeShift Team and may have been slightly modified for translation by the Information and Globalization workstream for an ongoing archival project.
>
> Original article can be found [here](https://shapeshift.com/library/shapeshift-hdwallet-library).
{.is-success}

---

- bounty: true
- amt: 19
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}