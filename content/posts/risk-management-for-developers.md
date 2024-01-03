---
title: 'Risk Management for Developers'
date: Sat, 25 May 2013 14:22:30 +0000
draft: false
tags: ['Lean Startup', 'Risk', 'TDD', ]
---

Most developers have worked on projects which haven't been as successful as they could have been. Everyone has things they would do differently if they were to do it again (which is why you should be doing retrospectives). But what can you do to reduce the risk of a project failing? Firstly it's important to understand a little bit about what risk management actually is. In [Slack](http://www.amazon.co.uk/gp/product/0932633617/ref=as_li_qf_sp_asin_tl?ie=UTF8&camp=1634&creative=6738&creativeASIN=0932633617&linkCode=as2&tag=jamjefblo-21 "Slack"), Tom DeMarco defines it as "a discipline of planning for failure". I like to think of it as _planning to fail fast_. When I say fail in this context I don't mean the project won't be a success, just that a risk that you were exposed to has occurred. Taking a risk exposes you to things that could lead your project to be a long term failure. By failing sooner we can minimise the impact of those risks on the project. I like to think of risk management by breaking it down in to three parts.

1.  Identifying risks
2.  Risk mitigation
3.  Risk avoidance

Each of them is equally important, but the first one is always a good place to start. **Identifying risks** Whether you want to use pen and paper, post-its or a spreadsheet is up to you, but this step is crucial. List each risk and next to it the following

*   what it's potential impact?
*   how likely is it to occur?
*   what will you do if it does occur?
*   how will you know that it is starting to occur as early as possible?

**Risk mitigation** Have a plan to minimise the impact of a risk if it does occur. This could be related to an external factor or it could be something in the system you are building. For example, you might take a risk and use a NoSQL database rather than a relation one. The risk could be that the technology is less mature or it could be that only a couple of your developers have any experience in using it. Either way if it isn't working out then have a plan for how you can switch back to trusty old Postgres or MySQL. Another risk mitigation approach to take is to try and fail as quickly as possible. Not sure about the performance of a third party API? Load test it sooner rather than later. Not sure if users will find your new navigation concept easy to use? Get some one to use it now, don't wait until it is released (or even better release it now and measure movement around the system). **Risk avoidance** How can you avoid a risk going bad? For example, the team have decided to use a new cool, but new bleeding edge library. While there is probably a cost in using a different library, it could be worth it to avoid potential problems with the bleeding edge one. As a developer it is your job to decide whether the effort of moving to a more stable library is better than the risk of potential problems with a less stable one. **Conclusion** Risk management sounds boring, but it should be an essential part of most developers day to day thinking. Next time you are working on something and you think "it would be bad news if this doesn't work out" think about what you can do to reduce that risk or at least to find out sooner.