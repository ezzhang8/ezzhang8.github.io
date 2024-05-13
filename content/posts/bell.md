---
author: "Eric Zhang"
title: "Reflecting on my time at Bell"
date: "2024-05-10"
description: "Applying popular technologies to niche problems"
tags: ["Vue.js", "Node.js", "Express.js", "SQL", "TypeScript", "Google Cloud Platform", "JavaScript"]
categories: ["themes", "syntax"]
series: ["Experience"]
aliases: ["bell"]
cover:
  image: /posts/bell/vault.png
  caption: Tour of the 'vault'-- the internet cables running underneath Bell's Toronto office.
ShowToc: true
Summary: Applying popular technologies to niche problems
TocOpen: true
weight: 1
---
## Background
I first joined Canada's largest telecom company last May as a summer student. Since then, I continued working for Bell part-time and then took a return offer for my second co-op work term. I'm so grateful to have spent a year building software with amazing people!

During my work terms, I worked primarily with full-stack web development. Our tech stack included Vue, Node, Express, and SQL. I also received training for and gained familiarity with Microsoft Power BI, given I worked for the **Contract Management Business Intelligence (CMBI)** team.

My work arrangements were primarily remote with occasional trips to the Downtown Toronto and Mississauga offices.

<figure class="entry-cover">
<img src="/posts/bell/geese.png"></img>
<p>A family of geese greets me to the Mississauga office</p>
</figure>

## Training
I spent my first few weeks on the job getting a comprehensive education about the telecom industry. Although not related directly to software engineering, I have always been passionate about the intersection between and software and hardware. Ultimately, I appreciated our lectures on central offices, copper decommissioning, outside plants, and fiber to the home, because they helped contextualize the work that followed.

## Main Project
<figure class="entry-cover">
<img src="/posts/bell/cdbstill.png"></img>
<p>A still from the Contractor Dashboard promotional <a target="_blank" href="https://www.linkedin.com/posts/activity-7042591626845716480-9NJm?utm_source=share&utm_medium=member_desktop">video</a>, published by our senior manager.</p>
</figure>

Contractor Dashboard is the project I was deployed to work on. It's mostly an internal application that bridges the gap between Bell corporate and its thousands of contractors. The website has many modules spanning many corners of the business, and contractors are only given access to relevant modules, using a Keycloak OAuth server. It's responsive and mobile friendly, and is often used on the go. 

