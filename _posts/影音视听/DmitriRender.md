---
title: DmitriRender 5.0.0.1 去水印无限试用 - 视频智能补帧插件
date: 2021-08-25 18:29:21
categories:
  - [冲浪技巧]
  - [实用资源, Windows, 影音视听]
tags: [冲浪技巧, 补帧, potplayer, 插件]
urlname: dmitrirender
cover: /img/DmitriRender/1.jpg
keywords: [冲浪技巧, 补帧, potplayer, 插件]
updated: 2022-05-20 12:21:00
---

# DmitriRender 视频智能补帧插件

DmitriRender 简称 DR，是一款智能补帧软件，可以将视频帧数翻倍。具体可以参考截图，原视频帧数 23 左右，开启 DR 之后帧数为 120，观感提升显著。

# 截图

![](/img/DmitriRender/2.jpg)

# 使用说明

DR 需要配合 [Potplayer](../potplayer/) 一起使用。  
只支持 **64 位** 版本的 Potplayer，不支持老显卡和核显  
补帧的最大帧数是屏幕的刷新率

## 初次使用

1. 解压文件
2. 按 Win + R 打开运行，输入 `%appdata%` 回车
3. 将 **DmitriRender** 文件夹复制到打开的文件夹中
4. 进入 **DmitriRender** 文件夹，以管理员身份运行 **dmitriRender_registerFilter.bat**
5. 进入 **x64** 文件夹，运行 **pcnsl.exe**
6. 点击 **激活或转移产品 -> 下一步**
7. 将 **version.dll** 复制到 Potplayer 安装目录
8. 打开 Potplayer，按下 **F5** 打开选项
9. 点击 **滤镜 -> 全局滤镜优先权 -> 添加系统滤镜 -> DmitriRender -> 确定**
10. 点击列表中的 **DmitriRender** 选择右侧 **优先顺序 -> 强制使用 -> 确定**

## 无限试用

安装上面的设置完成之后可以试用 30 天，30 天之后需要重新激活。

1. 按 Win + R 打开运行，输入 `regedit` 回车
2. 找到 `HKEY_CURRENT_USER\Software\` 下的 **DmitriRender** 文件夹并删除
3. 打开系统 **Documents** 文件夹（默认路径是`C:\User\<用户名>\Documents`）
4. 点击 **选项**  
   ![](/img/DmitriRender/3.png)
5. 点击 **查看**，找到 **隐藏受保护的操作系统文件（推荐）** 并把勾去掉，找到 **显示隐藏的文件、文件夹和驱动器** 并选中
6. 打开 Documents 文件夹中的 **desktop.ini**
7. 删除形似下图所示的内容并保存  
   ![](/img/DmitriRender/4.png)
8. 按 Win + R 打开运行，输入 `%appdata%` 回车
9. 进入 **DmitriRender\x64** 文件夹，运行 **pcnsl.exe**
10. 点击 **激活或转移产品 -> 下一步**

# 下载

{% btn '/download/index.html?f=DmitriRender%205.0.0.1%20x64.zip',下载 %}
