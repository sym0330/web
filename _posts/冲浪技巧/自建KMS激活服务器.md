---
title: 自建KMS激活服务器
date: 2021-07-29 13:03:16
categories: [冲浪技巧]
tags: [冲浪技巧, windows, office, kms激活]
urlname: deploykms
cover: /img/自建KMS激活服务器/1.png
keywords: [冲浪技巧, windows, office, kms激活]
updated: 2022-05-20 12:21:00
---

# py-kms

py-kms 是 cyrozap 创建的 node-kms 的一个移植，它是 KMS 模拟器的 C#、C++ 或 .NET 实现的一个移植。原始版本是由 CODYQX4 编写的，源自微软官方 KMS 的反向工程代码。

[Github](https://g.nite07.org/Py-KMS-Organization/py-kms)

# 搭建

`docker run -d --name py-kms --restart always -p 1688:1688 ghcr.io/py-kms-organization/py-kms`

# 支持的软件

- Windows Vista
- Windows 7
- Windows 8
- Windows 8.1
- Windows 10 ( 1511 / 1607 / 1703 / 1709 / 1803 / 1809 )
- Windows 10 ( 1903 / 1909 / 20H1, 20H2, 21H1, 21H2 )
- Windows 11 ( 21H2 )
- Windows Server 2008
- Windows Server 2008 R2
- Windows Server 2012
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server 2019
- Windows Server 2022
- Microsoft Office 2010 ( Volume License )
- Microsoft Office 2013 ( Volume License )
- Microsoft Office 2016 ( Volume License )
- Microsoft Office 2019 ( Volume License )
- Microsoft Office 2021 ( Volume License )

# Windows 激活方式

1. 按下 `Win + R` 打开运行 输入 `cmd` 后按 `ctrl + shift + Enter` （以管理员方式运行 CMD）
2. 输入 `slmgr.vbs /upk` 卸载密钥
3. 输入 `slmgr /ipk 密钥` 安装密钥 （具体密钥查看下方链接）
4. 输入 `slmgr /skms <kms服务器域名或IP>` 设置激活服务器
5. 输入 `slmgr /ato` 激活 Windows

# Office 激活方式

1. 找到 Office 安装目录 （例如 `C:\Program Files (x86)\Microsoft Office\Office16`）
2. 按下 `Win + R` 打开运行 输入 `cmd` 后按 `ctrl + shift + Enter` （以管理员方式运行 CMD）
3. 输入 `cd <Office安装目录> ` （例如 `cd C:\Program Files (x86)\Microsoft Office\Office16`）
4. 输入 `cscript ospp.vbs /dstatus` 查看已设置的密钥后五位 （即 `Last 5 characters of installed product key: XXXXX`）记下 `XXXXX`。如果这一步出现多个密钥，多次重复下一步卸载
5. 输入 `cscript ospp.vbs /unpkey:XXXXX` 卸载密钥（`XXXXX`为第四步中记下的密钥后五位）
6. 输入 `cscript ospp.vbs /inpkey:密钥` 设置密钥 （具体密钥到下面列表查找）
7. 输入 `cscript ospp.vbs /sethst:<kms服务器域名或IP>` 设置 KMS 服务器
8. 输入 `cscript ospp.vbs /act` 激活 Office

# 序列号

https://py-kms.readthedocs.io/en/latest/Keys.html
