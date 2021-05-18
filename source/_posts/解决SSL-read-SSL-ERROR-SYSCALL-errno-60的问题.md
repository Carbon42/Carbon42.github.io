---
title: '解决SSL_read: SSL_ERROR_SYSCALL, errno 60的问题'
date: 2021-05-18 16:13:03
tags:
- git
categories:
- git
---

### 问题出现
往git 仓库上传文件时出现

>SSL_read: SSL_ERROR_SYSCALL, errno 60
<!--more-->
用`git clone url`拉取代码也出现了同样的错误

### 故障排查

既然出现了SSL(Secure Socket Layer)加密传输的信息,说明应该是网络问题。

然而，经过测试，连接GitHub没有问题。

上网冲浪，怀疑是代理的问题。

查看代理配置

>git config --global -l
>//如果代理在git中，则在这里会出现信息。如果没有任何配置则没问题。
>env|grep -i proxy
>//查看环境变量中有没有配置代理

一切正常

### 问题解决
误打误撞，使用
>git config --global -l

检查git信息时才想起来我最近改了GitHub用户名。于是，

>git config  --global user.name newusername
>//修改全局git用户名

即可，此后一切正常。

### 总结
没事不要改用户名、仓库名...