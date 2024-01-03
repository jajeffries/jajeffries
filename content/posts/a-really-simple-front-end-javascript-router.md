---
title: 'A really simple front end javascript router'
date: Thu, 15 May 2014 19:58:49 +0000
draft: false
tags: ['javascript', 'js', ]
---

I dislike using large frameworks and libraries for front end work. I think I read a quote somewhere that you use librarie, but frameworks use you. I couldn't agree more and in fact where possible I prefer to use snippets or gists, such as [John Ressig's MicroTemplates](http://ejohn.org/blog/javascript-micro-templating/). The following funciton is intended to be used in a similar way, just copy it into your project. It listens to the popstate event and routes the change to the correct address based on an object you pass in.

```
function setupRoutes(routes) {
    window.onpopstate = function(event) {
        if (routes[location.hash.slice(1)]) routes[location.hash.slice(1)]() 
    };
}
```

So if you had a main page and a menu page you might call setupRoutes as follows.

> setupRoutes({ main: function () { // load your main page html }, menu: function () { // load your menu page html } });  

Typically I use the routes object to transition to new views and remove unused elements from the DOM in phonegap applications. In you HTML you can change the hash state by linking to a hash. For example,

> <a href='#main'>Main</a>

would call the main function in the previous example. You can also change it from javascript by setting the location.href to the hash you want. For example,

> location.href= '#main'

This keeps the code nice and simple, it's easy to debug and leaves you in complete control of how you change between views.