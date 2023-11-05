---
title: V2rayN 及使用教程
date: 2021-09-03 10:55:46
categories:
  - [实用资源, Windows, 网络代理]
  - [开源应用]
tags: [中文, 冲浪技巧, 网络代理, v2rayn]
urlname: v2raynguide
cover: /img/V2rayN/1.jpg
keywords: [冲浪技巧, 网络代理, v2rayn]
updated: 2022-07-02 20:50:00
---

# 添加订阅

订阅是一个网页链接，打开后里面都是字母，一个订阅是多个节点的集合

![](/img/V2rayN/2.png)

1. 首先复制订阅链接
2. 点击 **订阅 -> 订阅设置**，添加订阅
3. 点击 **订阅 -> 更新订阅**，更新订阅

![](/img/V2rayN/3.png)

![](/img/V2rayN/4.png)

# 添加节点

单个节点链接是以 `vmess://`、`ss://`、`trojan://` 等格式开头的，例如：

```
vmess://ew0KICAidiI6ICIyIiwNCiAgInBzIjogIuaWsOWKoOWdoWYxLXRnQGZyZWVub2RlcyIsDQogICJhZGQiOiAiMTg4LjE2Ni4yNTAuMjQzIiwNCiAgInBvcnQiOiAiMTg5OTgiLA0KICAiaWQiOiAiNGRkN2ZhNDUtMzQxMC00ZWZmLWI1MmItNmFkZmIzOTdkNTg4IiwNCiAgImFpZCI6ICIxIiwNCiAgInNjeSI6ICJhdXRvIiwNCiAgIm5ldCI6ICJ3cyIsDQogICJ0eXBlIjogIm5vbmUiLA0KICAiaG9zdCI6ICJodHRwOi8vZWMyLTU0LTIyMy0xMjAtMTYxLmNuLW5vcnRoLTEuY29tcHV0ZS5hbWF6b25hd3MuY29tLmNuLGY5MzJjM2Q5ODk4MWIuZG93bmxvYWQubWljcm9zb2Z0LmNvbSIsDQogICJwYXRoIjogIi9wYXRoIiwNCiAgInRscyI6ICJub25lIiwNCiAgInNuaSI6ICIiDQp9
```

1. 复制单个或多个节点链接
2. 点击 **服务器 -> 从剪辑版导入批量 URL**

# 判断节点是否可用

1. 点击节点列表，按下 **Ctrl + A** 全选
2. 右键列表点击 **测试服务器延迟 Ping（多选）**
3. 等待检测，看 **测试结果** 一栏，哪一个有具体延迟（xxms）哪个节点就可用

# 使用节点

列表选中任意节点右击 **设为活动服务器** 或者 选中节点后按下回车键

# 开启系统代理

右键右下角托盘图标，点击 **系统代理 -> 自动配置系统代理**

开启系统代理有时候会导致部分使用国内网络的软件加载缓慢，个人建议给每个需要代理的软件单独设置 Socks 代理，例如：浏览器使用 [SwitchyOmega](..\switchyomegaguide\)、支持代理的软件在设置中设置、不支持代理的软件使用 [Proxifier](..\proxifier\) 之类的软件

# 下载

{% btn 'https://g.nite07.org/2dust/v2rayN/releases/latest',下载 %}
