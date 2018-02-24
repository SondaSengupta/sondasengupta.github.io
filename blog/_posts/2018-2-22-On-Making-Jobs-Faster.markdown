---
layout: post
category: blog
title:  "On Making Jobs Faster"
img: "/images/speed.jpg"
excerpt: "We wanted to make a complex job faster. Here are some tips to tried to speed up performance."
date:   2018-2-22
---

Just recently, our team was faced with this question when we created a job that took 10 hours to finish. The task was to move data from one application to another, deleting some bad data along the way, and make sure each application published messaging events so subscribed services would know changes have been made. We kicked off the job with an api call in a specific jobs controller in code and which used our normal update/delete methods to update the database and send messages.

Even though this job was a one-time thing, there are definitely some downsides to the 10 hour duration. For one, anytime we wanted to make changes to this job as we were in the process of creating it, we had to wait 10 hours before we realized whether it was successful. As this was a complex job, this development and testing time frame significantly slowed this feature down. Also, no one wanted to stay late 10 hours waiting for this thing to finish. At a few hours, we figured we could watch a movie or play board games as a team we finished deployment, but 10 hours afterhours from a full day of work makes for a long night.

Here a few things we did to make sure we did all we could to make this job faster.

### Limit Slow Tasks.
Looping is slow. Do you really need nested loops or can there be a way to limit the number of times you have to touch each element. As much as I love LINQ queries, the terse syntax makes it so easy to write iterations without thinking. 

Database calls are slow. Because of a previous design, we were utilizing a pagination method to bring back data, but we realized that we could bring it back all at one time instead of successful SQL calls. Since we controlled the time frame we ran the job, we knew we could schedule for a time that wouldn’t slow the server down, so we changed it to a one time query instead. 

Messaging events are slow. We had been publishing events for each data change on an object, instead of publishing one message per object which included all changes. Not only was the former slower, but we found that it was buggier because the sheer amount of published messages guaranteed that subscribers could easily process messages out of order. 

In a general sense, be ruthless in code about where you can make easy performance enhancements. We made sure that we used async/await when we could to get parallelization benefits. We combed the code to see where we can do bulk changes, bulk saves, bulk message publishing. 


### Use Profilers to Analyze Slow Points.
Profilers can be such a godsend when you’re combing through thousands of lines of code or multiple sql statements. Generally how a profiler works is that you turn it on, call the specific task you want, stop the profiler and then the profiler will spit out areas that your application hangs the most. Visual Studio comes with some really good code profiling right out of the box and SQL Server Management Studio comes with SQL profiling as well. We use Entity Framework for database changes, and we wanted to know whether the sql statements it created were significantly slowing down the job. Running the SQL profiler allowed us to see that the time was negligible, which confirmed the decision to not rewrite the job straight ADO.NET or Dapper. 

### Analyze Business Need.
As a rule, whenever our objects change, we log the change in history tables. With this job as well, we were saving all changes we made to each object, so each change was saved in history which meant double, sometimes triple the amount of sql calls. Turns out that the business honestly didn't care about saving history information because most of it was bad data anyway that they just wanted to delete.

#### Helpful Links
- [Profile Application Performance in Visual Studio](https://docs.microsoft.com/en-us/visualstudio/profiling/beginners-guide-to-performance-profiling)
- [Start SQL Profiling](https://technet.microsoft.com/en-us/library/ms173799(v=sql.110).aspx)