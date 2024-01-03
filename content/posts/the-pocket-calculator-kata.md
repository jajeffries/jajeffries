---
title: 'The Pocket Calculator Kata'
date: Mon, 10 Feb 2014 19:19:30 +0000
draft: false
tags: ['kata', 'TDD', ]
---

Today I had a quick go at [Patchspace's](http://patchspace.co.uk/) Ash Moran's [Pocket Calculator kata](https://github.com/patchspace/katas/tree/master/pocket_calculator). I tried this once before when I was taking my first steps into BDD and found it quite challenging. In retrospect I think part of this might have been partly due to my lack of familiarisation with the tools I was using, specifically SpecFlow.

I have since started just using unit tests when doing BDD as I find it avoids the "framework" distraction and let's you and the customer really concentrate on the problem at hand.

Today I started with turning the calculator on by pressing the AC button. I was expecting the screen to display "0.". With this test quickly passing and a quick refactor to pass in a display object rather than getting the total, I moved on to the next test: entering numbers.

I easily added this feature by adding an if statement to my press method. With my tests passing again I tried to find a way of [removing the if](http://www.antiifcampaign.com/). I couldn't see a simple way of doing this in Ruby. In C# I would pass in a dictionary mapping types to lambdas which would take two arguments: the button pressed and the current value being displayed. I'm a bit unsure about how good a solution this as it isn't very object oriented. I suppose that it could be wrapped in a class instead though. I decided to leave the if in for now and move on to the next test.

Next up was entering multiple numbers. I changed the part of the code that handled numbers to prepend the button press to the existing display. I was still unhappy with the if, but unfortunately I had run out of time.

I will continue my fight against conditionals tomorrow and hopefully get chance to write up my findings.