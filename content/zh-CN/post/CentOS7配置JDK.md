---
author: "liuqiang"
title: "CentOS7配置JDK"
url: "2021/10/03/centos配置jdk.html"
date: "2021-10-03T15:58:15+08:00"
toc: true
math: true
description: ""
categories: ["CentOS"]
tags: ["jdk","linux","centos7"]
---

#### 下载

http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html

#### 解压

```
tar -zxvf  jdk-8u271-linux-x64.tar.gz.tar.gz
```

#### 配置环境变量

```
#vim /etc/profile -- 所有用户生效
#vim ~/.bash_profile --当前用户生效
JAVA_HOME=/opt/jdk1.8.0_271 
JRE_HOME=/opt/jdk1.8.0_271/jre 
CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar:$JRE_HOME/lib 
PATH=$JAVA_HOME/bin:$PATH 
export PATH JAVA_HOME CLASSPATH
```

#### 刷新

```
source  /etc/profile
```

