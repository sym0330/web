---
title: Tampermonkey(篡改猴) - 让网上冲浪体验飙升的浏览器插件
date: 2021-08-17 11:57:29
categories: 冲浪技巧
tags: [冲浪技巧, tampermonkey]
urlname: tampermonkey
cover: /img/Tampermonkey/1.jpg
keywords: [冲浪技巧, tampermonkey]
updated: 2022-05-20 12:21:00
---

# Tampermonkey（篡改猴）

Tampermonkey 是一款免费的浏览器扩展和最为流行的用户脚本管理器，它适用于 Chrome, Microsoft Edge, Safari, Opera Next, 和 Firefox。
虽然有些受支持的浏览器拥有原生的用户脚本支持，但 Tampermonkey 将在您的用户脚本管理方面提供更多的便利。 它提供了诸如便捷脚本安装、自动更新检查、标签中的脚本运行状况速览、内置的编辑器等众多功能， 同时 Tampermonkey 还有可能正常运行原本并不兼容的脚本。

# 支持的浏览器

- Chrome
- Microsoft Edge
- Safari
- Firefox
- Opera Next
- Dolphin Browser
- UC Browser

# 安装教程（以 Microsoft Edge 为例）

![](/img/Tampermonkey/2.jpg)

![](/img/Tampermonkey/3.jpg)

![](/img/Tampermonkey/4.png)

![](/img/Tampermonkey/5.jpg)

# 实用脚本

## [Userscript+](https://greasyfork.org/zh-CN/scripts/24508-userscript-show-site-all-userjs)

授人以鱼不如授人以渔，这个脚本可以显示适用于当前网站的 Tampermonkey 脚本，并且可以一键安装指定的脚本。

很多时候，我们并不知道一些网站是否有用户提供用来优化页面的脚本，而 **Userscript+** 就能帮你自动寻找适用的 UserJS，并默认按照评分高低排序推荐给你,给你带来一种全新的 Tampermonkey 使用体验！

![](/img/Tampermonkey/6.jpg)

## [AC-baidu-重定向优化百度搜狗谷歌必应搜索*favicon*双列](https://greasyfork.org/zh-CN/scripts/14178-ac-baidu-%E9%87%8D%E5%AE%9A%E5%90%91%E4%BC%98%E5%8C%96%E7%99%BE%E5%BA%A6%E6%90%9C%E7%8B%97%E8%B0%B7%E6%AD%8C%E5%BF%85%E5%BA%94%E6%90%9C%E7%B4%A2-favicon-%E5%8F%8C%E5%88%97)

名字有点长，主要功能有

- 去掉百度、搜狗、谷歌搜索结果的重定向，回归为网站的原始网址
- 去除搜索广告
- 添加百度、搜狗、谷歌搜索结果中 Favicon 显示效果
- 百度和谷歌搜索页面可以设置为单列、双列等模式
- 添加标记数量，标记当前的 id，界面更好看
- 搜索结果编号
- 下滑加载自动翻页
- 自定义样式
- 护眼模式
- 移除搜索预测
- 文字下划线

![](/img/Tampermonkey/7.jpg)

## [隐藏 youtube google 广告](https://greasyfork.org/zh-CN/scripts/38182-hide-youtube-google-ad)

隐藏 youtube 显示的 google 广告，自动点击 “skip ad”

# 其他脚本获取方法

## 脚本网站

直接在浏览器中`点击 Tampermonkey 图标 -> 获取新脚本`

官方提供了 4 种获取脚本的途径

- [Greasy Fork](https://greasyfork.org/zh-CN)
- [Userscript](https://www.userscript.zone/)
- [Github](https://gist.g.nite07.org/search?l=JavaScript&o=desc&q="%3D%3DUserScript%3D%3D"&s=updated)
- [OpenUserJS](https://openuserjs.org/)

按推荐度排序

## 源码

如果有了脚本的源码也可以添加脚本
直接在浏览器中`点击 Tampermonkey 图标 -> 添加新脚本`
把脚本源码复制到代码框中保存即可

# 管理已经安装的脚本

直接在浏览器中`点击 Tampermonkey 图标 -> 管理面板`