### Wireless Home Internet 
My first assignment was to create a module for managers and contractors within the [Wireless Home Internet](https://www.bell.ca/Bell_Internet/promotions/wireless-home-internet) (WHI) division. WHI connects those in rural and remote areas to the Bell network via cell towers instead of hard cables, providing an essential service to many Canadians with few other connectivity options.

However, not every potential customer can actually make use of the service. Some customers may have no line of sight to the nearest cell tower for a multitude of reasons. The company wants to survey what went wrong in these instances to optimally direct future infrastructure investments.

The existing workflow was to send contractors a Google Form to fill out. This wasn't the best for security, and made it difficult to query the collected data to hold contractors to surveying a certain percentage of missed customers. Everything also had to go through the contractors' managers before reaching the on site contractor at the customer's location to fill out a survey.

By shifting this process to Contractor Dashboard, contractors' surveys now go directly into Bell's database where they can be queried. I also created a scorecard to keep track of completion metrics, greatly reducing the workload of managers on this issue, and improving the integrity of data collected.

### Bell Smart Home
My next assignment was to extend my previous work into the realm of smart homes. Bell has a stake in smart home systems owing to their acquisition of Alarmforce. (Remember that commercial?) <br/><br/>
<div style="text-align: center">
<iframe  width="560" height="315" src="https://www.youtube.com/embed/awwvKlzAHdw?si=SImLGWqFhnIlp-_y" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

A program known as Security Business Net (SBN) has to be run by a contractor to ensure the system is armed and sensors are operational. Otherwise, Bell could risk liability for a breach of an alarm system by an intruder. 

With help from my manager in gathering data from Alarmforce, we expanded my module on Contractor Dashboard to enable contractors to report a follow-up for when the SBN software failed. This helps ensure as many Bell Smart Home customers are linked up properly.

### Claims
Bell's property is damaged on a daily basis, sometimes in ridiculous ways. Whether it's a car accident, construction negligence, or copper wire thievery, there's got to be a claim against someone written up eventually. The company was using antiquated claims software from the early 2000s, with the license to that due to expire soon. 

I joined my colleagues towards the end of the development cycle for incorporating claims management software to Contractor Dashboard, taking on a few story points each sprint to increase our team's output leading up to launch.

Some work I did for Claims include keeping track of the claims adjuster, troubleshooting SQL queries, and saving user preferences in LocalStorage.

<figure class="entry-cover">
<img style="width: 100%; height: 300px; object-fit: cover" src="/posts/bell/claim.png"></img>
<p>Best of luck to whomever writes up <a target="_blank" href="https://twitter.com/Bell/status/1788668606726721938">this claim</a>.</p>
</figure>

## Side Quests 
Over the course of my work terms, I occasionally explored some other technologies.
### Google Cloud Platform
When I joined the team, Contractor Dashboard stored the raw binary of files in an SQL table. This wasn't a sustainable way to handle file uploads, and could cause considerable strain on the server. My module for WHI used this system initially, but was first to transition off of it, as part of a company-wide commitment towards cloud storage.

I migrated files stored on the SQL server to a bucket on GCP, after restructuring my backend code for any API endpoints related to file uploading.
### Power BI Reporting
On an ad-hoc basis, I updated some Power BI dashboards and scorecards for internal metrics. While not an expert, I definitely gained some experience with this software in a professional setting.
### Documentation
Took a deep dive into Swagger in my final weeks of the internship, to adequately document everything about my backend code, while writing everything I knew to Confluence. For any potential employers reading this--- I seek to keep my deliverables operational as long as possible, even after I leave the company. I take ownership of my work, and will invest in communicating both the nitty gritty technical details to the broad high-level overviews to the team.
## Lessons Learned
* `SELECT *` is bad!!!
* I will never use a DBMS as a file management system. It's like storing treasured family photos in a spreadsheet.
* `git blame` came in extremely handy when I was given 30 minutes to find the cause of a production issue.
* No more generic error messages. This wasn't a hackathon project anymore, it's very helpful to code errors so bug reports can identify the problem for you.
## Exciting Anecdotes
Some cool stories from the past year, less work-related!

### Wizards @ Raptors
I was lucky to grab some Raptors tickets that Bell was giving away. Bell owns 37.5% of the Raptors, so it's really great to see them letting us in on the fun. They were awesome seats, just 14 rows from the action, and I got to bring a friend!

<figure class="entry-cover">
<img style="margin-left: 50%; width: 33%; height: 300px; object-fit: cover; transform:translate(-50%, 0%);" src="/posts/bell/wfriend.jpeg"></img>
<p>Enjoying the game with my friend, <a target="_blank"href="https://www.linkedin.com/in/aryan-s1/">Aryan Sharma</a></p>
</figure>


This was the game on November 13<sup>th</sup>, 2023, where the Raptors erased a 23 point deficit to beat the Wizards at Scotiabank Arena. Pascal Siakam put up a season-high of 39 points, in what was one of his last games before being traded to the Pacers. 

Halfway through the game, I joked to my friend that watching a Raptors game would be free, but watching them win would cost us again. Glad we ultimately stayed to see a victory and one of the last 2019 champs perform his best for the team.

<figure class="entry-cover">
<img style="width: 100%; height: 300px; object-fit: cover" src="/posts/bell/rapswin.jpg"></img>
<p>Raps win 111-107!</p>
</figure>

### Laptop Upgrade
CGI, our IT provider, is extremely stringent on scheduling us for upgrading equipment. My work laptop was due to be upgraded, but it was either go into the office on final exam day, or bear with my clunky overheating laptop for another 5 months.

I managed to do well on my [ECE 222](https://uwflow.com/course/ece222) exam that evening despite commuting from Waterloo to Mississauga and back. Totally worth it in the long run, since my productivity was boosted for the next 5 months.

## Conclusion
I couldn't have asked for a better start to my software engineering career. Heartfelt thanks to everyone in CMBI who made this opportunity possible. Looking forward, I'm excited to bring the experience I developed at Bell to future internships!