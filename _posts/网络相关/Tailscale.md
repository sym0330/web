---
title: Tailscale - 内网穿透的替代方案
date: 2021-08-06 21:11:21
categories:
  - [冲浪技巧]
  - [实用资源, Windows, 网络相关]
tags: [英文, 冲浪技巧, 实用资源, tailscale]
urlname: tailscale
cover: /img/Tailscale/1.png
keywords: [冲浪技巧, 实用资源, tailscale]
updated: 2022-05-20 12:21:00
---

# 简介

零配置网络代理。在几分钟内安装在任何设备上，为你管理防火墙规则，并在任何地方工作。
在你的服务器、计算机和云实例之间创建一个安全的网络。即使被防火墙或子网分开，Tailscale 也能正常工作。
设备只有在通过你现有的身份提供者签入后才能连接。轻松地执行多因素认证，取消对已离职员工的授权，以及更多。

上面是官网抄的，简单来说就是把你所有安装 Tailscale 的设备拉入一个局域网，即使不在同一个网络下也可以相互访问。

# 用法示例

## FTP 服务器（顺便测试速度，测试过程不是很严谨）

使用 FileZilla 搭建的 Ftp 服务器，运行在我的 PC 上，分别用 Frp、局域网、Tailsacle 测试文件传输速度
直接上三种不同情况的图片

1. Frp
   使用的内网穿透服务器是阿里云的学生机带宽 1m，实际测试也是速度感人，只有 **100+ KiB/s**

   ![](/img/Tailscale/2.png)

2. 局域网
   我的 PC 是连的网线，用于下载文件的笔记本是 Wifi 接入局域网，速度大概 **14,15 MiB/s**
   ![](/img/Tailscale/3.png)

3. Tailscale
   速度有 **2.x MiB/s**

   ![](/img/Tailscale/4.png)

## Windows 文件共享

电脑共享文件夹，手机访问。
手机端可以用 [CX 文件管理器](../cxfileexplorer/) 1. 点击 **网络** 2. 添加 **SMB**

![](/img/Tailscale/5.jpg)

## Windows 远程桌面

软件打开直接通过 Tailscale 给的 IP 连接

## Minecraft 联机

实测如果是开单人游戏之后启动局域网联机是连不上的，但是可以在一台电脑上开服务器，这样就可以联机。

# 截图

![](/img/Tailscale/6.jpg)

# 下载

[官网下载](https://tailscale.com/download)
