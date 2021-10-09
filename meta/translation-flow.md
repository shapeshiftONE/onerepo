---
title: Translation Workflow
description: v1 of our workstreams translation workflow. 
published: true
date: 2021-10-08T21:38:14.564Z
tags: globalfox program, meta, workflow
editor: markdown
dateCreated: 2021-10-03T21:34:37.955Z
---

# Translation Workflow
As a new workstream with completely new processes, things are bound to change and improve, and as contributors your understanding and patience is greatly appreciated.  This document shall serve as a guide to our translation workflow. Please do not hesitate to bring up issues or give suggestions on improvements to the workflow.

## Pre-Translation Checklist

Before you begin translating a document, it's important to double check the following.

- [ ] Is this a high priority content item?
- [ ] Is the document completed in English and marked ready?
- [ ] Have I completed other works that I have started?
- [ ] Am I aware of the bounty amount attached to this content item? (does not apply to GCAs)
- [ ] Has anyone already started work on this? (if there are multiple translators in a language)

If everything checks out and you are given the greenlight to continue, let's get translatin'!

## Translating Documents

There are a handful of processes you must follow when beginning the translation work of a document. They are relatively simple and after a few times, they should come as second nature. If a mistake is made and permission settings do not allow you to fix it, don't panic -- just message an admin to get it fixed 🙏
<br>
### 1. Understanding the Folder Structure

**Home Page Naming** 

> The page naming for the homepage of the docs site will always be `/home` regardless of the language.
{.is-info}

![homepage-naming.png](/homepage-naming.png)

---

The current homepage was put up as an example / high level view of the first round of documents that we are proposing to translate. The actual structuring of the documents will be divided into smaller, compartmentalized sub-folders. 

As a demonstration, the first portion of the overall repo has been created with the folder structuring. 

![shapeshift-folder-example.png](/shapeshift-folder-example.png)

> **As you can see, when you try to create a new page you will now see the correct folder structure for the "ShapeShift" documents as seen on the homepage under "ShapeShift & FOX."**
> {.is-success}

![shapeshift-folder-output.png](/shapeshift-folder-output.png)

> If we were to add a new section under this section in the future, the correct folder structure would be `en/shapeshift/page-name` (for the English version) - Creating a new page as `en/new-page` would be incorrect, as the new page would be assigned to the root directory.
{.is-info}

> Folders can be organized even further into more sub-directories. For example, creating `en/shapeshift/fox-token/xdai-network` would turn the `fox-token` page into a directory with a page called `xdai-network`
{.is-info}

<br> 

### 2. Preparing a Document for Translation

**Document Duplication**

First we must duplicate the original source file into the destination language (your language). There are two simple ways to do this, one would be at the top of the page under "Page Actions" and the other would be to hover over the bottom right icon and look for the Duplicate button.

![duplicating.png](/translation-workflow/duplicating.png)

**Duplication Settings**

> Don't forget to set the correct language locale code in the dropdown, and ensure that the page naming is consistent. If the naming is not consistent, there will be problems when switching languages on the frontend.
{.is-warning}


![settings.png](/translation-workflow/settings.png)

In this screenshot, I am duplicating the `en/shapeshift/shapeshift-company` page into a Korean locale version of the same document. The resulting page naming is `ko/shapeshift/shapeshift-company`

**Final Settings**

The tabs at the top can be ignored for now.

![newpage-popup.png](/translation-workflow/newpage-popup.png)



