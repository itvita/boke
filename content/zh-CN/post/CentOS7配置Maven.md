---
author: "liuqiang"
title: "CentOS7配置Maven"
url: "2021/10/03/centos配置maven.html"
date: "2021-10-03T15:58:50+08:00"
toc: true
math: true
description: ""
categories: ["CentOS"]
tags: ["maven","linux","centos7"]
---

### 下载
```
wget https://dlcdn.apache.org/maven/maven-3/3.8.2/binaries/apache-maven-3.8.2-bin.tar.gz
```

### 解压
```
tar -zxvf apache-maven-3.8.2-bin.tar.gz
```

### 配置环境变量

```
vim /etc/profile

export MAVEN_HOME=/opt/apache-maven-3.8.2
export PATH=$PATH:$MAVEN_HOME/bin
```

### 刷新配置
```
source /etc/profile
```