---
title: Windows11 非 Beta 通道安装安卓子系统(WSA)
date: 2021-10-25 12:23:50
categories: 冲浪技巧
tags: [实用教程, Windows11, 安卓子系统, wsa]
urlname: win11wsa
cover: /img/windows11安卓子系统/1.jpg
keywords: [实用教程, Windows11, 安卓子系统, wsa]
updated: 2022-05-20 12:21:00
---

# 安装 WSA

1. 打开 [Microsoft Store - Generation Project](https://store.rg-adguard.net/)
2. 在 URL 中输入 `https://www.microsoft.com/store/productId/9P3395VX91NR`
3. 选择框选择 **Slow**
4. 点击 **√**
5. 列表加载完成后下载最下方的文件(以 msixbundle 结尾)
6. 下载完成后双击运行安装(如果提示缺少依赖，可以到刚刚下载文件的网站里下载其他以 msixbundle 结尾的文件并安装)
7. 开启虚拟化支持（通常近年推出的新主板默认开启无需设置，不同主板开启方法不同自行百度）
8. 打开 **控制面板**，找到 **程序 - 启用或关闭 Windows 功能**
9.  开启 **Hyper-V** 和 **虚拟机平台**
10. 重启电脑
11. 到这里安卓子系统就安装完成了，但是还不能直接通过 APK 安装应用

# 安装 APK Installer (方便安装第三方 APK)

[微软应用商店](https://apps.microsoft.com/store/detail/9P2JFQ43FPPG)
