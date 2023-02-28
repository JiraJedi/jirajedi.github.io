---
layout: post
title:  "Jira: How to Manage More SCRUM Teams For One Backlog"
author: Mark
categories: [ Agile, Jira ]
image: assets/images/oneBacklog.png
description: We want a single backlog that a Product Owner can control the priorities of and work with teams to distribute tasks so that they appear in their respective backlogs and boards
toc: true
beforetoc: 
---
## Introduction
I often see the question: "How do I manage a product backlog that spans multiple teams / projects in Jira?".  

The typical scenario is a Product Owner overseeing a backlog that multiple teams need to pull issues from. These teams often have their own Projects in Jira and it doesn't make sense to have them flip between multiple projects / boards. It would certainly make prioritizing tasks a nightmare.

## Solution Overview
We want a single backlog that a Product Owner can control the priorities of and work with teams to distribute tasks so that they appear in their respective backlogs and boards. To do this we:
-  Create Components that correspond to their respective teams. 
- Assign Components to issues.
- Modify the filters of Team Boards to include any issues that have the team's Component assigned to them.

✅ Team Boards/backlogs now show the issue from the original backlog.

## How To Implement The Solution

### Create Components For Respective Teams
First, create components for each team or project that will be working on the backlog. Components can be created by selecting "Components" in the project's left sidebar menu. You can then create a component for each team or project, and assign it a name and description. This will help to categorize the work and allow each team to focus on their respective tasks.
 
### Assign Components to issues
When creating or editing an issue, you can assign it to a component by selecting the appropriate component from the drop-down menu of the `Component` field. This will help to ensure that each issue is properly categorized and assigned to the correct team or project.

### Modify The Team Boards' Filter
To adjust a backlog/board to include issues with specific components, modify the board filter. This can be done by:
1. Going to the board settings (the 3 dots on the top right of the page -> `Board Settings`)
2. Selecting  "<font color=blue>Edit Filter Query</font>" beneath the `Saved Filter`. 
3. You can then modify the filter to include the component(s) that correspond to the team or project you want to view issues for by appending `OR component = "**COMPONENT NAME**"` to the JQL query. 
>E.g 
>`Project = ABC OR component = "COMPONENT NAME" ORDER BY Rank ASC`  

4. Click 'Save' at the top of the page. This board will now see any issue in Jira that is assigned the Component as well as any issues in the project itself.

## Conclusion
Overall, using a single backlog in Jira to distribute work to multiple teams and projects can help to streamline the work process and ensure that each team is aligned on the highest priority tasks. By creating components, assigning issues to components, and modifying board filters, you can ensure that everyone is on the same page and working towards the same goals.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3OTg2MDM0MjcsLTE3MTY4MDk0OThdfQ
==
-->