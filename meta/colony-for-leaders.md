---
title: Colony (for Workstream Leaders)
description: 
published: true
date: 2021-10-08T21:38:12.591Z
tags: meta, workstream, colony, dao
editor: markdown
dateCreated: 2021-10-03T17:35:23.351Z
---

**What is Colony?**

[Colony](https://colony.io) is a DAO framework on the xDAI chain that ShapeShift DAO is using to enable Workstreams to manage their own treasury, reward contributors, and pay expenses, all in a decentralized way. One way to think about Colony is as a DAO containing sub-DAOs for each workstream, where the more you get paid by a workstream, the more voting power you have on how to allocate that workstream's future funds.

In our case, Colony powers the bottom 2/3 of the organizational structure below.

![Untitled](/untitled.png)

Learn more about Colony on their website, [https://colony.io](https://colony.io), there's lots of great info there

**Key concepts to understand**

Colony is a novel system complete with new concepts and terminology, and it can take a bit of time to wrap your head around. Understanding these key concepts is a great place to start:

[Reputation](https://colony.gitbook.io/colony/key-concepts/reputation)

[Native Tokens (in our case this is FOX)](https://colony.gitbook.io/colony/key-concepts/native-tokens)

[Token Activation](https://colony.gitbook.io/colony/key-concepts/token-activation)

[Motions & Disputes (Reputation)](https://www.notion.so/Motions-Disputes-Reputation-44fa4c8f534048abacb31e94a3839f6b)

Colony is a configurable system which can be designed to facilitate a wide spectrum of organizational structures. Be sure to familiarize yourself with [ShapeShift's Organizational Structure](https://forum.shapeshift.com/t/shapeshift-organizational-structure/50) to understand how we envision using Colony.

**Set up MetaMask and add xDAI network**

The first step to using Colony is to set up a MetaMask wallet and add xDAI network. If you prefer to user a hardware wallet, you can also use a Ledger or Trezor via MetaMask.

1. Download the MetaMask extension for Chrome or Firefox and/or the app for Android or iOS ([https://metamask.io/download](https://metamask.io/download)). You can also connect a Ledger or Trezor to Metamask for maximum security 🔒
2. Visit https://chainlist.org, connect your MetaMask, and add the **xDAI Chain**
    
    ![2021-09-09 10.47.01.gif](/2021-09-09_10.47.01.gif)
    
3. Once your wallet is set up and xDAI has been added, share your address with other workstream leaders and ask them to send you a bit of xDAI to cover gas costs. (@willyfox would be more than happy to send you 1.337 xDAI, which is more than enough)
4. Important: Whenever you interact with Colony, make sure your MetaMask wallet is connected to the xDAI Network before confirming a tx.
    
    ![2021-09-16 13.41.15.gif](/2021-09-16_13.41.15.gif)
    

**Join the Colony** 

To join the Colony and replace your hex string address into a username & avatar, visit [https://xdai.colony.io/colony/shapeshift](https://xdai.colony.io/colony/shapeshift), click the 'Join' button in the upper lefthand of the UI, and follow the instructions to complete your profile.

![2021-09-09 10.51.50.gif](/2021-09-09_10.51.50.gif)

**Requesting funds from the DAO**

In order to fund your workstream, you must go through the [governance process](https://forum.shapeshift.com/t/fox-governance-process/55) and pass a proposal to transfer funds from the DAO's treasury to your workstream on Colony. Check out these examples from other workstreams:

[Proposal to fund the Marketing + Growth Workstream through December 2021](https://app.boardroom.info/shapeshift/proposal/cHJvcG9zYWw6c2hhcGVzaGlmdDpkZWZhdWx0OnFtcHpvZG50Z2NncThmdnR5enRxMWVqN3Nnc3J2ZWN1c2pnZjExeWVmYmFiamg=)

[Proposal to fund the Operations Workstream through January 2022](https://app.boardroom.info/shapeshift/proposal/cHJvcG9zYWw6c2hhcGVzaGlmdDpkZWZhdWx0OnFtcXVvd211eHNqcnphbTJ2ZmlheGE0N2oxcHk0emdxZTh2aWNkZHZxM3p5b2o=)

[Proposal to fund the Product Workstream through December 2021](https://app.boardroom.info/shapeshift/proposal/cHJvcG9zYWw6c2hhcGVzaGlmdDpkZWZhdWx0OnFtZHlpdWZnaDF6eXhwdzk5amZ1eTMzY3N2dWxyMmJ0Zm0zaThiYTRxbGJlbjY=)

**Transferring funds from Root to a Workstream**

1. When the ShapeShift DAO transfers funds to Colony, any member with reputation can claim the funds from the [events page](https://xdai.colony.io/colony/shapeshift/events)

![ClaimFunds.gif](/claimfunds.gif)

1. This will deposit the funds into the Colony's Root team. To transfer funds from Root to your workstream, navigate to **New Action > Manage Funds > Transfer Funds**
    
    ![TransferFunds.gif](/transferfunds.gif)
    
2. Workstream leaders should coordinate to stake behind eachothers' motions to transfer funds from Root to Workstreams in accordance with passed governance proposals.

**Onboarding and paying contributors**

- Recommended practices for paying contributors:
    - Share [this guide](https://www.notion.so/Guide-to-Colony-Contributors-62ec380fd8724ef48c8f18d88904e2fe) with new contributors
    - Communicate with contributors ahead of work being completed
    - Agree upon scope of work, acceptance criteria, and payment details
    - When work is completed, create and stake the expected payment motion
    - If nobody objects to the payment motion during the 72 hour voting phase after the motion is staked, you (or anyone really) can finalize the motion, which will transfer the funds to the contributor
- Anyone with MetaMask and xDAI can create a payment motion, but the motion will not show up in the Activity feed until it has at least 10% of the required stake.
- A brand new contributor with no reputation or stake could theoretically create a payment motion and share the link with other workstream members or the workstream leader to stake the motion. However, contributors are strongly encouraged to communicate with the workstream leader before completing work in which payment is expected.
- While no onboarding to Colony is required, for best practices, share this guide (coming very soon!) with your contributors and offer to send them 1 xDAI to cover gas expenses of interacting on Colony.

**Paying contributors and expenses**

- To pay a contributor or expense, create a payment motion by clicking **New Action > Create Expenditure > Payment**. When the modal pops up, make sure you select your workstream from the dropdown in the top left. If you open the New Action menu while in your workstream, the correct workstream will be populated by default.
    
    ![2021-09-01_21.10.19.gif](/2021-09-01_21.10.19.gif)
    
- **Motion Staking**
    - Workstream members with reputation must stake FOX must behind a motion for it to pass.
    - The amount of FOX required to stake for a motion is the 0.05% of the total reputation points for a Workstream
    - 1 Reputation point is earned for every 1 FOX paid by a workstream, and it decays linearly with a half life of 90 days. E.g. if you earn 100 FOX you will have:
        - 100 Reputation points in that workstream on day 1,
        - 50 points by day 90
        - 25 points by day 180
        - 12.5 points by day 270, etc
    - Here is a [simple model](https://docs.google.com/spreadsheets/d/1Mc-FmtY1hdIt0nYik5GCE2kuZDL5VDN3Pn5fFUzOnMs/edit?usp=sharing) for calculating how much FOX you will need to stake based on payments (please copy the model to make changes)
- Reputation points & FOX balance cap the amount an individual is able to stake
- Stake minimum (currently 1%) is the minimum amount an individual can stake

**What if there is a dispute?** [Motions & Disputes](https://www.notion.so/Motions-Disputes-Reputation-44fa4c8f534048abacb31e94a3839f6b)

**Calculating USD Value for payments in FOX**

1. The exchange rate should be calculated using the exchange rate for FOX from Uniswap v2 at 12AM UTC on the day the payment request is created and the day the request is completed (15th and last day of the month). For recurring payments on the 15th and last day of each month, the Ops will post the exchange rate in the *Workstream Connect: Leadership* channel in Discord 3 days before payment requests and on payday.
2. If price decreases between the 3 days that a payment motion is staked and completed, the contributor should receive additional FOX to make up for the decrease in their next payment. If price increases, the contributor can keep the upside.

**Roles and Permissions**

Workstream leaders receive the following permissions in Colony:

**Funding:** Force the migration of funds between sub-teams within a workstream (sub-team functionality is coming soon)

**Administration:** Force payments to contributors or expenses which bypass the Motions & Disputes process (this is a permission we intend to remove as soon as we are comfortable/confident with Motions & Disputes)!