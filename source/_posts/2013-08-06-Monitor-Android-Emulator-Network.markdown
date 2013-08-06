---
layout: post
title: "Monitor Android Emulator Network"
date: 2013-08-06 14:53
comments: true
categories: [Android,network]
---
<!--more-->
```
adb shell
su
mount
mount –o remount /dev/block/mtdblock0 /system
mount
adb push tcpdump /system/xbin/
chmod 777 /system/xbin/tcpdump
adb shell tcpdump -p -vv -s 0 -w /sdcard/cap.pcap
adb install xxx.apk
adb pull /sdcard/cap.pcap cap.pcap
```
Easy way:Install shark for root  
Copy .pcap and open it in WireShark