---
author: "liuqiang"
title: "亚马逊awsVpn配置"
url: "2021/01/01/vpn配置.html"
date: "2021-01-14T16:12:06+08:00"
toc: true
math: true
description: ""
categories: ["其他"]
tags: ["vpn"]
---

# 注册亚马逊aws账号购买海外服务器
> 注册地址：https://aws.amazon.com/cn/ec2/?nc2=h_ql_prod_fs_ec2&ec2-whats-new.sort-by=item.additionalFields.postDateTime&ec2-whats-new.sort-order=desc
> 提前准备：身份证号，信用卡（需要短期冻结1刀）
> 注册成功安装EC2 > Ubuntu18系统 > 生成密钥(vpn.pem)并下载

# 使用脚本自动安装vpn
>https://github.com/itvita/setup-ipsec-vpn/blob/master/README-zh.md
>开放端口

```
进入安全组放开TCP 4500 & 500 端口
进入安全组放开UDP 4500 & 500 端口
```
> 打开电脑终端连接主机

```
chmod 400 vpn.pem // 修改文件权限,vpn.pem是刚刚下载的密钥文件名
ssh -i 'vpn.pem' ubuntu@公有DNS // 连接主机，进入主机操作
```
> 使用IPSec协议搭建L2TP VPN

```
wget https://git.io/vpnsetup -O vpnsetup.sh //下载vpnsetup.sh文件到当前目录
nano -w vpnsetup.sh // 编辑vpnsetup.sh内容
```

> 设置YOUR_IPSEC_PSK，YOUR_USERNAME，YOUR_PASSWORD

```
YOUR_IPSEC_PSK='itvita.cn'
YOUR_USERNAME='itvita'
YOUR_PASSWORD='YOUR_PASSWORD'
```

> 执行脚本

```
sudo sh vpnsetup.sh // 运行vpnsetup.sh脚本
 
sudo vim ipsec.scerets // 编辑ipsec.secrets
// 修改为：私有IP   %any   :PSK    "YOUR_IPSEC_PSK"
```