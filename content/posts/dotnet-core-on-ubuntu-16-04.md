---
title: 'DotNet Core on Ubuntu 16.04'
date: Wed, 15 Jun 2016 18:47:07 +0000
draft: false
tags: []
---

I've been playing around with dotnet core on linux on an old laptop. I just went to install it on my new laptop running ubuntu 16.04 and found that it won't be supported until the RTM release. In the meantime here is a work around where I basically installed the old version of libicu (which I think is something to do with unicode).```
wget http://security.ubuntu.com/ubuntu/pool/main/i/icu/libicu52\_52.1-3ubuntu0.4\_amd64.deb

sudo dpkg -i libicu52\_52.1-3ubuntu0.4\_amd64.deb

`sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet/ trusty main" > /etc/apt/sources.list.d/dotnetdev.list'

sudo apt-key adv --keyserver apt-mo.trafficmanager.net --recv-keys 417A0893

sudo apt-get update` `sudo apt-get install dotnet-dev-1.0.0-preview1-002702`
```