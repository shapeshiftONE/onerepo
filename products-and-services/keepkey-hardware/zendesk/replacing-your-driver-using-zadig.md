---
title: Replacing Your Driver Using Zadig
description: Is your Windows machine not detecting your KeepKey, Trezor, or Ledger? We have found that some machines do not have the appropriate...
published: true
date: 2021-11-10T15:55:33.924Z
tags: hardware wallet, hd wallet, keepkey, keepkey wallet, keepkey-zendesk, zendesk
editor: markdown
dateCreated: 2021-10-31T19:01:09.799Z
---

# Replacing Your Driver Using Zadig

## Is your Windows machine not detecting your KeepKey, Trezor, or Ledger?

## We have found that some machines do not have the appropriate default driver settings to successfully recognize a hardware wallet device on beta.shapeshift.com. Not to worry. We have a solution directly from the Windows to help.  The following will explain how to use a USB driver installer called Zadig.  
   
Installing Zadig

1\. To start, head over to [Zadig](https://zadig.akeo.ie/) Click "Zadig 2.4" and begin the installation.

![zadig1.png](https://shapeshift.zendesk.com/hc/article_attachments/360008039340/zadig1.png)

![zadig.2.png](https://shapeshift.zendesk.com/hc/article_attachments/360008048859/zadig.2.png)

2\. Once installed, you should see something like this:

![zadig.3.png](https://shapeshift.zendesk.com/hc/article_attachments/360008048879/zadig.3.png)

## Replacing Your Driver

3\. Click "Options" and select "List All Devices".

![zadig.8.png](https://shapeshift.zendesk.com/hc/article_attachments/360008048899/zadig.8.png)

4\. You should now see that devices have been detected. Click the drop down caret and select "KeepKey Interface (Interface 0). **For this process, it is important to note that we are NOT going to select KeepKey U2F Interface (Interface 1).**

![zadig.9.png](https://shapeshift.zendesk.com/hc/article_attachments/360008039300/zadig.9.png)

5\. To the right of the green arrow use the up or down arrow(s) to navigate to libusbK (v3.0.7.0).

 ![zadig.13.png](https://shapeshift.zendesk.com/hc/article_attachments/360008048959/zadig.13.png)

Note: If your current Driver is already libusbK (v3.0.7.0), use the up or down arrow(s) to select WinUSB (v6.1.7600.16385).

Zadig should now look something like this:

![zadig.4.png](https://shapeshift.zendesk.com/hc/article_attachments/360008039220/zadig.4.png)

6\. Click "Replace Driver".

7\. The driver will begin to install.

![zadig.5.png](https://shapeshift.zendesk.com/hc/article_attachments/360008039240/zadig.5.png)

![zadig.6.png](https://shapeshift.zendesk.com/hc/article_attachments/360008039260/zadig.6.png)

8\. You should now see that your current driver has changed to libusbK (or WinUSB depending on which one you replaced.

![zadig.10.png](https://shapeshift.zendesk.com/hc/article_attachments/360008048919/zadig.10.png)

If you had beta.shapeshift.com open, go ahead and close that down. Restart whichever you were trying to connect your device to and try to pair the KeepKey. If the driver was indeed the issue causing your device to not be detected, you should now see that you are able to connect your KeepKey.

**If you are having trouble replacing your driver or would like help reverting this process, please contact our [support team](/hc/en-us/requests/new).**

---

Documented archived by the ShapeShift DAO Information and Globalization workstream for translation purposes. Original article can be found [here.](https://shapeshift.zendesk.com/hc/en-us/articles/360011307520-Replacing-Your-Driver-Using-Zadig)

Last updated: 5 months ago