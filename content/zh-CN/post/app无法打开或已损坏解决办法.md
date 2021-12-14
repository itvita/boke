---
author: "liuqiang"
title: "App无法打开或已损坏解决办法"
url: "2021/03/03/开或已损坏解决办法.html"
date: "2021-03-03T15:50:46+08:00"
math: true
description: ""
categories: ["MAC"]
tags: ["mac"]
---

1、系统偏好设置... -> 安全性与隐私-->修改为任何来源

2、如果没有任何来源  ,打开终端执行:sudo spctl --master-disable

如果还不行 

sudo xattr -d com.apple.quarantine /Applications/Navicat\ for\ SQL\ Server.app


/Applications/Navicat\ for\ SQL\ Server.app 为app路径  

如果有空格，空格前加 \