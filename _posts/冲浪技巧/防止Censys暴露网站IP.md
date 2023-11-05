---
title: 防止Censys暴露网站IP
date: 2022-01-18 14:24:51
categories: [冲浪技巧]
tags: [冲浪技巧, Censys]
urlname: denycensys
cover: /img/防止Censys暴露网站IP/1.jpg
keywords: [冲浪技巧, Censys]
updated: 2022-05-20 12:21:00
---

# 简介

Censys 是一款免费的搜索引擎，最初由密歇根大学的研究人员在 10 月发行，目前由谷歌提供支持。 Censys 搜索引擎能够扫描整个互联网，Censys 每天都会扫描 IPv4 地址空间，以搜索所有联网设备并收集相关的信息，并返回一份有关资源(如设备、网站和证书)配置和部署信息的总体报告。
Censys 导致即使网站使用了 CDN 仍然会被检测到源站 IP 地址

# 屏蔽方法

{% hideToggle "方法1: 使用空白证书" %}

```
-----BEGIN CERTIFICATE-----
MIIBkjCB/AIJAI3bCYqa39hiMA0GCSqGSIb3DQEBBQUAMA0xCzAJBgNVBAYTAiAg
MCAXDTE4MTEyNDA5MDMzOFoYDzIwOTkxMjMxMDkwMzM4WjANMQswCQYDVQQGEwIg
IDCBnzANBgkqhkiG9w0BAQEFAAOBjQAwgYkCgYEA18hepvNcznqDj735Opxircn3
M0Ruv8nkpHHPuurxr6tLPKAe1XAsy5dWHDbK7t4sXpT0ds9c74yqmvfwKofPk7z9
ZBhmyw/5sp454/JftL1c2fr58wB9ETfX6as5aR5hQR0M0NuQLSAB/KVzi9eeNWDd
EzT0QN5B1Ai9BR/ApMMCAwEAATANBgkqhkiG9w0BAQUFAAOBgQBiqHZsuVP09ubT
GzBSlAFEoqbM63sU51nwQpzkVObgGm9v9nnxS8Atid4be0THsz8nVjWcDym3Tydp
lznrhoSrHyqAAlK3/WSMwyuPnDCNM5g1RdsV40TjZXk9/md8xWxGJ6n1MoBdlK8T
H6h2ROkf59bb096TttB8lxXiT0uiDQ==
-----END CERTIFICATE-----
```

```
-----BEGIN RSA PRIVATE KEY-----
MIICXQIBAAKBgQDXyF6m81zOeoOPvfk6nGKtyfczRG6/yeSkcc+66vGvq0s8oB7V
cCzLl1YcNsru3ixelPR2z1zvjKqa9/Aqh8+TvP1kGGbLD/mynjnj8l+0vVzZ+vnz
AH0RN9fpqzlpHmFBHQzQ25AtIAH8pXOL1541YN0TNPRA3kHUCL0FH8CkwwIDAQAB
AoGAQ4ejh6AV5VCWJ8AOZXdXsofIYzUBa+glNAmiNx8b8BwteZWq0KVAf56nBkFn
lQXW4OrA7wXKUfW11rXNZaIHJePJXv1swkN9+Em18Hon6BrtcqnKAwzAbhok3SzY
IVjI/zrgOABH6+ii77xCRBzI1itVPNN88DAUHC7PYLYiaaECQQD7PSoij37+kMc/
wPeEkl9r3vzU0OrsCsjU8Ev714OaoL/SIuAh6nsiRh9rcbUrrpGSSzIcmsk9HMDa
hXBNkNl5AkEA298yQvssaUc4tbEWxAVfd9DsHJdCdbXfgf9Dy5/tpCzYncY7T0du
VVHqKu3jXWoMc5XlesiCOerU/DIlMM8dGwJBANQn7GLO5iC1xWvS2bF7oVSIMtzL
pvW4jaszWBbNAPccc59RkA9T4LMqn/GtTZ4bhhYRpbl+BB21IC3nrNPzU5ECQG8T
Ln0QDruQs2F2eR3F6RjKfr1i3LxCiQtPPZycypzp2vS5tDS0zVRk8XuGehoy/N9X
lnqU2NURgU92tbsWpokCQQDdc9tU3B/OM/YfzUNwvOLmUVwrJX6PFSFsOn+XHrCC
q9LcGEAHyzaf5GEWje84ee4rkv5oaZcwll3dg4IioBnC
-----END RSA PRIVATE KEY-----
```

修改 `nginx.conf` 的 `server` 块

```config
	server {
     listen 80 default_server;
     server_name _;
     allow all;
     deny 162.142.125.0/24; # Censys爬虫的IP段公布在其官网 https://support.censys.io/hc/en-us/articles/360043177092-Opt-Out-of-Scanning
     deny 167.94.138.0/24;
     deny 167.94.145.0/24;
     deny 167.94.146.0/24;
     deny 167.248.133.0/24;
     deny 2602:80d:1000:b0cc:e::/80;
     deny 2620:96:e000:b0cc:e::/80;
     if ($http_user_agent ~* (Censys)) {
         return 404;
     }
     location / {
         return 404;
     }
 }

	server {
     listen 443 ssl http2;
     server_name _ ;
     ssl_certificate     /path/to/emptyssl/crt;
     ssl_certificate_key /path/to/emptyssl/key;
     return 444;
 }
```

{% endhideToggle %}

{% hideToggle "方法2: 使用ssl_reject_handshake" %}

修改 `nginx.conf` 的 `server` 块

```config
	server {
     listen 80 default_server;
     server_name _;
     allow all;
     deny 162.142.125.0/24; # Censys爬虫的IP段公布在其官网 https://support.censys.io/hc/en-us/articles/360043177092-Opt-Out-of-Scanning
     deny 167.94.138.0/24;
     deny 167.94.145.0/24;
     deny 167.94.146.0/24;
     deny 167.248.133.0/24;
     deny 2602:80d:1000:b0cc:e::/80;
     deny 2620:96:e000:b0cc:e::/80;
     if ($http_user_agent ~* (Censys)) {
         return 404;
     }
     location / {
         return 404;
     }
 }

	server {
     listen 443 ssl http2;
     server_name _ ;
     ssl_reject_handshake on; # 关键, 启用拒绝 TLS 握手
     return 444;
 }

{% endhideToggle %}

修改 `robots.txt`

```

User-agent: Censys
Disabled: /

```

```
