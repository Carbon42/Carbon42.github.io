---
title: 解决hexo deploy上传失败的问题
date: 2021-05-13 21:10:29
tags:
- 网站建设
- 疑难杂症
- hexo
- git
categories:
- 网站建设
---

## 问题出现

今天用hexo d命令后命令行报错。
>fatal: unable to access 'https://github.com/username/username.github.io.git/': LibreSSL SSL_read: SSL_ERROR_SYSCALL, errno 60<!--more-->
FATAL {
  err: Error: Spawn failed
      at ChildProcess.<anonymous> (/Users/username/Documents/hexo/node_modules/hexo-util/lib/spawn.js:51:21)
      at ChildProcess.emit (events.js:315:20)
      at Process.ChildProcess._handle.onexit (internal/child_process.js:277:12) {
    code: 128
  }
} Something's wrong. Maybe you can find the solution here: %s https://hexo.io/docs/troubleshooting.html

## 问题解决

一开始以为是网络问题，遂魔法上网，换了几种姿势，未果。

尝试连接GitHub。
>ssh -T git@github.com

结果通了。
>You've successfully authenticated, but GitHub does not provide shell access.

看来真是疑难杂症。

上网冲浪后经高人指点应该通过env命令修改GIT_SSL_NO_VERIFY环境变量为”ture”。
>env GIT_SSL_NO_VERIFY=true

## [TODO] 原理

本来有篇帖子讲了这个问题的原理，遗憾的是那个链接已经挂掉了。于是继续上网冲浪，发现了点头绪。

However，最近考试多作业多，暂时没时间研究了，让子弹再飞一会。

