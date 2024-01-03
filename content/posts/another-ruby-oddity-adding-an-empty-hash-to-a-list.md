---
title: 'Another ruby oddity: adding an empty hash to a list'
date: Fri, 05 Jun 2015 13:58:03 +0000
draft: false
tags: []
---

When adding a hash to a list you need to call push with brackets or you end up with an empty list. \[code\] 2.2.0 :001 > \[\].push {} => \[\] 2.2.0 :002 > \[\].push({}) => \[{}\] \[/code\] You can also use << which doesn't need brackets either. \[code\] 2.2.0 :003 > \[\] << {} => \[{}\] \[/code\] This isn't the behaviour I'd expect, but I'm pretty sure there's a logical reason for this. [Drop me a tweet](http://twitter.com/jjeffries1) if you have any idea why.