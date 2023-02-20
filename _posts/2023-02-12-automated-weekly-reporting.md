---
layout: post
title:  "Automated Weekly Reporting"
author: Mark
categories: [ Automation ]
image: assets/images/automation.png
toc: true
beforetoc: As any project manager knows, there are management tasks that are handled on a repetitive basis and seemingly could be automated were it not for small nuances. This article addresses weekly reporting and potential solutions for automation.
description: As any project manager knows, there are management tasks that are handled on a repetitive basis and seemingly could be automated were it not for small nuances. This article addresses weekly reporting and potential solutions for automation.
---
## The Problem

When sending out emails/messaging for multiple projects to various stakeholders you cannot send out a generic template because the report needs to be populated with project/client relevant data.

### Example Report Template

> _Hi **{Stakeholder Name}**_
> 
> _This week we accomplished the following items:_
> 
> 1.  _**{Accomplishment 1}**_
> 2.  _**{Accomplishment 2}**_
> 3.  _**{Accomplishment 3}**_
> 
> _We have used **{hours used}** / **{budgeted hours}** hours._
> 
> **_The breakdown is as follows:_**
> 
> -   _Front-end Development: **{Front-end hours used}**_
> -   _Backend Development: **{Backend hours used}**_
> -   _Design: **{Design hours used}**_
> 
> _Next week we anticipate completing the following features:_
> 
> 1.  _**{Upcoming feature 1}**_
> 2.  _**{Upcoming feature 2}**_
> 3.  _**{Upcoming feature 3}**_
> 
> _Please let me know if you have any questions. I hope you have a great weekend._
> 
> _Best,_

The above is a typical example of a concise, yet detailed report that a PM may deliver on a weekly basis to his/her clients. The variables are identified in  **bold**  with <font color="#00ab6b">"{ }"</font> symbols on either side.
  
## Solutions

### Mail Merge

Microsoft Word has this functionality out of the box. You can reference a source of data, such as a spreadsheet, to generate multiple emails with data pulled from your spreadsheet.
  
>_See a complete walkthrough at  [Microsoft Support](https://support.microsoft.com/en-us/office/use-mail-merge-to-send-bulk-email-messages-0f123521-20ce-4aa8-8b62-ac211dedefa4)_

<font color="#00ab6b">Pros</font>	
<ul><li>Easy to use</li><li>Fast</li></ul>

<font color="red">Cons</font>
<ul><li>Cannot be used outside of the Outlook Mail client</li></ul>

___  

### Macros

If you have some background in coding this next suggestion will be easier to pickup.

Utilizing macro tools such as PhraseExpress, AHK, etc (**or even actual code!**), you can create a program to pull data from a chosen repository (such as a spreadsheet), populate a template and send to your chosen destination.
<figure>
    <img src="/assets/images/pexpress.png"
         alt="PhraseExpress Script">
    <figcaption>A Weekly Report PhraseExpress Macro</figcaption>
</figure>


The above example utilizes the PhraseExpress tool. It performs the following functions when called:

1.  Opens the given Teamwork URL and waits for the page to load
2.  Enters the string 'Weekly Update | ' followed by the current date and then hits the TAB key to navigate to the message box
3.  Enters the first part of the message and then begins to list completed work for the past week as given by the data source (Excel Spreadsheet). It is set to list 3 cells, hitting the enter key and bulleting each completed item.
4.  The next step provides the used hours and the budgeted hours for the month, pulled from the sheet
5.  Lastly, similar to step 3, the program lists upcoming work to be worked on in the upcoming week and closes out the message

Note that this could have been streamlined to pull urls and stakeholder names from the spreadsheet as well.
<figure>
    <img src="/assets/images/spreadReport.png"
         alt="A Weekly Report Source Spreadsheet">
</figure>

<font color="#00ab6b">Pros</font>	
-   Can have custom subject lines per message
-   Can use other messaging platforms
-   Greater range of data sources available (not restricted to Sheets)
-   Can be combined with other macros for a complete workflow
-   Can be run faster than a mailmerge once setup

<font color="red">Cons</font>
- More difficult to setup, especially without technical experience

___

## Conclusion

This article covered 2 potential solutions for automating reports: Microsoft Word’s Mail Merge feature and creating a Macro in PhraseExpress. Both solutions have their pros and cons, but as always, use the right tool for the situation you are in.
