---
title: 'Git stash recipes'
date: Tue, 20 Jan 2015 14:00:58 +0000
draft: false
tags: []
---

Git's stash command is one of the most used features in my toolbox. Here are a few of my favourites. **Undo everything since the last commit** \[code\] git stash \[/code\] **Get back what you just undid** \[code\] git stash apply \[/code\] **Get back what you just did and remove the stash** \[code\] git stash pop \[/code\] **Remove a stash without applying it** \[code\] git stash drop \[/code\] **View the last thing you stashed** \[code\] git stash show -p stash@{0} \[/code\]