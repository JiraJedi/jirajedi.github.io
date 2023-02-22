---
layout: post
title:  "Unblock An Issue When The Blocker Is Resolved"
author: Mark
categories: [ Jira, Automation ]
description: Linked blockers are pesky!
image: assets/images/autoThumbnail.png
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

> **Name:**	`Unblocks`<br>
> **Outward Link Description:**	`unblocks`<br>
> **Inward Description:**	is `unblocked by`

Click ‘Add’ and you will have sucessfully set up a new link. Try using it on an existing Jira issue to verify it is there.

### Auto Unblock Completed Blockers
This is where the Jira automation suite comes in.

#### Steps
The following steps describe a rule that auto unblocks issues upon completion:
> 1.  Navigate to the Automation suite via the Kanban/Scrum board OR via the project settings
> 2.  Select  ‘Issue Transitioned’ as the trigger and configure it to activate upon transition to ‘DONE’. Save.
> 3.  Add a new condition:  ‘Related issues condition’ and configure:
>     1.  Related Issues:  `Linked Issues`
>     2.  Link Types:  `Block`s
>     3.  Condition:  `Are Present`
>     4.  Save
> 4.  Add a Branch Rule and set the following configurations:
>     1.  Type of Related Issues:  `Linked Issues`
>     2.  Link Types:  `Blocks`
>     3.  Save
> 5.  Add a New Action (_**under the branch rule**_):  ‘Link Issues’ and configure:
>     1.  This Issue:  `is unblocked by`
>     2.  Issue:  `Trigger Issue`
>     3.  Save
> 6.  Add a New Action  **Outside of the branch rule**:  ‘Delete Issue Links’ and set to unlink ‘blocks’ and Save.  
> 7.  Final Step: Publish and Enable your rule

![Automation Overview]({{ site.baseurl }}/assets/images/automationOverview.png)

If your workflow allows for issues to be transitioned back from ‘DONE’ you may wish to have rules auto-block if issues are shifted back. You can easily do this by duplicating the above rule, changing the transition in step 1 from ‘To Done’ to ‘From Done’ (to specified or all statuses) and replace the link changes in steps 3-6 from ‘blocks’ to ‘is unblocked by’.

## Summary

This article covered adding a new link type to indicate unblocked issues and adding automation to unblock/restore blockers from transitioned Jira issues.

If you have questions or feedback, feel free to drop by the comments section.
