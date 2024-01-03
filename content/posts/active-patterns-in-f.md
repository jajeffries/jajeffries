---
title: 'Active Patterns in F#'
date: Sun, 19 Aug 2012 16:37:16 +0000
draft: false
tags: []
---

While learning F# one of the most unique things I've come across is active patterns. They allow you to split data into named partitions which can be used when pattern matching. For example:

> \> let (|Pass|Fail|) sucess = - if sucess then Pass else Fail - ;; val ( |Pass|Fail| ) : bool -> Choice<unit,unit> > let ExamResult res = - match res with - | Pass -> printfn "%s" "You Passed!" - | Fail -> printfn "%s" "You Failed. Sorry!" - - ;; val ExamResult : bool -> unit > ExamResult true - ;; You Passed! val it : unit = ()

I'm just starting to really play around with active patterns, but already I can see a significant reduction in code and an increase in readability from having to use discriminate unions instead.