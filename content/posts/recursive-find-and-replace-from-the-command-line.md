---
title: 'Recursive find and replace from the command line'
date: Mon, 11 Aug 2014 11:46:53 +0000
draft: false
tags: []
---

I always have to look up how to recursively find and replace in multiple files. Here is what I usually use:

`find . -type f -print0 | xargs -0 sed -i 's/old/new/g'` where old is what you want to find and new is what you want to replace it with. This will find all the files under the current directory, pipe it to sed, which will find and replace in the files.