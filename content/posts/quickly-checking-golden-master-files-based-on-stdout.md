---
title: 'Quickly checking golden master files based on stdout'
date: Fri, 09 Dec 2016 15:48:24 +0000
draft: false
tags: []
---

A couple of people were interested in quick ways of checking program outputs against golden masters last night at XP Manchester. Here's a couple of one liners I use. This assumes your program outputs to stdout and you've already created a file with the output. Firstly using powershell if I'm on windows without bash \[code\] (compare-object (get-content goldenmaster.txt) (yourcommand) | Measure-Object).Count \[/code\] Or alternatively using bash \[code\] diff goldenmaster.txt <(youcommand) >/dev/null; echo $? \[/code\]