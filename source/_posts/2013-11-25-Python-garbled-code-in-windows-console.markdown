---
layout: post
title: "Python garbled code in windows console"
date: 2013-11-25 16:19
comments: true
categories: [python] 
---
```
CHCP [nnn]
chcp 65001    #utf-8
chcp 936      #gbk
chcp 437      #us_eng
```
在命令行标题栏上点击右键，选择"**属性**"->"**字体**"，将字体修改为**True Type**字体"**Lucida Console**"，然后点击确定将属性应用到当前窗口。
<!--more-->