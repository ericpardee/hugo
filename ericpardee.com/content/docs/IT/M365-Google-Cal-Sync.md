---
title: Unifying M365 and Google Calendars
authors: [{'name': 'Eric Pardee'}]
published: Tue, 15 Jun 2021 07:45:38 GMT
---

# Integrating Outlook and Google Calendars

With working remotely, flexibility becomes a cornerstone of our professional lives.\
Integration is not just a convenience—it's an imperative.\
Why not integrate your professional Outlook Calendar into personal Google Calendar?

![Unifying M365 and Google Calendars](/blog-post6.webp-1.jpg)

## Work Meets Personal

Imagine a scenario: You're navigating Google Workspace for personal matters while your professional life revolves around Microsoft Office 365/Outlook. Ideally, wouldn't you prefer a merged view of your work and personal events?

In my quest for integration, I initially experimented with [sharing the Outlook Calendar via an ICS link](https://www.howtogeek.com/435975/how-to-show-an-outlook-calendar-in-google-calendar/).

A limitation surfaced. [Google's syncing mechanism operates in a 6 to 24-hour window](https://webapps.stackexchange.com/questions/6313/how-often-does-google-calendar-update-its-other-calendar-feeds), casting shadows of doubt over the real-time authenticity of the events. Consequently, I often found myself reverting to the dual-calendar check, defeating the very objective.

## Discovering the Perfect Sync Tool

Fortune favors the persistent. I happened upon [a promising script](https://github.com/derekantrican/Google-Apps-Script-Library). This code reminded me of a [synchronization script from my Atlas Digital days, which aligned Sage Time and Attendance events with Google Calendar](https://github.com/epardee/timestar-to-gcal).

Initial skepticism about this script arose from a [2019 Stack Exchange commentary](https://webapps.stackexchange.com/questions/6313/how-often-does-google-calendar-update-its-other-calendar-feeds) which highlighted the [Google Apps Script](https://developers.google.com/apps-script/) as incomplete. Yet, delving deeper, I discovered its evolution into a feature-loaded tool. While I toyed with the idea of adapting this into a Kubernetes function, akin to [my Craigslist renew routine](https://www.ericpardee.com/selling-smart-on-craigslist/), the [current Google Apps Script](https://script.google.com/home/projects/1BOk8MDLbLaHh6SwG1M1tsgNXjkcC-79LE0QoipRuTDxbO3fMVvqoROQD/edit) stood robust.

## Successful Integration

The outcome? Absolute synchronization delight! With updates every 15 minutes and an auto-clear function for past work events, my personal calendar now exclusively displays future work-related tasks, streamlining my planning process.

![Streamlined Calendar Syncing Process](/cal-script.webp.jpg)

Confronted with similar scheduling challenges?\
Embark on this integration journey:
[Google Apps Script Integration Guide](https://script.google.com/home/projects/1BOk8MDLbLaHh6SwG1M1tsgNXjkcC-79LE0QoipRuTDxbO3fMVvqoROQD/edit)\
(Begin the setup using the clear instructions provided at the start of the script.)
