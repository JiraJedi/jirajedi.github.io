---
layout: post
title:  "Show Sum Of Epic Children's Estimates"
author: Mark
categories: [ Jira, Automation ]
image: assets/images/EpicsDashboard.png
description: 
toc: true
beforetoc: 
---
## Introduction
It can be useful to see how much effort is required for an Epic based on it's children but while the functionality to see a sum total is available to some extent for Stories and Tasks, this is not the case for Epics. 

This post shows you how to track scope for an Epic and its children and show that data in dashboard. Definitely useful for reporting!

## Create text fields for 
`Remaining Work`
`Total Time Spent`
`Delta`

## Automation
### Trigger & Conditions
<figure>
    <img src="/assets/images/automationSection1.png"
         alt="Automation Section 1">
</figure>
**Step1: Define your automation trigger**
We can use any desired trigger but for the purpose of limiting how often I want this automation to occur, I've set it to trigger whenever work is logged.

**Step 2: Exclude Issue Types**
Set the issue fields conditon so that the `Field` = "Issue Type" and the `Condition` = "is not one of" `Value` = "Epic" , "Sub-task".
- We don't want this automation to trigger for the Epic value because we want to calculate the Epic's *children*. 
- We don't want this automation to trigger for the Sub-task value because we want to calculate the Epic's *children's aggregate totals which includes the sub-tasks*.

**Step 3: Branch Rule & Lookup**
Add a branch rule `Type of related issues` = "Epic (parent)" and restrict it to your project to avoid spending global automation runs.
Then, add the "Lookup Issues" action to the branch rule. The JQL should be `"Epic Link" = "{{issue.Epic Name}}"`
What we are doing here is defining that we want the following actions to take place within Epics that are parents of the issues that have triggered the automation flow. Then, we are creating a lookup variable that stores

### Calculate Totals
This is where our newly created fields come in.
<figure>
    <img src="/assets/images/editIssueFields.png"
         alt="Edit Issue Fields">
</figure>
#### Calculate Sum Of Children's Original Estimates

#### Calculate Sum Of Children's Time Spent

#### Calculate Sum Of Children's Remaining Estimates (Delta)
---
### Color Status


## Dashboard
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIxMjQ2Mjc4ODFdfQ==
-->