---
author: "liuqiang"
title: "Kettle-数据库存储"
url: "2021/12/12/kettle-data-repo.html"
date: "2021-12-23T10:12:54+08:00"
toc: false
math: true
description: ""
categories: ["kettle"]
tags: ["kettle"]
---

kettle支持数据库存储和文件存储，默认是文件存储

当有很多个作业的时候，文件不好管理，需要使用数据库存储

### 配置数据库存储

打开Spoon右上角Connetc->Other Repositories >Database Repository>Get Start >create new connect