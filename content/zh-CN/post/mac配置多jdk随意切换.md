---
author: "liuqiang"
title: "Mac配置多jdk随意切换"
url: "2021/06/20/jdk随意切换.html"
date: "2021-06-20T16:04:43+08:00"
toc: true
math: true
description: ""
categories: ["MAC"]
tags: ["mac","jdk"]
---

## 下载安装

jdk6：https://support.apple.com/kb/DL1572?locale=zh_CN

## 配置环境变量

open .bash_profile

export PATH=$PATH:/usr/local/apache-tomcat-7.0.79/bin
export JAVA_6_HOME=/Library/Java/JavaVirtualMachines/1.6.0.jdk/Contents/Home
export JAVA_7_HOME=/Library/Java/JavaVirtualMachines/jdk1.7.0_79.jdk/Contents/Home
export JAVA_8_HOME=/Library/Java/JavaVirtualMachines/jdk1.8.0_131.jdk/Contents/Home

 

## 设置默认的jdk版本

export JAVA_HOME=$JAVA_8_HOME 

 

## 设置alias 用于切换

alias jdk8='export JAVA_HOME=$JAVA_8_HOME'
alias jdk7='export JAVA_HOME=$JAVA_7_HOME'
alias jdk6='export JAVA_HOME=$JAVA_6_HOME'

保存退出

source .bash_profile

## 切换jdk

　　输入  jdk6，再输入java -version 查看当前版本即可实现动态切换，jdk7，jdk8同样。

 

 

 

 