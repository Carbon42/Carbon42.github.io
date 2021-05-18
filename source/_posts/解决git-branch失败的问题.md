---
title: 解决git branch失败的问题
date: 2021-05-15 12:13:49
tags:
- 疑难杂症
- git 使用
categories:
- git 使用
---

### 问题出现

在git仓库本地文件夹下

>% git branch

出现
>fatal: not a git repository (or any of the parent directories): .git
<!--more-->
并没有预期的现实当前repository下的branch情况

### 尝试解决

上网冲浪后发现应该初始化，于是

>git init

出现
>Initialized empty Git repository in /Users/username/Documents/source/.git/

再
>git branch

好家伙，这回什么都没有了

### 最终解决

>git add .
>git commit
>git branch

这回正常了

### 原理
首先初始化没有错
>git init

但是git的branch只有在commit之后才会生效...

