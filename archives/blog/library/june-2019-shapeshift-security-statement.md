---
title: ShapeShift Security Statement
description: Our Response to clarify Ledger’s recent claims at #BreakingBitcoin.
published: false
date: 2021-12-20T23:03:03.761Z
tags: library, security, keepkey, bitcoin, needs-review
editor: markdown
dateCreated: 2021-12-20T23:03:03.761Z
---

# ShapeShift Security Statement

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fdf3cce036369ec8de731_1_R53l5-JzGtTc0ZTNCs9HfQ.png)

Last weekend, during the [Breaking Bitcoin Conference](https://twitter.com/breakingbitcoin), Ledger’s Chief Security Officer Charles Guillemet presented *Extracting Seeds from (Hardware) Wallets.* The presentation exposed vulnerabilities in open hardware wallets — including [KeepKey.](https://www.keepkey.com/) This vulnerability resulted in the extraction of the private key.

**We consider this class of vulnerability — one that can reveal private keys — the most critical type of bug.**

So we dug deeper to understand the issue.

Although Guillemet was unable to specify how Ledger retrieved the private key, ShapeShift has known about an attack that yields the private key *since* before we acquired KeepKey in 2017.<br/> 

## How this Attack Works

An attacker **steals** your KeepKey device, opens it up, and uses specialized electronics to read encrypted data off the flash storage. Next, he uses software to guess your PIN code by trying every possible combination. To pull this off, an attack would need:

* Specialized hardware engineering knowledge, skills, and experience
* Specialized software engineering knowledge, skills, and experience
* Specialized software designed to guess every possible PIN code; and
* Physical possession of your KeepKey

Hardware wallets (like KeepKey) are designed to protect you from the most common attack vectors: including malware, viruses, and remote hackers looking to steal private keys. But — the vulnerability that Guillemet and Ledger reference does not attack keys in these ways.

**Rather, this vulnerability is one in which an attacker would need to have physical possession of your KeepKey.** KeepKey’s job is to protect your keys against remote attacks.

If somebody else has physical access to your device — as well as the time, skill, and tools necessary — they will **always** be able to command the device to do whatever they want, bypassing any digital lock that exists.

**Again, this is true of any hardware wallet.**

Of course, this is nothing new. Companies have been fighting this problem in computing for decades to no avail, as it comes up in a variety of industries.

For example, operating systems, applications, and digital media use digital locks to ensure end-users have paid for licenses. Hackers modify the code on their local machines to make the system think it is paid for.

Games use a variety of digital locks to prevent cheating, but cheaters modify games to play however they want.

And each time a bright engineer thinks of a new type of digital lock, an equally bright hacker analyzes the lock on their own machine to understand how it works — and then uses that knowledge to circumvent it.

**It’s like a maze where you can see every twist and turn — all from a birds-eye view.**

The fact is that there’s no way to prevent a highly sophisticated attacker with physical possession of the device, and lots of time, technology, and resources, from completely “pwning” that device — eventually.

ShapeShift recommends that you secure your device with the same caution you would with other investments or valuables. Protect your KeepKey like it could be stolen tomorrow.

**It’s like a maze where you can see every twist and turn — all from a birds-eye view.**

While PIN codes add 4–9 simple digits to create a barrier between hackers and your private key(s), 9 digits aren’t enough. In his presentation, Guillemet demonstrated that you can guess a 9-digit PIN in approximately one minute.

With KeepKey, you‘re able to set a passphrase that provides an added layer of protection.

Guillemet recommends using passphrases comprised of at least 32 digits made up of a unique combination of numbers, symbols, as well as upper and lower-case letters.

With a sufficiently-long [passphrase](https://keepkey.zendesk.com/hc/en-us/articles/360000616300-How-Do-I-Access-My-ShapeShift-Membership-Account-with-a-Passphrase-), if an attacker takes the data off your device, they’ll never be able to unlock it. Your PIN and your passphrase **k**eeps your funds — safe.<br/> 

## Enable Your BIP39 Passphrase with the [KeepKey Client](https://chrome.google.com/webstore/detail/keepkey-client/idgiipeogajjpkgheijapngmlbohdhjg)

1. Plug-in and unlock your KeepKey
2. Click the gear icon **⚙️** located on the top-left of the KeepKey client
3. Click “Enable BIP39 Passphrase”
4. Enter a long passphrase (you’ll be prompted to re-enter/confirm this).
5. Copy/Write down your new bitcoin/litecoin/etc. addresses from your passphrase-protected account
6. Unplug your KeepKey and plug it back in.
7. Do not enter a passphrase. Click “OK” with an empty passphrase to access your original unprotected accounts.
8. Send your bitcoin/litecoin/etc. to the addresses that you copied in #5 (above). Double-check the addresses that haven’t been altered from clipboard jacking malware.
9. Unplug your KeepKey and plug it back in.
10. Enter your passphrase and click “OK.”
11. You can now see all of your coins on your passphrase-encrypted addresses.<br/> 

## Final Thoughts

If you’re interested in additional security to protect against this extremely unlikely edge case, make sure to check out [*How Do I Access My ShapeShift Membership Account with a Passphrase?*](https://keepkey.zendesk.com/hc/en-us/articles/360000616300-How-Do-I-Access-My-ShapeShift-Membership-Account-with-a-Passphrase-)

If you’re a security researcher who has identified what you believe to be a bug or vulnerability in any of ShapeShift’s products or services, we’d love to hear from you.

And, we’re always here to help. [Contact our support team](https://shapeshift.zendesk.com/hc/en-us/requests/new) — anytime.

---

> This document was originally published on 2019-06-13 by ShapeShift Team and may have been slightly modified for translation by the Information and Globalization workstream for an ongoing archival project.
>
> Original article can be found [here](https://shapeshift.com/library/shapeshift-security-statement).
{.is-success}

---

- bounty: true
- amt: 40
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}