---
layout: post
title:  "Automated Weekly Reporting"
author: Mark
categories: [ Automation ]
image: /assets/images/automation.png
toc: true
beforetoc: As any project manager knows, there are management tasks that are handled on a repetitive basis and seemingly could be automated were it not for small nuances. This article addresses weekly reporting and potential solutions for automation.
description: As any project manager knows, there are management tasks that are handled on a repetitive basis and seemingly could be automated were it not for small nuances. This article addresses weekly reporting and potential solutions for automation.
---
## The Problem

When sending out emails/messaging for multiple projects to various stakeholders you cannot send out a generic template because the report needs to be populated with project/client relevant data.

### Example Report Template
## The Problem

When sending out emails/messaging for multiple projects to various stakeholders you cannot send out a generic template because the report needs to be populated with project/client relevant data.

### Example Report Template

> _Hi **<<Stakeholder Name>>**_
> 
> _This week we accomplished the following items:_
> 
> 1.  _**<<Accomplishment 1>>**_
> 2.  _**<<Accomplishment 2>>**_
> 3.  _**<<Accomplishment 3>>**_
> 
> _We have used **<<hours used>>** / **<<budgeted hours>>** hours.  
> __The breakdown is as follows:_
> 
> -   _Front-end Development: **<<Front-end hours used>>**_
> -   _Backend Development: **<<Backend hours used>>**_
> -   _Design: **<<Design hours used>>**_
> 
> _Next week we anticipate completing the following features:_
> 
> 1.  _**<<Upcoming feature 1>>**_
> 2.  _**<<Upcoming feature 2>>**_
> 3.  _**<<Upcoming feature 3>>**_
> 
> _Please let me know if you have any questions. I hope you have a great weekend._
> 
> _Best,_

The above is a typical example of a concise, yet detailed report that a PM may deliver on a weekly basis to his/her clients. The variables are identified in  **bold**  with << >> symbols on either side.
  
## Solutions

### Mail Merge

Microsoft Word has this functionality out of the box. You can reference a source of data, such as a spreadsheet, to generate multiple emails with data pulled from your spreadsheet.
  
>_See a complete walkthrough at  [Microsoft Support](https://support.microsoft.com/en-us/office/use-mail-merge-to-send-bulk-email-messages-0f123521-20ce-4aa8-8b62-ac211dedefa4)_
| Pros | Cons |
| --- | --- |
  | <ul><li>Easy to use</li><li>Fast</li></ul> | <ul><li>Cannot customise each subject line</li><li>Cannot be used outside of the Outlook Mail client (e.g if you want to post an update in another platform such as Basecamp/Teamwork).</li></ul> |
___  
