---
title: Python 防止 Selenium 被检测
date: 2021-08-06 13:40:29
categories: 笔记
tags: [Python, selenium, 反反爬虫, stealth]
urlname: pythonstealth
cover: /img/Python爬虫防止selenium被检测/1.png
keywords: [Python, selenium, 反反爬虫, stealth]
updated: 2022-05-20 12:21:00
---

# 简介

最近在写自动登录 QQ 音乐刷新 Cookie 的工具，发现就算破解了滑块还是不能成功登录，可能是 QQ 音乐检测到了 Selenium。
这个方法是在网上看到的，记录一下。
是使用 `stealth.min.js` 来反反爬虫

# Python 代码

```python
option = webdriver.ChromeOptions()
option.add_experimental_option('excludeSwitches', ['enable-automation'])
option.add_experimental_option('useAutomationExtension', False)
driver = webdriver.Chrome(options=option)
driver.execute_cdp_cmd("Page.addScriptToEvaluateOnNewDocument", {
    "source": """
    Object.defineProperty(navigator, 'webdriver', {
    get: () => undefined
    })
    """
})
# 2,3和5~11行是网上找的另一种反检测的方法，也记在这里

with open('stealth.min.js') as f:
    js = f.read()
driver.execute_cdp_cmd("Page.addScriptToEvaluateOnNewDocument", {
    "source": js
})
driver.get(url)
```

# 获取 stealth.min.js

[Github](https://g.nite07.org/berstend/puppeteer-extra/blob/master/packages/extract-stealth-evasions/readme.md)

Github 里并没有直接提供 `stealth.min.js` 需要自己生成。
我试着跑了一下代码，但是报错了，没能解决。
这里贴一下错误 ![](/img/Python爬虫防止selenium被检测/2.png)

这是我在网上找到的 `stealth.min.js`
{% btn '/download/index.html?f=stealth.min.js',下载 %}
