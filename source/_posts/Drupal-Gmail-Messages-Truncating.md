---
title: Drupal Gmail Messages Truncating
date: 2016-10-23 09:46:47
tags:
---

Drupal has a built-in email system that sends out emails by default. However, there are modules such as "Mimemail" that allow you to send out emails using HTML templates rather than Drupal's default plain-text emails.

Sometimes an issue can occur while using Mimemail that sends out emails in HTML format that are too large for Gmail viewers. This causes an unpleasant user experience because the email is clipped and you would have to click a link to view the entire email. 
The email would read as follows: "[Message clipped] View entire message for gmail user" with a read more link below.
A client of ours was experiencing this issue, so I did some digging. I found from reading through [this Drupal.org discussion](https://www.drupal.org/node/581328) and the documentation for the MimeMail module how to fix this issue. 

First, you need a mail.css in the theme of your Drupal site.
Second, you need to enable a side that comes with MimeMail. It's called Mime Mail CSS Compressor. What this does is convert your mail.css into inline CSS in the HTML emails MimeMail sends out. With this enabled, the Gmail truncated messages are no longer an issue.
