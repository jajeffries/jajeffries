---
title: 'TDD as a tool'
date: Wed, 14 May 2014 12:10:31 +0000
draft: false
tags: []
---

So over the last few weeks there has been a lot of talk on twitter about the benefits of TDD and the traditional red, green, refactor cycle. I have a few thoughts about each article, so I thought I'd put them together here. First Bob Marshall wrote about [thinking about refactoring as waste](http://flowchainsensei.wordpress.com/2014/04/15/code-refactoring/). Specifically he talks about whether it is type 1 or 2 muda

*   Type I muda: Non-value-added tasks which seem to be nevertheless necessary.
*   Type II muda: Non-value-added tasks which can be eliminated immediately

I see refactoring as a useful tool for finding my way to a good design or through a difficult problem, especially when I am tired or distracted. However, if I am wanting to go quickly I will tend to think more about my design upfront and refactor less. I think this is what Bob is talking about to some extent. By thinking slightly more about our designs we could reduce the amount of refactoring we do. This would be interpreting refactoring as type 2 muda. However I think that we would lose some of the benefits of refactoring:

*   Better understanding of the code base
*   Faster track to working code
*   Less crystal balling
*   YAGNI
*   DRY

I appreciate that you can get some of these benefits without refactoring, but I feel that I learn more from doing the refactoring than not. Perhaps over time I will feel less benefit from this. Next up was my colleague Gemma Cameron's [response](http://rubygem.me/2014/04/22/is-refactoring-waste/). She highlights a technique that significantly sped up my TDD. She suggests refactoring with an awareness of the next test. For example, writing the next test commenting it out and then refactoring to get the code in a good position to get the next test passing.

1.  Red,
2.  Try to get green in one, simple step,
3.  Comment out red  test,
4.  Green,
5.  Refactor,
6.  Red,
7.  Green

Again this reduces waste as we are refactoring with a goal in mind, not just refactoring to make everything pretty (although there is also benefit in this). Next up, in a [blog post](http://david.heinemeierhansson.com/2014/tdd-is-dead-long-live-testing.html) David Heinemeier Hansson (@dhh) says

> Test-first units leads to an overly complex web of intermediary objects and indirection in order to avoid doing anything that's "slow"

I agree with this to some extend, but I tend to favour integration tests where I don't fake very much. This still helps me with YAGNI, but I _do_ find this leads to slower tests, which makes me favour smaller composable programmes, as per the unix philosophy. This has it's own set of problems, but I think it solves more than it creates (a rant for a future blog post).

One point that I do agree with David about is that we shouldn't do TDD (or anything) just because it is what everyone is doing or because it's cool. We should learn about it, understand the principles behind, the advantages and disadvantages, and then make a decision about whether it is good or bad. Only then can we think about Bob Marshall's question of whether what we are doing is type I or type II muda. Otherwise we are just guessing.

Finally [Uncle Bob's article](http://blog.8thlight.com/uncle-bob/2014/05/02/ProfessionalismAndTDD.html), talks about TDD being a step towards professionalism. I agree that a lot of the developers I know who I would consider professional to practice TDD, but also agree that it is not a prerequisite for professionalism.

I found the analogy in the article about midwives washing their hands particularly interesting, but I wonder whether this is accurate in the size of the impact. The difference with TDD and hand washing is that it is possible for TDD to have a negative affect when done by inexperienced developers on a complicated code base, whereas washing your hands is easy and has no negative impacts that I can think of. The problem with TDD is that it is hard to learn how to do it well, so teaching yourself while working on something complicated, will probably slow you down, give you a lack of confidence in your tests and often ultimately result in ceasing using TDD.

So to conclude, I will continue to use TDD as I find it a useful tool for building a good design and regression testing my changes. I don't always use it, but I'm certainly glad I can use it when I need to.