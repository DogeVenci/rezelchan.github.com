---
layout: post
title: "putty login SSH by key"
date: 2014-01-03 14:15
comments: true
categories: [linux,ssh,security,putty]
---
<!--more-->
`sudo vi /etc/ssh/sshd_config`

- **Protocol 2**                  #使用SSH2
- **ServerKeyBits 768**           #加密强度
- **PermitRootLogin no**          #不允许用root进行登录
- **PermitEmptyPasswords no**     #禁止空密码进行登录
- **PasswordAuthentication no**   #不允许密码方式的登录

`sudo vi /etc/hosts.deny`

- **sshd: ALL**                   #添加这一行，屏蔽来自所有的SSH连接请求


`sudo vi /etc/hosts.allow`

- **sshd: xxx.xxx.xxx.**          #添加这一行，只允许来自内网的SSH连接请求


```
ssh-keygen -t rsa                  #生成密钥对
cd ~/.ssh 
cp id_rsa.pub authorized_keys
chmod 400 authorized_keys		   #复制和修改权限
```
复制 id_rsa 到 windows 的客户端上
打开 [PUTTYGEN.EXE](http://pan.baidu.com/s/1ntnubS9)- Conversions- import key- Save private key