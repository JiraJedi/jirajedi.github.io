---
layout: post
title:  "Jira: How to Manage More SCRUM Teams For One Backlog"
author: Mark
categories: [ Agile, Jira ]
image: assets/images/automation.png
description: 
toc: true
beforetoc: 
---
## Introduction
I often see the question: "How do I manage a product backlog that spans multiple teams / projects in Jira?".  

The typical scenario is a Product Owner overseeing a backlog that multiple teams need to pull issues from. These teams often have their own Projects in Jira and it doesn't make sense to have them flip between multiple projects / boards. It would certainly make priortizing tasks a nightmare.

## Solution Overview
We want a single backlog that a Product Owner can control the priorities of and work with teams to distribute tasks so that they appear in their respectie backlogs and boards. To do this we:
-  Create Components that correspond to their respective teams. 
- Assign Components to issues
- Modify the filters of Team Boards to include any issues that have the team's Component assigned to them.

✅ Team Boards/backlogs now show the issue from the original backlog.

## How To Implement The Solution

Create Components that correspond to their respective teams. 
   - Assign Components to issues
  Modify the filters of Team Boards to include any issues that have the team's Component assigned to them.

<!--stackedit_data:
eyJoaXN0b3J5IjpbNzg0NjY1MjU2LC0xMDM3MDUwMzM2LC0xOD
k1OTMwOTYyXX0=
-->