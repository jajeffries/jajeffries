---
title: 'Finding files that have been removed in git'
date: Thu, 08 May 2014 15:04:37 +0000
draft: false
tags: ['git', ]
---

Another git thing I keep having to look up is how to find when a file was deleted. The following command does it easily.

> git log -1 -- <file name>