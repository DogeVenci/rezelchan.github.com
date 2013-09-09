---
layout: post
title: "Git think file save with Unicode are binary"
date: 2013-09-09 11:15
comments: true
categories: 
---
Create a `.gitattributes` file with the contents
```
*.cpp diff
```
<!--more-->
The [Pro Git book](http://git-scm.com/book) has a [chapter on Git Attributes](http://git-scm.com/book/ch7-2.html), and there's the [man page](http://www.git-scm.com/docs/gitattributes.html) of course.