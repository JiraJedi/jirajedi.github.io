---
layout: post
title:  "Jira: Auto Update Fields When Specific Comments Are Made"
author: Mark
categories: [ Automation, Jira ]
image: assets/images/automation.png
description: 
toc: true
beforetoc: 
---
## Problem
As a Product Owner, I would like Jira to store infomrtionat 

### **Steps**:

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
ltYWdlOiBhc3NldHMvaW1hZ2VzL1xuIiwiaGlzdG9yeSI6Wy0x
OTUwNzY1OTk1LC0xNzM0NTA0NDcwLC0yMDAwMzQ5MDExLDE4OT
I5NjE5MDFdfQ==
-->