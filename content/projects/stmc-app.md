---
author: "Eric Zhang"
title: "STMC iOS App"
date: "2020-10-15"
description: "A student life app I developed for my high school!"
tags: ["app", "ios", "swift", "xcode"]
categories: ["themes", "syntax"]
series: ["STMC App"]
cover:
  image: /projects/stmc-app/stmc.png
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

>*View schedules, class rotations, and timetables in advance to always be prepared for the future.
This app also is compatible with Widgets, allowing you to add a snapshot of the school day to your home screen.
Designed for St. Thomas More Collegiate students, staff, and community, this app will keep you updated about everything on campus.*


## Inception 
### September 2017 – May 2018
"What's the schedule for tomorrow?" and "when's next class?" were the most common questions asked by my classmates. School started at 8:23 AM, and lunch was at 11:52 AM. Classes were 63 minutes long, with an 11 minute recess and 3 minutes to move between each class. Eighth graders like me were expected to keep track of these *literally* odd lengths of time.

Sometimes school would end 25 minutes early and follow an entirely different schedule, but it was never communicated effectively.

### June 2018
I ran for the student council with a popular running mate against other very popular candidates. Unexpectedly, we win the only 2 seats reserved for grade 8s.

### September 2018
The odd schedule system was revised to make the length of each class, transition, and break a multiple of 5 minutes. However, it came with even more variations for assemblies and special classes. The same inconveniences from before remained.

### May 2019
I'm now running for re-election, thinking of creative campaign ideas to win support. I had seen content creators on YouTube as young as me develop iOS apps. An app that displays schedules could be a success, and could be expanded for other functions! Although this was ambitious, expectations for campaign promises were set very low. 

I got elected.

## Development
### June 2019
To run the Xcode, the app that makes apps, I needed a Mac. Sadly, I couldn't find $1,600 for a decent MacBook Pro setup. Luckily, my school's IT director was preparing to recycle this 2012 Mac mini. I upgraded the hard drive to a solid-state drive and the RAM to 16 GB, which cost $120. 

### July 2019 – November 2019
This first phase of development involved watching hours of YouTube tutorials. In the end, I made something pretty ugly, but at least it was taking shape.

### November 2019 – March 2020
I found working with UIKit to be difficult, so I decided to experiment with SwiftUI, Apple's new declarative UI builder. I immediately clicked with the concept, and felt I had made more progress in a day than in months of trying UIKit.

I made my first API call, using the Google Calendar API to retrieve the school calendar with all the events as JSON, and put each event in a `List`.

### March 2020 – June 2020
The COVID-19 pandemic emerges and shuts down the world. At least for a while, an app like this wouldn't be needed for school. However, online school gave me lots of free time to pursue this project.

### June 2020 – August 2020
Progress rapidly accelerates. I am learning in a week what used to take a month for me to grasp. To get this done in time for the next school year, I definitely had to make some *creative* design choices.

The REST API for the backend was written in PHP, and I used a SQLite database. I couldn't afford to pay for a server from DigitalOcean or AWS, for example. PHP would work easily with my school's hosting provider, and I would get a free subdomain to host my backend.

I also had to create a website for app admins to change information. This also used PHP. Although this setup was not ideal, it was suitable for the number of users I expected, no more than 700 students.

## Release & Subsequent Updates
### September 2020 – October 15, 2020
I met with the principal and the IT director to discuss deploying the app school-wide. They managed to get an organizational Apple Developer account set up for free as a non-profit educational institution. I then was able to compile my project and release it to the App Store!

Since the first release on October 15, 2020, I have made several updates. A visual overhaul was done in early 2021, and several changes to the class schedules were made to accomodate changes in the COVID-19 situation in British Columbia. 