---
title: How ShapeShift Protects Your Data
description: ShapeShift is committed to doing everything possible to keep customer data safe
published: false
date: 2021-12-20T23:02:39.376Z
tags: library, security, shapeshift, needs-review
editor: markdown
dateCreated: 2021-12-20T23:02:39.376Z
---

# How ShapeShift Protects Your Data

ShapeShift offers users a variety of exciting and unique benefits such as lower fees, higher trading limits, rewards on trading volume, seamless access to decentralized exchanges, and more. While some services do not require us to collect and store customer data (or “Know Your Customer” practices), others—such as buying Bitcoin—still do in order to meet regulatory requirements.

At ShapeShift, we are committed to doing everything possible to keep customer data safe. We asked the question, “what can hackers do if they break into our systems?” to inform our design decisions.

For our services requiring KYC, the ShapeShift platform collects your information and immediately encrypts it with a 4096-bit RSA key using the widely used open-source GPG software. This encrypted data is stored in our database and—in most cases—is never used again. Once it’s collected, we don’t need to reference it for any business reason.

If you run into a problem and contact customer support (for example for help), they do not see your name or details by default, allowing them to focus on your problem rather than your identity.

There are only a few cases where our staff need to use your identity information. For example, if you lose both your password and two-factor authentication and are trying to get back into your account, our staff will need to know your name and other information in order to compare it with what you’ve given them. In this case, our customer support agents will download your encrypted data to their machine and use a cold storage device containing the private key to decrypt your information. This is managed on a case-by-case basis, preventing wholesale access of customer information by any employee at the company. Another example would be if we were legally compelled to do so by a valid subpoena or similar document. For more information on this example, please see our Privacy Policy [here](https://shapeshift.com/privacy).

Since ShapeShift’s servers never have the decryption key to any personal information (it’s held in cold storage), even if an attacker breaches the servers and copies the entire database, they will not be able to see or access your information. If one of our cold storage devices is lost or stolen, it is configured to wipe itself under certain circumstances.

ShapeShift understands the value of your data and privacy. We are committed to ensuring the safety and security of your information while providing the best non-custodial, decentralized finance solutions in the industry.<br/>

---

> This document was originally published on 2018-09-04 by Michael Perklin, CISO at ShapeShift and may have been slightly modified for translation by the Information and Globalization workstream for an ongoing archival project.
>
> Original article can be found [here](https://shapeshift.com/library/how-shapeshift-protects-your-data).
{.is-success}

---

- bounty: true
- amt: 21
- signedBy: 0xFAc9dD5194098461B627554347f83D5431Fb30e2
- hash: 
{.is-hidden}