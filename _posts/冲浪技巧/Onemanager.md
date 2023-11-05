---
title: 用宝塔搭建 Onemanager
date: 2021-08-21 11:14:46
categories: 冲浪技巧
tags: [经验分享, onemanager, 宝塔, onedrive]
urlname: onemanager
description: 一个基于无服务器的 Onedrive、Aliyundrive、Googledrive 的索引和管理器。可以部署到 Heroku/Glitch/Vercel/SCF/FG/FC/CFC/PHP web hosting/VPS。
cover: /img/Onemanager/1.jpg
keywords: [经验分享, onemanager, 宝塔, onedrive]
updated: 2022-05-20 12:21:00
---

# Onemanager

[Github](https://g.nite07.org/qkqpttgf/OneManager-php)

一个基于无服务器的 Onedrive、Aliyundrive、Googledrive 的索引和管理器。可以部署到 Heroku/Glitch/Vercel/SCF/FG/FC/CFC/PHP web hosting/VPS。

# 部署

1. 在宝塔面板中添加站点，PHP 版本选择 **PHP-74**，无需数据库

2. 到 [Github](https://g.nite07.org/qkqpttgf/OneManager-php) 中下载源码，并把压缩包上传到站点根目录解压

3. 在宝塔面板中编辑根目录下的 **.htaccess** 可以查看伪静态的设置要求。找到 `###nginx` 下的内容，即 `rewrite ^/(?!.well-known)(.*)$ /index.php?/$1 last;`

4. 在宝塔网站设置中添加伪静态 `rewrite ^/(?!.well-known)(.*)$ /index.php?/$1 last;`

5. 访问刚创建的网站，点击开始安装程序
   ![](/img/Onemanager/2.png)
6. 之后的选项根据自己需要设置

7. 设置完成后跳转回站点根目录

   ![](/img/Onemanager/3.png)

8. 点击左上角 **登录**，输入安装过程中设置的密码

9. 登录成功后，点击左上角 **管理**

10. 在这里选择需要添加的网盘
    ![](/img/Onemanager/4.png)

11. 根据要求设置完成后 Onemanager 搭建完成

12. 在 **平台变量** 页面中可以设置 背景、样式、访问密码等
    ![](/img/Onemanager/5.png)

# 获取阿里云盘 refresh_token

1. 手机登录阿里云盘
2. 用文件管理器打开 `手机根目录\Androd\data\com.alicloud.databox\files\logs\trace`
3. 把 trace 文件夹下的文件（夹）都删了
4. 启动一次阿里云盘
5. 回到文件管理器，此时 trace 文件夹下会出现一个文件夹，进入它
6. 进入 yunpan 文件夹
7. 点开 log 文件
8. 找到 `"refreshToken":"xxxxxxxxxxxxx"`
