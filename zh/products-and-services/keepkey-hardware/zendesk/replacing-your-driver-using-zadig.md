---
title: 使用 Zadig 更换驱动程序
description: 您的 Windows 计算机是否未检测到您的 KeepKey、Trezor 或 Ledger？我们发现有些机器没有合适的...
published: false
date: 2021-12-02T02:25:57.870Z
tags: hardware wallet, hd wallet, keepkey, keepkey wallet, keepkey-zendesk, zendesk
editor: markdown
dateCreated: 2021-11-28T12:51:10.265Z
---

# 使用 Zadig 更换驱动程序

## 您的 Windows 计算机是否未检测到您的 KeepKey、Trezor 或 Ledger？

## 我们发现，某些计算机没有适当的默认驱动程序设置来成功识别 beta.shapeshift.com 上的硬件钱包设备。不用担心。我们有一个直接来自Windows的解决方案来提供帮助。下面将说明如何使用名为Zadig的USB驱动程序安装程序。
   
安装 Zadig

1\.要开始，请转到 [Zadig](https://zadig.akeo.ie/) 单击"Zadig 2.4"并开始安装。

![zadig1.png](https://shapeshift.zendesk.com/hc/article_attachments/360008039340/zadig1.png)

![zadig.2.png](https://shapeshift.zendesk.com/hc/article_attachments/360008048859/zadig.2.png)

2\.安装后，您应该看到如下内容：

![zadig.3.png](https://shapeshift.zendesk.com/hc/article_attachments/360008048879/zadig.3.png)

## 更换驱动程序 

3\. 单击"选项"，然后选择"列出所有设备"。

![zadig.8.png](https://shapeshift.zendesk.com/hc/article_attachments/360008048899/zadig.8.png)

4\. 您现在应该看到已检测到设备。单击下拉插入记号，然后选择"KeepKey 接口（接口 0）"。**对于此过程，请务必注意，我们不会选择KeepKey U2F接口（接口1）。**

![zadig.9.png](https://shapeshift.zendesk.com/hc/article_attachments/360008039300/zadig.9.png)

5\. 在绿色箭头的右侧，使用向上或向下箭头导航到 libusbK （v3.0.7.0）。

 ![zadig.13.png](https://shapeshift.zendesk.com/hc/article_attachments/360008048959/zadig.13.png)

注意：如果当前驱动程序已是 libusbK （v3.0.7.0），请使用向上或向下箭头选择 WinUSB （v6.1.7600.16385）。

Zadig现在应该看起来像这样：

![zadig.4.png](https://shapeshift.zendesk.com/hc/article_attachments/360008039220/zadig.4.png)

6\. 单击"替换驱动程序"。

7\. 驱动程序将开始安装。

![zadig.5.png](https://shapeshift.zendesk.com/hc/article_attachments/360008039240/zadig.5.png)

![zadig.6.png](https://shapeshift.zendesk.com/hc/article_attachments/360008039260/zadig.6.png)

8\. 您现在应该看到您当前的驱动程序已更改为 libusbK（或 WinUSB，具体取决于您替换的驱动程序。）

![zadig.10.png](https://shapeshift.zendesk.com/hc/article_attachments/360008048919/zadig.10.png)

如果您打开了 beta.shapeshift.com，那就继续关闭它。重新启动您尝试将设备连接到的任何设备，并尝试配对KeepKey。如果驱动程序确实是导致您的设备未被检测到的问题，则现在应该可以看到您可以连接KeepKey。

**如果您在更换驱动程序时遇到问题，或需要帮助恢复此过程，请联系我们的 [支持团队](/hc/en-us/requests/new).**

---

Documented archived by the ShapeShift DAO Information and Globalization workstream for translation purposes. Original article can be found [here.](https://shapeshift.zendesk.com/hc/en-us/articles/360011307520-Replacing-Your-Driver-Using-Zadig)

Last updated: 5 months ago