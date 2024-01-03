---
title: 'A Ruby Oddity'
date: Tue, 01 Apr 2014 19:34:32 +0000
draft: false
tags: []
---

I discovered some odd behaviour in Ruby the other day. If I have the following code declaring some variables

> irb(main):002:0> a=1, irb(main):003:0\* b=1 => \[1, 1\]

This doesn't result in 'a' having the value 1. Instead it is an array. This initially struck me as odd, until I started thinking about it as packing or unpacking tuples as you might do to return multiple values in a functional language, such as [Haskell](https://xkcd.com/1312/). For example, if we wanted to square a number and return both the square and the original number (why we'd want to do this I don't know), we could write

> let square x = (x, x \* x) in square 10
> 
> \=>(10,100)

The first part of our tuple is the original value and the second part is the origianl value squared. So how would this look in Ruby? I'd probably write something like this.

> irb(main):013:0> def square(x) irb(main):014:1> \[x, x \*x\] irb(main):015:1> end

Our braces to initalise the array seem a bit redundant here. Maybe we could rewrite it without them.

> irb(main):016:0> def square(x) irb(main):017:1> x, x \*x irb(main):018:1> end SyntaxError: (irb):17: syntax error, unexpected '\*', expecting '=' x, x \*x ^ from /usr/bin/irb:12:in \`<main>'

Hmmm. Looks like this doesn't work quite the way I expected. We need a return statement in there too.

> irb(main):025:0> def square(x) irb(main):026:1> return x, x\*x irb(main):027:1> end

I'm not sure which I prefer, [or if this is even a good idea at all](http://xaviershay.github.io/writing/docs/ruby_style_guide.html). But how does this relate to our original problem? Well as we just saw in our square function we don't need the brackets to intialise an array so our original code could be rewritten as

> irb(main):005:0> \[a=1,b=1\] => \[1, 1\] irb(main):006:0> a => 1 irb(main):007:0> b => 1

Like in most functional languages Ruby is expression based so every statement evaluates to a value, even assignments. This means that our original code is actually the same as either

> irb(main):028:0> a=1 => 1 irb(main):029:0> b=1 => 1 irb(main):030:0> \[a,b\] => \[1, 1\]

Or even

> irb(main):031:0> a,b=\[1,2\] => \[1, 2\] irb(main):032:0> a => 1 irb(main):033:0> b => 2

Our last example strikes me as much more readable than the others, but as someone who regularly switches between node.js and Ruby I will certainly have to watch out for trailing comma's in my variable declarations.