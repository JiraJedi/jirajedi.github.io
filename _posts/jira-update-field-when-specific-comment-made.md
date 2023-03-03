---
layout: post
title:  "Jira: Auto Update Fields When Specific Comments Are Made"
author: Mark
categories: [ Automation, Jira ]
image: assets/images/jiraComment.png
description: 
toc: true
beforetoc: inspired by a solution I provided [in a reddit post.](https://www.reddit.com/r/jira/comments/jwqhe2/comment/gctzc1e/?utm_term=35604468914&context=3&utm_medium=comment_embed&utm_source=embed&utm_name=296167ca-2a77-11eb-b0c5-0ee6fa4404d1&utm_content=timestamp)
---
## Introduction
This post addresses how to recognise when a specific string of text has been added to a Jira comment and then posting the comment into a given field via automation.

## User Story
As a Product Owner, I would like when a comment is added to an issue, if it starts with a given value, its contents will be copied to a custom field so that I can access information withoud digging through comments.

## How To Implement

1.  Add your  _trigger_  (I suggest 'When Issue Commented')

2.  Add a new  _condition_  ->  _Advanced Compare Condition_
    1.  Set the  `First Value`  to {{issue.comments.last}}
    2.  `Condition`  should be 'Starts with'
    3.  `Second Value`  is 'xxx' (or whatever you want)
        
3.  Add a new  _action_  ->  _Create Variable_   
    1.  `Name`  the variable 'Link'        
    2.  Set the  `Smart value`  to {{issue.comments.last}}
        
4.  Add a new  _action_  ->  _Edit Issue_    
    1.  Choose Sharepoint Link as the  `Fields To Set`        
    2.  In the empty  `Sharepoint Link`  field, enter {{Link}}
<!--stackedit_data:
eyJwcm9wZXJ0aWVzIjoiYXV0aG9yOiBNYXJrXG5mZWF0dXJlZE
ltYWdlOiBhc3NldHMvaW1hZ2VzL1xuIiwiaGlzdG9yeSI6Wy02
OTYxOTk2MjksNDA3NzQ5MDg2LDE3MjQwMzk3NjEsLTE3MzQ1MD
Q0NzAsLTIwMDAzNDkwMTEsMTg5Mjk2MTkwMV19
-->