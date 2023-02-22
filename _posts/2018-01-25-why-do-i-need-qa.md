---
layout: post
title:  "Why Do I need a QA Engineer?"
description: Why is a Quality Assurance engineer necessary for development of software? Couldn’t I simply get my developers to QA/review their own work?
author: Mark
categories: [ Agile ]
image: assets/images/QAThumbnail.jpg
---
## Introduction
Why is a Quality Assurance engineer necessary for development of software? Couldn’t I simply get my developers to QA/review their own work? Could I get get developers to review each other’s work? These are all questions that I have come across at some point or other from multiple people.

Before I answer, let’s briefly summarize what QA is:

## What is QA?
QA is the analysis of functionality and overall appearance of your site / app. This can include (but is not limited to): Cross-browser testing, screen resolution compatibility testing, grammar, spelling, functionality.. the list goes on. QA is ideally approached from multiple angles.

When testing a simple ‘contact us’ form, the QA engineer would ensure that the email field ensures that a valid email address is entered, the name fields do not accept numbers, the name fields do not accept special characters, ensuring fields have limits so malicious users cannot overwhelm your system by entering large amounts of characters, etc.
![QA Meme]({{ site.baseurl }}/assets/images/needQA.png)

## QA Responsibilities

A QA engineer’s responsibility is to review each feature before it is released, suggest edits to issues and approve code before it reaches the product owner. Therefore, not only is the entire site under the QA engineer’s watchful eye, each part of the site is analysed during its creation.

## Why is QA Necessary For Development?

As you can see above, the responsibilities for QA are laborious. A dedicated amount of time by someone who knows your system is needed. Not only is QA needed for each release, regular testing across your site is critical to catch issues that may affect it from external sources.  
Example: Still running flash player on your site? Browsers are discontinuing support since it is considered deprecated technology. Your QA Engineer will (/would) know this.

## Can Developers QA Their Own Work?
The QA engineer should be a consistent team member, part of daily scrums and involved in feature development. Developers however,are assigned a particular module of the whole system and aren’t truly aware of the system as a whole. Not only is development typically modular, a developer has a completely different mindset and thought process. He/she may not consider all the scenarios a tester would consider.
They can definitely code review their peers but QA is a different game entirely.
