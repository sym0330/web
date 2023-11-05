---
title: 搭建个人密码库(Vaultwarden)
date: 2021-04-06
categories: 冲浪技巧
tags: [个人, 密码, 搭建, 经验分享, bitwardenrs, vaultwarden]
description: 借助宝塔面板搭建 vaultwarden 密码库，实现密码多平台同步保存，再也不用记那么多密码了!
urlname: vaultwarden
cover: /img/Vaultwarden/1.png
keywords: [密码库, vaultwarden, 宝塔, 搭建, bitwardenrs]
updated: 2022-05-20 12:21:00
---

# 简介

[Github](https://g.nite07.org/dani-garcia/vaultwarden)

Vaultwarden，原名 Bitwardenrs，是 Bitwarden 的第三方开源修改版

# 准备

- 云服务器
- 宝塔面板
- 域名

# 部署

## 在宝塔面板安装 docker 管理器

![](/img/Vaultwarden/2.png)

## 获取 vaultwarden docker 镜像

在宝塔面板中打开 **docker 管理器 - 镜像管理 - 获取镜像 - 官方库**  
输入镜像名称 `vaultwarden/server:latest` 后获取镜像

## 创建 docker 容器

![](/img/Vaultwarden/3.png)

具体参数参考上图，其中 **8000** 对应本地页面端口号，可以自己修改，**80 和 /data 是固定值，不能修改**
**/xxx/xxx** 自己设置为保存数据的路径  
环境变量添加一个 `ADMIN_TOKEN=内容自定` （[其他环境变量参考](https://rs.bitwarden.in/configuration)）  
提交之后自动创建容器

## 解析域名到服务器

例如：passwd.example.com  
这个大家应该都知道怎么解析

## 创建网站

在宝塔面板中点击左侧 **网站 - 添加站点**  
**域名** 设置为第四步解析的域名 例如：passwd.example.com  
**PHP 版本** 选择 **纯静态**

## 设置 SSL

域名解析生效后在宝塔面板中点击对应站点后的 **设置 - SSL - Let's Encrypt** 申请一个证书

## 设置反向代理

接着上一步 点击左侧 **反向代理 - 添加反向代理**  
**代理名称** 随意  
**URL** 设置为 `http://127.0.0.1:端口` 其中端口对应第三步中设置的第二个端口，上例中是 8000  
其他保持默认，提交

## Vaultwarden 设置页面

访问 https://passwd.example.com/admin  
输入之前设置的环境变量 `ADMIN_TOKEN` 的值

## 开始使用

Vaultwarden 的客户端也是 Bitwarden  
[Bitwarden 客户端下载](https://bitwarden.com/download/)
