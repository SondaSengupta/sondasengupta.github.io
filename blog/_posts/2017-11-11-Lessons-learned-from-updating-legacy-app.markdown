---
layout: post
category: blog
title:  "Lessons Learned from Updating A Legacy App"
img: "/images/http.jpg"
excerpt: "Over the course of a year and a half, our team took a monolothic legacy application and moved chunks into microservices. Here is what we learned."
date:   2017-11-11
---
Over the course of a year and a half, our team took a large monolothic legacy application and broke it down into microservices. These are the lessons we learned from launching a brand-new app as our business used the legacy application.

### Find the earliest minimally viable product that is adoptable and stick to it.
Scope creep was huge. Find the earliest minimally viable product that is adoptable and stick to it. The scope kept changing and the project grew by months. Find your steel thread -- the reason your project exists and the real pain your business is spending loads of money to help you to solve-- and stick to it. Often times I think we worried too much about how adoptable it was so we had the tendency to add more features to increase it. Know what adoptable means to you ahead of time and make sure the development team and the business agree.

### Keep the architecture flexible because they won't know what they want. And neither do you.
It is easy to have a grand vision of what the architecture will be, but you will always know the LEAST about a project when you first begin. To that end, if you "tighten" the bolts of a project too early, you may find that you may have some costly refactoring ahead of you as the project evolves. There was an instance that we had an inheritance structure around a core tenent only to find out that there were children that didn't needed some inherited fields overwritten. This caused us to completely rework our design, but if we had taken a more flexible approach, the rearchitecture step would not have been so painful.

### Business engagement is extremely important. Engage early and keep engagement.
While working up to the minimum viable product, it is easy to lose business interest because this development work does not affect their day to day operations. However, you need their input to make sure a feature is coded with the right requirements and to catch any oddities hopefully before rework becomes expensive. Thus, its important to show them finished features and user stories, even if it only in a QA environment, and perhaps even set up time for them to specifically play with the product as development continues. That way, during the big MVP launch, nothing is a surprise and they are excited about being able to use the product in production.

### Push to really understand business rules and processes. Know what's a process versus a workaround.
Perhaps in their old application, they are used to thinking of a certain concept because they've always done it that way. However, that process was only in place because the app allowed X number of characters. Maybe the old application only allowed a certain number of fields so a field maybe doing double duty in conveying information. It is important to dig down into why customers do things a certain way to understand whether it is true business logic that needs to be in the new system or an artifact of an old idea. 

### Add validation as early as you can.
It maybe tempting to deploy a certain feature without any level of validation/business logic around it in the hopes of putting it in front of your customers faster. However, keep in mind, because you don't have validation, you are allowing any sort of data to enter your database, significantly decreasing the data quality. Then when you add validation at a later time, you will have to address the data descrepencies that show up.



