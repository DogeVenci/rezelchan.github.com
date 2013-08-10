---
layout: post
title: "nmap usage"
date: 2013-08-09 15:46
comments: true
categories: [network,linux,hacker]
---
<!--more-->
```
#ping 
nmap　-sP　192.168.7.0/24
nmap　-sP　-PT80　192.168.7.0/24

#port
nmap　-sT　192.168.7.12
#SYN 
nmap　-sS　192.168.7.7 
#UDP
nmap　-sU　192.168.7.7

#os
nmap　-sS　-O　192.168.7.12

#-v more info
nmap　-sS　-p　21,23,53,80　-O　-v　www.yourserver.com

-P0
```