---
title: SwitchyOmega 使用教程 - 单独配置浏览器代理
date: 2021-09-03 11:20:16
categories: [冲浪技巧]
tags: [冲浪技巧, 网络代理, 浏览器]
urlname: switchyomegaguide
cover: /img/Switchyomega/1.jpg
keywords: [冲浪技巧, 网络代理, 浏览器]
updated: 2022-05-20 12:21:00
---

# 简介

SwitchyOmega 是浏览器专用的代理设置工具，可以轻松快捷地管理和切换多个代理设置，指定哪些网站使用代理哪些网站使用直连

# 安装 SwitchyOmega 扩展的浏览器

可以安装扩展的浏览器有 Microsoft Edge、Chrome、Firefox 等
如果你不会装浏览器扩展可以参考这篇文章的操作 [Tampermonkey（篡改猴） - 让网上冲浪体验飙升的浏览器插件 | Nite07 的小窝](/tampermonkey/)

![](/img/Switchyomega/2.png)

# 配置 SwitchyOmega （浏览器代理）

1. 打开浏览器
2. 点击 SwitchOmega 图标
3. 点击 **选项**
4. 点击左侧 **Proxy**
5. **代理协议** 为 **Socks5**
6. **代理服务器** 为 **127.0.0.1**
7. **代理端口** 在你使用的代理软件中查看（下图展示的是 Clash for Windows）
   ![](/img/Switchyomega/3.png)
   ![](/img/Switchyomega/4.png)
8. 点击左侧 **应用选项**
9. 点击左侧 **auto switch**
10. 找到 **规则列表设置**
11. **规则列表格式** 选择 **AutoProxy**
12. **规则列表网址** 填入 `https://g-raw.nite07.org/gfwlist/gfwlist/master/gfwlist.txt`
13. 点击 **立即更新情景模式** ，等待数据更新
14. **规则列表规则** 选择 **Proxy**
15. **默认情景模式** 选择 **直接连接**
16. 点击左侧 **应用选项**
17. 点击 **扩展图标 -> auto switch**

设置完成后，关掉代理软件的系统代理模式浏览器也能访问谷歌页面，如果不能则设置有误

# SwitchyOmega 手动设置网页代理模式

如果遇到 SwitchyOmega 不能正确识别是否需要代理的页面可以手动设置正在访问的页面的代理规则

**proxy** 为代理模式
**[直接连接]** 为直连模式

![](/img/Switchyomega/5.png)
