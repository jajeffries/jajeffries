---
title: 'Wildcard matching in apt-get'
date: Sat, 16 Nov 2013 12:02:13 +0000
draft: false
tags: []
---

I've never really played with some of the more advanced features of debian and ubuntu's package manager, but today I came across something useful. Ubuntu installs LibreOffice as part of a new installation, which I don't really want as I use Google Drive for most presentations and spreadsheets. To uninstall it I typed

> sudo apt-get remove libre

and pressed the tab button. There were lots of packages, but I couldn't see a base package that looked like it would remove everything. Just on the off chance that it might work I tried

> sudo apt-get remove libre\*

This came up with a big list of all the packages that I don't have installed and told me so

> ... Package 'libreoffice-help-el' is not installed, so not removed Package 'libreoffice-help-en-gb' is not installed, so not removed Package 'libreoffice-help-es' is not installed, so not removed Package 'libreoffice-help-et' is not installed, so not removed Package 'libreoffice-help-eu' is not installed, so not removed Package 'libreoffice-help-fi' is not installed, so not removed ...

But it also correctly identified the packages to be removed and asked if I wanted to remove them. I'm not sure whether this functionality is part of how the linux command line globs things or something built into apt-get. Either way, it might come in handy again some time.