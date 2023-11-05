---
title: 宝塔搭建 Panindex
date: 2021-09-20 18:11:16
categories: [冲浪技巧]
tags: [冲浪技巧, Panindex]
urlname: panindex
cover: /img/Panindex/1.png
keywords: [冲浪技巧, Panindex]
updated: 2022-05-20 12:21:00
---

# 简介

[Github](https://g.nite07.org/libsgh/PanIndex)

- 简单的网盘目录列表
  - 跨平台、易部署
  - 多模式，多账户
  - 多主题
  - 下载直链
  - 防盗链
- 目前支持的网盘
  - 本地目录
  - 天翼云网盘
  - teambition 盘（个人、项目、国际服）
  - 阿里云盘
  - OneDrive 国际版

# 搭建教程

## 准备

- 宝塔面板
- 软件商店中的 **Docker 管理器**

## 开始搭建

1. 打开 **Docker 管理器**，点击 **镜像管理 -> 获取镜像 -> 官方库**
   ![](/img/Panindex/2.png)
2. 输入 `iicm/pan-index:latest` 后点击 **获取镜像**
3. 点击 **容器列表 -> 创建容器**
   ![](/img/Panindex/3.png)
4. **镜像** 选择 **iicm/pan-index:latest**
5. **端口映射** 随便填，官方给的是 **5238**
6. **目录映射 -> 容器目录** 填 `/app/data`
7. **目录映射 -> 服务器目录** 随意
8. **内存配额** 根据服务器配置决定
9. 其他保持默认
10. 点击 **提交**
    我的设置（仅供参考）
    ![](/img/Panindex/4.png)
11. 打开宝塔面板的 **网站** 设置页面，添加一个站点，**PHP** 选择 **纯静态** 就可以
12. 申请一个 SSL 证书
13. 添加 **反向代理**，名称随意、目标 URL 为 `服务器IP:端口`，其他不变
    ![](/img/Panindex/5.png)
14. 完成！现在可以访问 `https://你的域名/admin` 来设置 Panindex 了
