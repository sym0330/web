---
title: Parsec - 远程控制和游戏神器
tags: [英文, 实用资源, Windows, Parsec]
cover: /img/Parsec/1.jpg
date: 2022-06-05 18:09:26
updated: 2022-06-05 18:09:26
categories: [实用资源, Windows, 社交娱乐]
urlname: parsec
keywords: [实用资源, 破解, 去广告, 纯净, 绿色, 白嫖, 免费, Windows, Parsec]
---

# 简介

Parsec 是我最近发现的一个远程控制神器。
官方主打的功能是远程玩游戏，其他用户可以远程连接到你的电脑和你一起玩只能本地联机的游戏。
软件使用 P2P 直连，所以延迟很低。
当然也可以不用来玩游戏，只作为一款远程控制软件，我觉得也能甩其他远控软件几条街。

# 解决错误 800

> 需要代理

最近 Parsec 的网站被墙了，导致很多人打开软件会报错，登不上账户。
下面是比较完美的解决方案。
打开 Parsec 的配置文件 `%appdata%/Parsec/config.txt`
在结尾添加

```
app_proxy_address = 127.0.0.1
app_proxy_scheme = http
app_proxy = true
app_proxy_port = <你的http代理端口>
```

# 截图

![](/img/Parsec/2.jpg)

# 下载

> 可能被墙了

[官网下载](https://parsec.app/)
