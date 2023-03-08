---
layout: post
title:  "Jira: Auto Update Fields When Specific Comments Are Made"
author: Mark
categories: [ Automation, Jira ]
image: assets/images/jiraComment.png
description: 
toc: true
beforetoc: 
featured: true
---
## Introduction
This post addresses how to recognise when a specific string of text has been added to a Jira comment and then posting the comment into a given field via automation.

## User Story
As a Product Owner, I would like when a comment starting with a given value is added to an issue, its contents will be copied to a custom field so that I can access information without digging through comments.

## How To Implement
In the following example, we are looking for a Sharepoint link and adding the comment with this link to a `Sharepoint Link` field.

1.  Add your  _trigger_  (I suggest 'When Issue Commented')

2.  Add a new  _condition_  ->  _Advanced Compare Condition_
    1.  Set the  `First Value`  to {{ issue.comments.last }} 
    2.  `Condition`  should be 'Starts with'
    3.  `Second Value`  is 'xxx' (i.e the text you want to identify)
        
3.  Add a new  _action_  ->  _Create Variable_   
    1.  `Name`  the variable 'Link'        
    2.  Set the  `Smart value`  to \`{{issue.comments.last}}\`
        
4.  Add a new  _action_  ->  _Edit Issue_    
    1.  Choose Sharepoint Link as the  `Fields To Set`        
    2.  In the empty  `Sharepoint Link`  field, enter `\{{Link}}`\

> ❗️Remember to save and publish your automation!
<!--stackedit_data:
eyJwcm9wZXJ0aWVzIjoiYXV0aG9yOiBNYXJrXG5mZWF0dXJlZE
ltYWdlOiBhc3NldHMvaW1hZ2VzL1xuIiwiaGlzdG9yeSI6WzIx
MjEzMDM3MzAsLTE5MTQ3Mzc0MiwtMjQyNzEyNDgxXX0=
-->