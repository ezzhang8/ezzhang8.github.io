---
author: "Eric Zhang"
title: "STMC iOS App"
date: "2023-05-04"
description: "A student life app I developed for my high school!"
tags: ["iOS Development", "Swift", "SwiftUI", "Xcode", "PHP", "SQL"]
categories: ["themes", "syntax"]
series: ["STMC App"]
cover:
  image: /projects/stmc-app/STMCAppPreview.png
aliases: ["stmc-app"]
ShowToc: true
TocOpen: false
weight: 1
---
<p align="center">
  <img style="filter: drop-shadow(0px 0px 5px #909090);" src="/projects/stmc-app/stmc.png" height="100px" width="100px"/>
</p>
<p align="center">
  <a href="https://apps.apple.com/ca/app/stmc/id1535346830?itsct=apps_box_badge&amp;itscg=30200" style="display: inline-block; overflow: show; border-radius: 13px; width: 150px; height: 63px;"><img src="https://tools.applemediaservices.com/api/badges/download-on-the-app-store/black/en-ca?size=150x36&amp;releaseDate=1602633600&h=59db9ed20649a95abfeafc2f412683ca" alt="Download on the App Store" style="border-radius: 13px; width: 150px; height: 63px;"></a> 
</p>

## Why this project? 
"What's the schedule for tomorrow?" and "when's next class?" were some of the most common questions asked by my peers. School started at 8:23 AM, and lunch was at 11:52 AM. Classes were 63 minutes long, with an 11 minute recess and 3 minutes to move between each class. Even eighth graders were expected to keep track of these odd lengths of time. Sometimes school would end 25 minutes early and follow an entirely different schedule, but it was never communicated effectively, and some people would be left waiting at school for a ride home.

## What does it do? 
*STMC* is a tabbed application with four views. 

The default view, Schedules, shows the period rotation for upcoming school days, exact times for each class, and school events on that day. Students in my high school took 8 classes year round, with 4 on one day and 4 others on the next day, labelled A through H. The order was scrambled by moving the first class of one day to the end of the next day in the rotation.

The Explore tab shows six divisions of the school, *houses*, and points they've collected by demonstrating school spirit. Below that, *Bulletins* show brief announcements and news by administration. Below that, there are some static resources of the school such as locker and room locations.

The Notifications tab shows past push notifications sent out by school officials. Push notifications were enabled in the app for students to get announcement information at an instant at the end of the school day.

The last tab, Resources, shows more static information about the school such as its website, phone number, and links to other tools used by students.

## How was it made?
### Tech Stack
#### Frontend
I made the frontend interface using SwiftUI in Xcode 13. At the time, there were some features lacking in SwiftUI so I implemented some workarounds with UIKit as well. I used a 2012 Mac mini for development and my iPhone 8 for testing.
#### Backend
The information presented in the app is fetched from API endpoints that were written in PHP, that retrieved information from a SQLite database. PHP is a bit odd in retrospect, but I chose it because it would require the least configuration of school servers.

I was given FTP access to a subdomain on the school website. Using PHP I could create endpoints with files. SQLite was chosen because the database was just a file, and I could execute queries on my local machine and then transfer it to the server. I would approach this differently if I worked on this today, but I think I made the most out of my technical ability at the time.

The endpoint for getting school schedules and events used Google Calendar's PHP library with a service worker account granted access to the school's private calendar. For user content, I created a dashboard using React.js where admins could update information associated with bulletins, schedules, and notifications.
### Deployment
I got the support of school administrators in getting my project deployed and operational. My school was able to register for a free Apple Developer Program account as a nonprofit institution, and I was able to release my project using App Store Connect. I made several updates since the app was first released in October 2020. I did all this work for free, as I was passionate about software development, and the school gave me an opportunity to gain experience with professional tools.