---
title: ContextMenuManager - Windows 右键菜单管理程序
tags: [中文, 实用资源, Windows, ContextMenuManager]
cover: /img/ContextMenuManager/1.jpg
date: 2023-05-08 16:35:04
updated: 2023-05-08 16:35:04
categories:
  - [实用资源, Windows, 系统工具]
  - [冲浪技巧]
  - [开源应用]
urlname: contextmenumanager
keywords: [实用资源, 破解, 去广告, 纯净, 绿色, 白嫖, 免费, Windows, ContextMenuManager]
---

# 简介

一款 Windows 右键菜单管理程序

这个软件有几个比较好用的点，给大家介绍一下。

1. 可以根据右键点击对象的不同类型管理菜单。比如右键点击文件夹的时候显示哪些内容，点击 exe 文件的时候显示哪些内容，设置起来非常简单明了。
2. 可以根据程序自带的网络字典设置额外的菜单项，图二以 Bandizip 的右键菜单为例，可以增加以管理员方式解压、解压完后自动删除原文件等菜单项。
3. 可以自动感知并分析对象的菜单类型。这个功能主要用在当你不知道你想要修改的对象属于哪种菜单类型。图三以感知文件夹类型为例，程序自动判断了与文件夹相关的菜单类型。
4. 可以添加一些非常实用的菜单项，比如在桌面背景菜单中添加重启资源管理器的菜单项，在回收站的菜单中添加清除缩略图的菜单项，在 exe 文件菜单中添加管理防火墙规则的菜单项（在限制破解程序联网时就很常用到这个功能）等等，更多增强菜单项可以看图四到九。

附带：

- Windows11 恢复旧版右键菜单的方法
  `reg add "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32" /f /ve`
- 恢复 Windows11 右键菜单的方法
  `reg delete "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}" /f`
  执行完后都需要重启资源管理器

# 截图

| ![](/img/ContextMenuManager/2.jpg) | ![](/img/ContextMenuManager/3.jpg) | ![](/img/ContextMenuManager/4.jpg) |
| :--------------------------------: | :--------------------------------: | :--------------------------------: |
| ![](/img/ContextMenuManager/5.jpg) | ![](/img/ContextMenuManager/6.jpg) | ![](/img/ContextMenuManager/7.jpg) |
| ![](/img/ContextMenuManager/8.jpg) | ![](/img/ContextMenuManager/9.jpg) |                                    |

# 下载

{% btn 'https://g.nite07.org/BluePointLilac/ContextMenuManager/releases/latest',Github下载 %}
