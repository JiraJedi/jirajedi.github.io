---
layout: post
title:  "Never stopped worrying or loving the bomb"
author: Mark
categories: [ Jira, Automation ]
description: Linked blockers are pesky!
image: assets/images/14.jpg
---
## Problem Intro

Jira allows users to track blocked tasks by ‘linking’ them to their blockers. For example, issue EX-1 may be linked to EX-2 with a ‘blocked by’ link and vice versa. However, once the ‘blocker’ (EX-2) has been completed, EX-1 will not reflect this on a surface level. You need to delve into the issue details and check on the status of EX-2.

This can affect a user that is tracking blocked issues by card color or if a report is showing ‘blocked’ issues, it is difficult to reflect that an issue is no longer ‘blocked’.

## Proposed Solution

We create a new type of issue link: Unblocks/Unblocked to reflect when a blocker has been resolved. We then add automation to ensure the appropriate link changes occur.

> ❗️ _I.e: We replace the ‘blocks/is blocked by’ link with ‘unblocks/is unblocked by’_  _upon blocker resolution._

## How To Do It
---
### Create New Issue Link

Following  [Atlassian’s guidelines for creating a new link (Add New Link Section)](https://confluence.atlassian.com/adminjiraserver/configuring-issue-linking-938847862.html), you will want to create a new link type:
![JIra Admin Interface]({{ site.baseurl }}/assets/images/issueLinking.png)

**Name:**	`Unblocks`
**Outward Link Description:**	`unblocks`
**Inward Description:**	is `unblocked by`
