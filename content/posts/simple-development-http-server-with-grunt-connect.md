---
title: 'Simple development HTTP server with grunt connect'
date: Thu, 22 Jan 2015 19:49:11 +0000
draft: false
tags: []
---

I'm working on a phonegap project at the moment. I like phonegap because it lets me develop quickly and iterate fast, because I can test in the browser. To serve the files I've been using a [grunt](http://gruntjs.com/) task called [grunt-contrib-connect](https://github.com/gruntjs/grunt-contrib-connect). It's simple to setup. I just run this command to install it and add it to my package.json: \[code\] npm install grunt-contrib-connect --save-dev \[/code\] And then add the following config to my gruntfile.js: \[code language="js"\] module.exports = function(grunt) { // Project configuration. grunt.initConfig({ pkg: grunt.file.readJSON('package.json'), connect: { dev: { options: { port: 9001, keepalive: true, hostname: '0.0.0.0', base: 'build' } } }); grunt.loadNpmTasks('grunt-contrib-connect'); }; \[/code\] Now I can run my web server by running one simple command: \[code\] $ grunt connect:dev Running "connect:dev" (connect) task Waiting forever... Started connect web server on http://0.0.0.0:9001 \[/code\]