---
layout: post
title:  "Running Automations In Bulk"
author: Mark
categories: [ Agile, Project Management ]
image: assets/images/automation.png
description: 
toc: true
beforetoc: 
---
Problem
Running bulk tasks in Jira doesn't always allow animatoins to kick in on time. E.g bulk transition tasks to `QA`. Trigger is transition to QA. Will fail because Jira moves too fast. 

My Use case
QA Script to che

Solution 
is to add re-fetch issue data as an action between trigger and checks/followup actions.

Bulk Limit is ~500 (Check)
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTI0NTc3NTk3NCwtMTI0MTU1NDI1NV19
-->