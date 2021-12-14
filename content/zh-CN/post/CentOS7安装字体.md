---
author: "liuqiang"
title: "Centos安装字体"
url: "2021/03/15/安装字体.html"
date: "2021-03-15T16:01:32+08:00"
toc: true
math: true
description: ""
categories: ["CentOS"]
tags: ["linux","centos7"]
---

### 事先安装
```shell
yum -y install fontconfig
yum -y install mkfontscale
```
### 查看已安装字体
```shell
fc-list
```
### 查看linux已安装中文字体
```shell
fc-list :lang=zh
```
### 安装字体
#### 1. 进入字体目录
```
cd /usr/share/fonts
```
#### 2. 新建目录 myfonts
```
mkdir myfonts
```
#### 3. 上传字体到myfonts,并进入目录
> window字体目录 C:\Windows\Fonts 
#### 4. 开始安装
```shell
# 更新字体库索引
mkfontscale
mkfontdir
# 更新字体缓存
fc-cache
```