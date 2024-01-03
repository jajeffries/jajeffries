---
title: 'Thoughts on purescript after a couple of weeks of use'
date: Fri, 07 Aug 2015 11:35:27 +0000
draft: false
tags: []
---

Most of the work I do at the moment involves dynamic languges (mostly ruby and javascript) and I often feel like I have to work slightly differently without a type system to support me, especially in javascript. A few weeks ago, I saw [Becky Conning](https://twitter.com/BeckyConning) give a talk at the Manchester Lambda Lounge on purescript, which peaked my interest in finding an alternative to javascript for work in the browser. Purescript is a haskell like strongly typed language, which compiles to javascript. It supports javascript interop via it's FFI module and compiles to much more readable javascript than other alternatives, such as clojurescript. I've spent a couple of weeks using it and mostly I like it. Here are a few highlights for me.

*   I find being able to drive the structure of your program by defining types makes it a lot easier to think about how changes will affect other parts of your program.
*   The FFI is wonderfully simple to use. It allows you to define type signatures for external code, call multi argument functions as if they were purescript functions using Fn2 and even curry them. It's a little bit fiddly the first time you use it, but I found it fairly easy once I got my head round it.
*   The Eff monad, is similar to haskell's IO monad and is used for defining types of side effects. Unlike haskell you need to be more specific about the type of effects. For example, a function which outputs a log message to the console would have the following constraint for Eff:
\[code\] forall e. Eff (console :: CONSOLE | e) Unit \[/code\] This probably looks a bit different to what you would writ in haskell, which would probably be something like: \[code\] Unit -> IO() \[/code\] because in purescript you have to be explicit with forall, whereas in haskell it is implied (I think).*   QuickCheck. I've used ports of quickcheck in other languages (ruby, .Net etc.), but they've never been as elegant as haskell or scala, but the purescript port is excellent.
*   Easy to install and good tooling. Purescript is available in npm, as is the preferred build tool, pulp. I found getting started with pulp, to be very simple and easy. Just run the following and you have deployable code ready for your browse:
\[code\] pulp init pulp browserify \[/code\]

When I get chance, I'll try and put up some examples of what I've been working on, but in the meantime head over to [purescript's github page](https://github.com/purescript/purescript) and to find out more.