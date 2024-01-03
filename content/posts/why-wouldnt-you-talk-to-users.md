---
title: 'Why wouldn''t you talk to users?'
date: Sun, 02 Mar 2014 17:08:29 +0000
draft: false
tags: ['customers', 'lean', ]
---

I've hear it said that the best code is the code you don't write. The more code you have the more code that could have mistakes and that you have to remember how it works so you can maintain it.

TDD and [YAGNI](http://en.wikipedia.org/wiki/You_aren't_gonna_need_it) goes some way towards only writing the code you need, but how do you know what your tests should be in the first place?

**Involve your users**

You have to talk to users or customers or domain experts. Anyone who knows more about your domain than you. Us software people tend to think that we know what we are building is the right thing, but without validating your assumptions and finding your biases you will probably end up with features and code that aren't being used.

**Assumptions**

Assumptions can be anything from the best position for a button to whether people want or need to use what you are building. Testing out your assumptions early by putting your software, or at least your ideas, in front of users reduces risk by helping you make less mistakes and find out when you have made a mistake more quickly. It also stops wasting your time and energy building features that don't add value to your project.

**Bias**

By biases I really man cognitive biases, of which [there are many](http://en.wikipedia.org/wiki/List_of_cognitive_biases). Being aware of which ones you are most susceptible to can help prevent you from forming an incorrect idea about what people want.

For example, I know I sometimes fall afoul of the [curse of knowledge bias](http://en.wikipedia.org/wiki/Curse_of_knowledge), meaning that I can find it hard to see that others don't have the same technical or background knowledge as I do when I am thinking about usability. Knowing this means I can do something about it. I speak to users, do [hallway usability tests](http://www.joelonsoftware.com/articles/fog0000000043.html) and document what does or doesn't work for me refer back to next time.

In [Thinking, Fast and Slow](http://www.amazon.co.uk/gp/product/0141033576/ref=as_li_ss_tl?ie=UTF8&camp=1634&creative=19450&creativeASIN=0141033576&linkCode=as2&tag=jamjefblo-21) Daniel Kahneman suggests that there is a link between blood glucose levels and being effected by your cognitive biases, so when I am doing usability work I always make sure I eat plenty of fruit. I don't know whether this makes a real difference, but I feel like it helps so I keep doing it.

**Now for the really hard part**

When you are talking to people, especially about abstract ideas, you need to remember that not only do you need to be aware of when you are making assumptions and which biases might be affecting your decisions, but you also need to take into account other peoples biases and assumptions.

This is really hard because you don't know what is going on in their heads. Are they just telling you your idea is good because they don't want to hurt your feelings? Do they really think it's a good idea, but when it comes to it won't think it's worth paying for? Are their suggestions pushing you down the a route you don't want your product to go down or that don't fit with your overall vision?

In his book, [The Mom Test](http://www.amazon.co.uk/gp/product/1492180742/ref=as_li_ss_tl?ie=UTF8&camp=1634&creative=19450&creativeASIN=1492180742&linkCode=as2&tag=jamjefblo-21), [Rob Fitz](https://twitter.com/robfitz) calls this bad data. He suggests that there are three categories of bad data:

1.  Compliments
2.  Fluff
3.  Ideas

Rob's approach to dealing with bad data basically comes down to focusing back on the problem domain and current user behaviour. I really like this approach and find that it makes me much more confident in my decisions. I'd highly recommend The Mom Test to anyone who regularly talks to customers about ideas.

**The five whys technique**

Another approach I like to use is called the [5 whys technique](http://www.isixsigma.com/tools-templates/cause-effect/determine-root-cause-5-whys/). As you can probably guess this is simply asking why 5 times when someone tells you about something. This really helps you get to the real cause of the problem, allowing you to find a suitable solution, rather than take what you were told at face value.

For example (to use the canonical car won't start example given on wikipedia), 

_The vehicle will not start. (the problem)_

1.  _Why?_ - The battery is dead. (first why)
2.  _Why?_ - The alternator is not functioning. (second why)
3.  **_Why?_** - The alternator belt has broken. (third why)
4.  _Why?_ - The alternator belt was well beyond its useful service life and not replaced. (fourth why)
5.  _Why?_ - The vehicle was not maintained according to the recommended service schedule. (fifth why, a root cause)

By doing the same thing when we are talking to users or customers we can dig into the heart of the issue quickly and get past any solutions that they are presenting us with. Rather than them saying, "This button should go here", you can dig down to "The current position of the button is difficult to press whilst using a tablet".

When you use this technique an important thing to note is that you shouldn't just keep saying "Why?" as this will break down trust between you and your customer. Phrasing the question slightly differently each time by including some context gives them more confidence that you trust their opinion and that you aren't questioning why they do something like they do.

**What should you do next?**

If you don't already talk to your customers, start doing so. You will get a better understanding of your problem domain and the needs that your customers are interested in you fulfilling. Questioning the way you thinking about problems and validating your ideas will help you to build products that people want to use and reduce the amount of time you waste not adding any value. Understanding how other people think will help you focus on what people _actually_ need rather than what they _tell you_ they need. Using these ideas well can increase the chance of your product being successful and reduce the frustration of building something that no one wants.