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

## Create fields for 
`Remaining Work` - text field <br>
`Total Time Spent` - text field <br>
`Delta` - text field

`Color Status` - dropdown selector with options for 
1. 🟢 _On Track
2. 🟡 _At Risk / Delayed
3. 🔴 _Red

## Automation
### Trigger & Conditions
<figure>
    <img src="/assets/images/automationSection1.png"
         alt="Automation Section 1">
</figure>
**Step1: Define your automation trigger** <br>
We can use any desired trigger but for the purpose of limiting how often I want this automation to occur, I've set it to trigger whenever work is logged.

**Step 2: Exclude Issue Types** <br>
Set the issue fields conditon so that the `Field` = "Issue Type" and the `Condition` = "is not one of" `Value` = "Epic" , "Sub-task".
- We don't want this automation to trigger for the Epic value because we want to calculate the Epic's *children*. 
- We don't want this automation to trigger for the Sub-task value because we want to calculate the Epic's *children's aggregate totals which includes the sub-tasks*.

**Step 3: Branch Rule & Lookup** <br>
Add a branch rule `Type of related issues` = "Epic (parent)" and restrict it to your project to avoid spending global automation runs.

Then, add the "Lookup Issues" action to the branch rule. The JQL should be `"Epic Link" = "\{\{issue.Epic Name\}\}"`

What we are doing here is defining that we want the following actions to take place within Epics that are parents of the issues that have triggered the automation flow. The lookup provides us with a variable to reference that points to the associated Epic.

### Calculate Totals
This is where our newly created fields come in. We add another action in the branch rule "Edit Issue Fields" and modify the following fields:
<figure>
    <img src="/assets/images/editIssueFields.png"
         alt="Edit Issue Fields">
</figure>
#### Calculates Sum Of Children's Original Estimates
`Remaining Work` = `{{lookupIssues.Remaining Estimate.sum.divide(3600)}}h`
#### Calculates Sum Of Children's Time Spent
`Total Time Spent` = `{{lookupIssues.timeSpent.sum.divide(3600)}}h`
#### Calculates Sum Of Children's Remaining Estimates (Delta)
`Delta` = `{{issue.Original Estimate.divide(3600).minus(lookupIssues.timeSpent.sum.divide(3600)).minus(lookupIssues.Remaining Estimate.sum.divide(3600))}} hours`

---
### Color Status
This is the cherry on top 🍒! The following actions will determine the color status set for the Epic.
1. Add an "Advanced Compare Condition" to the branch. The `First value` = `{{issue.Delta}}`. The `Condition` = "greater than". The `Second value` = "-1"
2. Add an "Edit Issue" action: Field to set is `Color Status` = 🟢  _On Track
3.  Add another "Advanced Compare Condition". The `First value` = `{{issue.Delta}}`. The `Condition` = "less than". The `Second value` = "0"
4. Add another "Edit Issue" action: Field to set is `Color Status` = 🔴 _Red

<figure>
    <img src="/assets/images/automationSection2.png"
         alt="Automation Section 2">
</figure>

> ❗️ Make sure you publish your new rule! Try it out by adjusting adding a time entry to a User Story / Task.

## Dashboard
It's great to see this data at an Epic level but it's not super easy to show in reporting. This is where a Jira Dashboard can come in to display this data cleanly.
<figure>
    <img src="/assets/images/EpicsDashboard.png"
         alt="an Epics Dashboard">
</figure>
1. [Create a filter](https://community.atlassian.com/t5/Jira-Software-questions/How-do-i-create-a-new-filter-in-new-JIRA-UI/qaq-p/714010) that shows the Epics that you want to show.
2. In your Jira dashboard, Add a Filter Results widget and set the Saved Filter option to your newly created filter. The columns to display are:
		<br>a. Issue Type
		<br>b. Key
		<br>c. Summary
		<br>d. Orginal Estimate
		<br>e. Total Time Spent
		<br>f. Remaining Work
		<br>g. Delta
		<br>h. Color Status

> Be Sure to hit Save!
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTU1MTc1NzcxMiwxNDI2MzI0OTA2LC0xMD
A2OTQ1NzQwLDExMzY4MDAzMDgsLTQ1NTI1NTkzOCw4ODMyNzYx
NzAsMTU0MDAzODgwMF19
-->