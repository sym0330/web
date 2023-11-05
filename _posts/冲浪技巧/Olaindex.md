---
title: 用宝塔搭建 Olaindex6
date: 2021-05-31 21:43:03
categories: 冲浪技巧
tags: [经验分享, olaindex, 宝塔, onedrive]
description: 一款 OneDrive 目录文件索引应用，基于优雅的 PHP 框架 Laravel 搭建，并通过 Microsoft Graph 接口获取数据展示，支持多类型帐号登录，多种主题显示，简单而强大。
urlname: olaindex6
cover: /img/Olaindex/1.png
keywords: [经验分享, Olaindex, 宝塔, onedrive]
updated: 2022-05-20 12:21:00
---

# 环境要求

- PHP >= 7.4
- PHP OpenSSL 扩展
- PHP PDO 扩展
- PHP Mbstring 扩展
- PHP Tokenizer 扩展
- PHP XML 扩展
- PHP Ctype 扩展
- PHP JSON 扩展
- PHP BCMath 扩展
- PHP Fileinfo 扩展
  如果使用宝塔安装的 PHP 则只需要在 PHP 设置界面手动安装 **fileinfo**

# 宝塔内设置

## 取消函数禁用

在 PHP 设置界面选择 `禁用函数`
找到 `proc_open`，`proc_get_status`，`putenv` 并取消禁用

## 添加站点

网站页中添加站点，不需要数据库，只需要 PHP

## 选择 网站目录

关闭 `防跨站攻击(open_basedir)`

## 选择 伪静态

将伪静态改为 `laraval5`

## 选择 配置文件

删除下方代码

```
location ~ .*\.(gif|jpg|jpeg|png|bmp|swf)$
    {
        expires      30d;
        error_log /dev/null;
        access_log /dev/null;
    }

    location ~ .*\.(js|css)?$
    {
        expires      12h;
        error_log /dev/null;
        access_log /dev/null;
    }
```

# 安装

按行执行下列代码

```
cd web目录
git clone https://g.nite07.org/WangNingkai/OLAINDEX.git tmp
mv tmp/.git .
rm -rf tmp
git reset --hard
composer install -vvv
chmod -R 777 storage
chown -R www:www *
composer run install-app
```

安装完成后在宝塔中将 `网站目录` 设置为 `/www/wwwroot/XXX/public` (XXX 为站点目录)

# 配置 SSL

建议使用 Let's Encrypt 免费证书

# Olaindex 设置

访问 `https://example.com/admin`

默认账号为 `admin`

默认密码为 `123456`

# 绑定账号

1. **redirect_uri**填入http://example.com/callback
2. 点击申请
3. 登录 Microsoft 账号
4. 复制网页中给出的代码粘贴到**client_secret**中
5. 点申请页面的返回按钮，把返回页面链接中`&appID=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx&appName` 的 `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx` 复制到 **client_id**
6. 点击保存

# 修改默认密码

在控制台中 cd 到站点根目录

执行 `php artisan helper:reset-password`

**更多设置参考 https://olaindex.js.org/**
