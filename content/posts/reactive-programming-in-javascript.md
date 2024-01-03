---
title: 'Reactive programming in JavaScript'
date: Tue, 06 Jan 2015 21:40:15 +0000
draft: false
tags: []
---

Reactive programming is something of a hot topic at the moment. While the concepts have been around for a while, it's popularity has increased over the last few years since Microsoft released Reactive extensions for .NET (Rx.NET). It has been open sourced and now there are ports to almost every language, from Java (RxJava) to Ruby (rx.rb). Here I'm going to give a quick introduction to the JavaScript version: RxJS. **So what are reactive extensions?**

> RxJS = Observables + Operators + Schedulers

Observables are the core of rx. An observable is something that produces a stream of data. For example, we can produce a stream of integers asynchronously using the interval method. \[code language="js"\] Rx.Observable.interval(1000) \[/code\] The resulting observable will emit a count every second. To access the emitted values we need to subscribe to the observable. \[code language="js"\] Rx.Observable.interval(1000).subscribe( function (x) { console.log(x); }); \[/code\] This will print every number it receives from the observable to the console. So in this case the output would be: \[code\] 0 1 2 ... \[/code\] Next up we have operators. Operators perform operations on the stream of data from an observable. Operators fit into one of four categories:

1.  Filtering - getting rid of some of the stream
2.  Transforming - changing the stream
3.  Inspecting - looking at the contents of the stream
4.  Aggregating - collecting data from the stream and putting it together to make something else

The simplest of these (and the one we will focus on in this article) is filtering. We can filter using the filter method. For example, if we wanted to only subscribe to the even numbers we could insert a call to filter before subscribe in our method chain. \[code language="js"\] Rx.Observable.interval(1000) .filter(function(x) { return x % 2 == 0; }) .subscribe(function (x) { console.log(x); }); \[/code\] Next up we have schedulers. Schedulers let you choose how and whether your code is executed concurrently. There are lots of built in schedulers and it's possible to write your own, but for now we will concentrate on the TimeoutScheduler. [![timeout](https://jajeffries.files.wordpress.com/2015/01/timeout.gif)](https://jajeffries.files.wordpress.com/2015/01/timeout.gif) If we our running our code in the browser will execute our code asynchronously in a setTimeout. We can tell our subscription to use the TimeoutScheduler by adding a call to observeOn into our method chain before subscribe. \[code language="js"\] Rx.Observable.interval(1000) .filter(function(x) { return x % 2 == 0; }) .observeOn(Rx.Scheduler.timeout) .subscribe(function (x) { console.log(x); }); \[/code\] This will give us the same output, but our subscription won't be blocking the current thread. Hopefully now you have a basic understanding of the fundamental building blocks or Rx. The examples we used today were all in JavaScript, but they should translate pretty easily to other languages. We saw how we can:

*   create observable streams of data
*   perform operations on the streams of data
*   control the concurrency model used to run our operations

[Here](http://jsfiddle.net/dpq9t96a/) is a jsfiddle of the examples from this article in case you want to have a play around with some of the code. This brief overview should be enough for you to get started, but watch this space for more Rx examples and tutorials, both in JavaScript and other languages.