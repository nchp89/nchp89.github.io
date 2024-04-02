---
layout: post
title: "Graybar: Optimizing Hadoop Ingests"
---
<hr>

#### The Need For Data
In my professional experience working as a Sr Advanced Analytics Developer at Graybar Electric, I worked in a variety of roles. Sometimes I would focus on software development and my days were spent writing Python and SQL. At other times I would concentrate on developing data visualization tools in Qlik for the consumption of business users external to our team. 

Regardless of the task I was working on, one thing was always the same: the need for up-to-date, reliable data.

Our team leveraged an on-prem Hadoop cluster to store and analyze the vast quantities of data produced by the day-to-day business. After about a year of working on the team, I began transitioning into a data engineering role and learned more about Hadoop and the braoder concept of distributed computing. 

##### The Shift to Data Engineering
What prompted my shift into a data engineering role was the emergence of a new and serious problem: the process to update the team data lake each day was severely outdated and was no longer trustworthy. 

The troubled process was written at a time when the team required just 24 data tables to conduct all of their work. By this time in the teams lifespan, we needed over 150 tables to be up-to-date each morning we came into work, and that number was only growing. It was time for an upgrade.

#### The Problem

The old data ingestion process had three major issues: speed, visibility, and reliability. A new process would have to address and improve each of these three parts.

##### Speed
From start to finish, it took about 22 hours for the old process to perform a complete update on all of our data tables. If the team was expected to work 8 hours a day, they should expect to have reliable data for at least that duration. The most they could hope for at this juncture was for 2 hours of stable data. It goes without saying that this status quo was beyond unacceptable.

##### Visibility
When a data table ingestion failed, it failed silently. The only way to learn of a failed update was to either look into the endless log files or to stumble upon an error while browsing data that one thought was up-to-date. Of course, outdated data can be hard to detect for end users, especially when relying on downstream data that has already been manipulated in some way, and even more so when there is an <i>expection</i> that the data has been updated. 

##### Reliability
Finally, when a table ingest did fail (something that happened all too often), there was no automated process to handle that failure. It just failed and moved on to the next table as if nothing had happened. That meant that any tables that failed during a given ingest had to be manually updated if they were to be used that day. This produced a lot of unnecessary extra work for the team, and it distracted us all from more important and valuable work.

#### The Solution

A teammate and I sat down together one day and began combing through the code that made up the old process. After a few days of brainstorming and testing ideas, we came up with a solution. It would be a completely new process built on five ideas: 

<ol>
    <li>Parallel Processing</li>
    <li>Deltas</li>
    <li>Priority Queue</li>
    <li>Email Notifications</li>
    <li>Automatic Retries</li>
</ol>

##### Parallel Processing

##### Deltas

##### Priority Queue

##### Email Notification

##### Automatic Retry


#### Results




Myself and a fellow team member rewrote the ingest process from the bottom up. We used parallel processing to ingest smaller tables in parallel, and for large tables implemented a delta process where only records that had been changed or added were ingested rather than the entire data source. 

This drastically reduced the time taken for daily data ingestion from 22 hours to around 7 hours. With this improvement, the team was able to build new dashboards in Qlik that could provide other teams within the business up-to-date information to assist their needs.