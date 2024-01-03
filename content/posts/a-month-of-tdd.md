---
title: 'A Month of TDD'
date: Fri, 07 Feb 2014 12:43:47 +0000
draft: false
tags: ['kata', 'TDD', ]
---

NOTE: I actually wrote this yesterday, but didn't get chance to post it. There may be an additional post today.

**Background**

I'm starting a new job in a few weeks where I will be using some technologies outside of my usual toolkit, namely node.js and Ruby. I've used them both for bits and pieces in the past, but I've never worked on a large code base in either.

I'm also looking to improve my TDD skills. I have used TDD everyday in the last 18 months and a little on other projects before that. While I am by no means inexperienced I feel like I could benefit from some concentrated learning to learn some more advanced techniques.

**The Challenge**

I am aiming to do a kata in Ruby or JavaScript at least three times a week for the next month and I intend to blog about what I learn each time.

**What I learnt today**

Today I worked on the checkout kata in Ruby. This taught me a few interesting things about Ruby.

- blocks
- Ruby uses the oddly named 'inject' method rather than foldl or reduce
- regex literals are similar to JavaScript literals
- test classes inherit from Test::Unit::TestCase
-test methods must start with the word test

I also used the self shunt pattern to practice using tell don't ask. I feel that this was simpler than adding mocks, at least initially and still helped me to think about interactions between objects in terms of message passing.