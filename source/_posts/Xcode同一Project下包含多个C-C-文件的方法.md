---
title: Xcode同一Project下包含多个C/C++文件的方法
date: 2021-05-15 13:08:41
tags:
- Xcode
- C/C++
categories:
- Xcode
description:
"本来挺简单的事，新手却很难在网上找到答案，这里写一下我的做法"
---

### 背景

Xcode不能运行单个C/C++文件，想用Xcode写C/C++必须新建或打开现有工程(Project)，工程中包含C/C++文件。

但是一个C/C++文件放一个工程有点麻烦，于是想把多个C/C++文件都放到一个工程里。

[TODO]插入图片
