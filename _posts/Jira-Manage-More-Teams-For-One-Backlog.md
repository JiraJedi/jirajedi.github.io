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

- We create Components that correspond to their respective teams. 
- Components are assigned to issues
- Team Boards' filters are modified to include any issues that have the team's Component assigned to them.
- Team Boards/backlogs now show the issue from the original backlog


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0NTE3MDgyODYsLTE4OTU5MzA5NjJdfQ
==
-->