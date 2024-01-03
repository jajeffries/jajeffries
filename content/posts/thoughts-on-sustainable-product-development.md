---
title: 'Thoughts on sustainable product development'
date: Sun, 20 Aug 2017 12:29:53 +0000
draft: false
tags: []
---

I've been working across several client products over the last couple of years and have noticed a couple of common problems which contribute negatively to the longevity of the projects. **Knowledge Loss** When projects move between teams or people working on the product move on (or even the project moving between companies, which can be common in an agency setting) some knowledge is lost of

*   How the code works
*   The features of the system
*   Why particular decisions were made
*   What to do it something goes wrong

I've been thinking recently about how we can minimise the impact of these issues to make projects more sustainable. Some ideas I've got so far

*   Pair programming
*   Executable specifications
*   [Architectural decision records](http://thinkrelevance.com/blog/2011/11/15/documenting-architecture-decisions)
*   Incident reports
*   Lightweight documentation (such as the [C4 Model](http://www.codingthearchitecture.com/2014/08/24/c4_model_poster.html))
*   Consistent use of ubiquitous language
*   Automate everything (it has a secondary effect of being documentation)

**Brittle code that's hard to change** When developers aren't confident in their knowledge of the system they're working on I find they can be more likely to try and make smaller changes and refactor less. Over time this leads to

*   duplication
*   code that's hard to understand
*   code that's hard to change
*   low test coverage

Once a code base has started down this path I see there a few things needed to correct this

*   Increase test coverage on areas of code that change frequently
*   Refactoring to improve code
*   Gradual refactoring to improve the architecture

I'll probably write some more on this over the coming months as I work on more client products.