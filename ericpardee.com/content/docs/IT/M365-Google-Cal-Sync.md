---
title: M365 to Google Calendar Sync
authors: [{'name': 'Eric Pardee'}]
published: Tue, 15 Jun 2021 07:45:38 GMT
---


# Microsoft Office 365 Calendar to Google Workspace Calendar Sync

Having multiple calendars with different events on each one is a sure path to double bookings. Get organized and reliable by subscribing to your Outlook Calendar in Google Calendars.

![Microsoft Office 365 Calendar to Google Workspace Calendar Sync](/blog-post6.webp-1.jpg)

Complete hypothetical here but imagine that you use Google Workspace for your email and calendar but your employer uses Microsoft Office 365/Outlook.

Let’s say hypothetically that you wanted to be able to see your upcoming work calendar _together_ with your personal calendar such that you can _look in one place_ to see what time you have events throughout the day. Can this even be done?

This is especially applicable when working from home, while also occasionally working flexible hours, sometimes outside of traditional business hours. Or like when you're trying to book a Doctor's appointment during the workweek.

Originally I found [this method of sharing your Outlook Calendar](https://www.howtogeek.com/435975/how-to-show-an-outlook-calendar-in-google-calendar/) using an [ICS link](https://en.wikipedia.org/wiki/ICalendar) however [Google only allows you to sync every 6 to 24 hours](https://webapps.stackexchange.com/questions/6313/how-often-does-google-calendar-update-its-other-calendar-feeds). This **delay** makes the validity of the events in the calendar suspect so in practice, I ended up still checking both calendars, which kind of defeats the purpose.

Fortunately, [someone has written a simple script](https://github.com/derekantrican/Google-Apps-Script-Library), a script that reminds me of [a sync script that I wrote while at Atlas Digital that syncs Sage Time and Attendance (Insperity TimeStar) time-off events to Google Calendar](https://github.com/epardee/timestar-to-gcal).

At first, I was suspect, the [Stack Exchange post that referenced the script article](https://webapps.stackexchange.com/questions/6313/how-often-does-google-calendar-update-its-other-calendar-feeds) had comments from someone in 2019 that said the [Google Apps Script](https://developers.google.com/apps-script/) was not feature-complete. So I did some research and it turns out that it is now a feature-rich application and I gave it a shot. Although I wouldn’t mind running this as a function in Kubernetes, as a scheduled cronjob, similar to [my Craigslist renew job](https://www.ericpardee.com/selling-smart-on-craigslist/), I find that [this Google Apps Script](https://script.google.com/home/projects/1BOk8MDLbLaHh6SwG1M1tsgNXjkcC-79LE0QoipRuTDxbO3fMVvqoROQD/edit) is sufficient.

And let me tell you it works, really well! I think a sync every 15 minutes is sufficient. But what’s great about this, I have it set up such that it will delete events, so and I don’t have any work events from the past, all I’m seeing on my personal calendar is work future events, which is all I need this for planning.

![Microsoft Office 365 Calendar to Google Workspace Calendar Sync](/cal-script.webp.jpg)

If this is your situation, give it a shot!
[https://script.google.com/home/projects/1BOk8MDLbLaHh6SwG1M1tsgNXjkcC-79LE0QoipRuTDxbO3fMVvqoROQD/edit](https://script.google.com/home/projects/1BOk8MDLbLaHh6SwG1M1tsgNXjkcC-79LE0QoipRuTDxbO3fMVvqoROQD/edit)\
(The installation instructions are at the top of the script, it's pretty straightforward)
