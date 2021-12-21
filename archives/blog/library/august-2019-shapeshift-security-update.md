---
title: ShapeShift Security Update
description: Our response to the disclosed KeepKey vulnerability.
published: false
date: 2021-12-20T23:03:05.568Z
tags: library, security, bitcoin, needs-review
editor: markdown
dateCreated: 2021-12-20T23:03:05.568Z
---

# ShapeShift Security Update

![](https://assets.website-files.com/5e9a09610b7dce71f87f7f17/5e9fbc6174f1eb0baecd6ef8_1_HF9N0x8Vhs9xPNjuJD84kw%20(1).png)

On May 1st, 2019, ShapeShift received a report from Christian Reitter through our [**Responsible Disclosure Program**](https://corp.shapeshift.io/responsible-disclosure-program/) that identified what they believed to be a vulnerability in KeepKey. This report was part of a coordinated disclosure across multiple hardware wallet vendors, and the vulnerability has since been assigned tracking number [CVE-2019–14355](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-14355) by Mitre. Security is obviously one of our highest priorities at ShapeShift, so we’ve reviewed the report to better understand the vulnerability in detail.

> “We believe there is insignificant risk to ShapeShift users, their KeepKeys, and their funds. “<br/>— ShapeShift’s Security Team

## Here’s How it Works

KeepKey’s screen uses power. By measuring the subtle differences in the amount of power used by the screen at any moment, it is possible to identify what is being displayed. This is called a side-channel attack. While the attack is not reading the screen directly (it’s only reading power fluctuations), an attacker can figure out what is on the screen anyway. If this is done while sensitive information is on the screen (like your recovery phrase), an attacker could ultimately steal your funds.<br/> 

## Here’s What Would Need to Happen

An attacker needs the following in order to perform this attack:

* **Physical Access** — They need your KeepKey in their hands to make this work
* **Specialized Equipment** — They need an oscilloscope or another device capable of measuring the minute differences in the power drawn from the screen
* **Hardware Skills** — They need the ability to measure the electrical signals on the USB interface without disrupting it
* **Statistical Data** — A lot of work and analysis is required to understand how much power is drawn from each seed word

*That’s a lot of stuff… and again the attacker needs to physically possess your KeepKey.*

By comparison, it would be far easier to steal someone’s Recovery Phrase by simply looking over their shoulder while they set up their KeepKey or installing a hidden camera in the room in which it was being initialized. It is impossible to stop someone from tampering with any hardware wallet if they have it in their hands. We discussed this in June on [our blog](https://medium.com/shapeshift-stories/responding-to-ledgers-2019-breakingbitcoin-findings-4213849a4fb) after Ledger presented their research at Breaking Bitcoin. In other words, if you care about actual risk, there are far more important things to be concerned with, such as the physical environment in which you initialize and use your hardware device.<br/> 

![](https://assets.website-files.com/max/6000/1*-aymwYV6nX3cwCADC79waw.png)

## KeepKey Not Materially Affected

After analyzing this attack in-depth, we believe KeepKey is not affected:

1. **Physical Access is Required** — You should always keep your device hidden, regardless.
2. **USB Ports Aren’t Enough** — Commodity laptops and desktops do not have the specialized equipment to read the subtle differences in power fluctuations.
3. **Impractical Supply Chain Attack** — A supply chain attack on the cable itself would also require corresponding malware on the user’s computer to read the data out of the cable.
4. **Large Display** — Due to the larger display in KeepKey, multiple Recovery Phrase words are displayed at once. This makes it much more difficult to identify individual words (and the order of words) based off the power used by the screen. Other hardware wallets with tiny screens display words one at a time which makes it very easy to match power draw with specific words.
5. **Recovery Phrase Only Displayed Once** — The Recovery Phrase is only displayed once during the setup of KeepKey. If this is done in private and no one is looking over your shoulder, your Recovery Phrase and funds will be safe.
6. **Optional Passphrase —** KeepKey has an [optional security feature called a passphrase](https://keepkey.zendesk.com/hc/en-us/articles/360000616300-How-Do-I-Access-My-ShapeShift-Membership-Account-with-a-Passphrase-) which can be used to encrypt your private keys. The passphrase is never displayed on KeepKey’s screen.

**<br/>This is why we believe there is insignificant risk to ShapeShift users, their KeepKeys, and their funds.** Regardless, ShapeShift always recommends that you secure your device with the same caution you would with other valuables. Protect your KeepKey like it could be stolen tomorrow.

We will continue to monitor this vulnerability and any other reports submitted to our [Responsible Disclosure Program](https://corp.shapeshift.io/responsible-disclosure-program/) to keep our users in control of their funds with an easy to use secure platform.

If you’re a security researcher like Christian — who has identified what you believe to be a bug or vulnerability in any of ShapeShift’s products or services, we’d love to hear from you.

And, we’re always here to help. Contact our [support team](https://shapeshift.zendesk.com/hc/en-us/requests/new) — anytime.

> *KeepKey vulnerability reported by Christian Reitter, an independent security researcher.*

---

> This document was originally published on 2019-08-07 by ShapeShift Team and may have been slightly modified for translation by the Information and Globalization workstream for an ongoing archival project.
>
> Original article can be found [here](https://shapeshift.com/library/shapeshift-security-update-2).
{.is-success}

---

- bounty: true
- amt: 37
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}