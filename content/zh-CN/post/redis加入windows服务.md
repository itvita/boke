---
author: "liuqiang"
title: "Redis加入windows服务"
url: "2022/03/03/入windows服务.html"
date: "2022-03-14T16:21:57+08:00"
toc: true
math: true
description: ""
categories: ["redis"]
tags: ["redis"]
---


## 安装命令:
```shell
redis-server.exe --service-install redis.windows.conf --loglevel verbose 
```
## 卸载命令：
```shell
redis-server --service-uninstall  
```