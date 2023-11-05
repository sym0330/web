---
title: Mirai机器人框架使用方法
date: 2021-07-27 10:25:08
categories: [冲浪技巧]
tags: [冲浪技巧, qq机器人, mirai]
urlname: miraiqqbot
cover: /img/Mirai机器人框架使用方法/1.png
keywords: [冲浪技巧, qq机器人, mirai]
updated: 2022-05-20 12:21:00
---

# Mirai

mirai 是一个在全平台下运行，提供 QQ Android 协议支持的高效率机器人库

[Github](https://g.nite07.org/mamoe/mirai)

# 运行环境

Java 运行时（版本必须 >= 11）

# 使用方法

1. 下载 `mirai-console-loader` 下文简称 `mcl`
   [Github](https://g.nite07.org/iTXTech/mirai-console-loader)
2. 解压 `mcl`
   ![](/img/Mirai机器人框架使用方法/2.png)
3. 运行 `mcl.cmd` 也可以手动通过 cmd 运行 `mcl.jar`
4. 当输出 `mirai-console started successfully.` 时 mirai 就启动完成了，可以输入 `help` 查看全部指令
   ![](/img/Mirai机器人框架使用方法/3.png)
5. 接下来登录 QQ 号，在 cmd 中输入 `login <QQ号> <QQ密码>` 回车
6. 首次登录需要进行账户安全认证
   ![](/img/Mirai机器人框架使用方法/4.jpg)
7. 将弹出的链接发送给手机 QQ 打开，会得到一个二维码，使用手机 QQ 扫码验证
8. 验证完成后关闭弹窗，等待登录，当输出下图内容就登录完成了
   ![](/img/Mirai机器人框架使用方法/5.png)
9. 至此 mirai 框架基础配置结束，但现在的机器人并没有实际功能

# 插件使用

> 本文以 tulingbot 插件为例，插件的安装都大同小异，具体方法以插件文档为准

[Github](https://g.nite07.org/Nambers/Mirai-TuLingBot)

1. 下载插件
2. 将插件解压到 `mcl目录\plugins` 文件夹下
3. 运行 mcl 后关闭
4. 打开 `mcl目录\data\TuLingBot\config.json` 设置图灵 API 信息
5. 再次运行 mcl 并登录使用
6. 至此 tulingbot 插件安装完成，可以和机器人进行对话测试
   ![](/img/Mirai机器人框架使用方法/6.png)
