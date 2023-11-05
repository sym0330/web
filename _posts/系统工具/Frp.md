---
title: frp内网穿透配置教程(以MC服务器为例)
date: 2021-07-26 17:17:39
categories: [冲浪技巧]
tags: [冲浪技巧, minecraft, 服务器, frp, 内网穿透]
urlname: frp
cover: /img/Frp/1.png
keywords: [冲浪技巧, minecraft, 服务器, frp, 内网穿透]
updated: 2022-05-20 12:21:00
---

## Frp

frp 是一个专注于内网穿透的高性能的反向代理应用，支持 TCP、UDP、HTTP、HTTPS 等多种协议。可以将内网服务以安全、便捷的方式通过具有公网 IP 节点的中转暴露到公网。

## Github

[Github](https://g.nite07.org/fatedier/frp)

## 部署结构

> 本文以 Minecraft 服务器为例，搭建 Minecraft 服务器的过程很简单，下文中省略。

1. Minecraft 服务器部署在我自己的电脑上（Windows）

2. Frp 服务端部署在 CentOS 服务器上

3. Frp 客户端则和 Minecraft 服务器一样运行在我的电脑上

## 使用方法

### 服务端

1. 下载对应版本的 Frp

2. 将 Frp 上传到有公网 IP 的服务器并解压

3. 编辑 `frps.ini` 文件，其中 `bind_port` 是 Frp 服务运行的端口

   ```ini
   [common]
   bind_port = 7000
   ```

4. 输入 `frps路径 -c frps.ini路径`（例如：`.\frps -c .\fprs.ini`）运行 frps

### 客户端

1. 下载对应版本的 Frp 并解压

2. 编辑 `frpc.ini`

   ```ini
   [common]
   server_addr = XXX.XXX.XXX.XXX
   server_port = 7000

   [Minecraft]
   type = tcp
   local_ip = 127.0.0.1
   local_port = 25565
   remote_port = 25565
   ```

   `server_addr` 为 服务端 IP

   `server_port` 为 服务端端口 即上文中的 `7000`

   `type` 为 代理类型

   `local_ip` 为 要进行内网穿透的内网服务器地址

   `local_port` 为 要进行内网穿透的内网服务器的应用端口

   `remote_port` 为 服务端监听的端口
   其他参数请查阅 [文档 | frp (gofrp.org)](https://gofrp.org/docs/)

3. 打开 `cmd` 输入 `frpc路径 -c frpc.ini路径` （例如：`frpc.exe -c frpc.ini`）运行 Frpc

4. 访问 Minecraft 服务器，IP 为 `server_addr:remote_port` 本文中即 `XXX.XXX.XXX.XXX:25565`

## 下载

{% btn 'https://g.nite07.org/fatedier/frp/releases/latest',下载 %}
