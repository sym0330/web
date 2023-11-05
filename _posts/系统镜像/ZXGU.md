---
title: '[朝气蓬勃][22H2]Win11.0.22622.586专工-微创-优化'
tags: [中文, 实用资源, Windows, Windows镜像]
cover: /img/ZXGU/1.jpg
date: 2022-07-21 19:12:11
updated: 2022-08-30 10:00:11
categories: [实用资源, Windows, 系统镜像]
urlname: zxgu
keywords: [实用资源, 破解, 去广告, 纯净, 绿色, 白嫖, 免费, Windows, Windows镜像]
---

_终于，22621 上了 22H2 通道，比 22000 性能好很多也稳定很多，于是乎出一个优化微创版。如果这个作品合你心意，那么我感到荣幸至极。如果使用此系统发现任何问题请回帖留言，我将于放假时回应并尽力修复。_

配方文件公开于网盘，也可根据自己需求进行修改，开学了也希望有人能够替我更新，用羊大汉化的工具和 NTLite（免费版）就好，DISM++可调

部分集成来源于 MSMG，部分优化来源于 MDL 和论坛，感谢各位支持！

### 以 UUP 下载的 22622.586 为母盘，仅专业工作站版，id=a6430260-66ab-4049-980d-f12b88ff59a8

## 提供 ISO 镜像，带 Administrator 为无人值守版本（无人值守版本无 WinRE），带 RE 为有恢复环境的版本，ESD 镜像为不可打补丁和增删功能的 WinSxS 极限精简版

## 提供 Windows 目录下被修改/替换/删除的镜像原始文件和常用注册表恢复

**如果你需要用到 Hyper-V 或 WSL/WSA，那么请在 reg_restore.zip 恢复 Exploit Protection，需要 MPO、幽灵熔断防护等都可在此恢复。不希望看到多余的右键菜单，分享链接有提供右键菜单管理工具.Net3.5 版，可自行关闭或删除，同时提供可恢复 Win11 新右键菜单的工具**

### 不封装，保留原味驱动，保留绝大部分功能组件和附件，可更新

# 资源直达：

```
京服隧道：https://pan.huang1111.cn/s/YeMQIA
CF世纪互联Cloudreve：https://pan.igjbbs.cn/s/rqXSk
Nite07公益盘：https://share.nite07.com/s/GokuE
OneDrive国际版：https://liuxiane5-my.sharepoint.com/:f:/g/personal/zxgu183_e5_liuxianl_com/ErZsK-TYX81Og2C9GHcwu48BgAd7yXuOi0j5183OHRKtrg?e=OesUb7
```

## 系统状态截图

![](https://tvax4.sinaimg.cn/large/0073r2KBly1h4w0zd9nckj30ss0lqjuu.jpg)

## 系统信息旁边要素过多但是挺正常的

![](https://tva3.sinaimg.cn/large/0073r2KBly1h5mvbziaikj31ha0pqjve.jpg)

# 集成列表

```
集成.NET 3.5框架
集成DirectX9c
集成常用VC运行库
Win32计算器顶替UWP计算器并替换来自MDL的Metro皮肤
照片查看器顶替UWP图片并替换来自MDL的Metro皮肤（自建账户版MediaPlayer也为Metro）
IE顶替Edge并在桌面显示图标
Notepad2顶替传统记事本并卸载UWP记事本
桌面右键新增传统个性化
此电脑右键添加上帝模式、组策略、系统配置、注册表编辑器、"关闭显示器"菜单
```

## 映像信息和桌面右键（除个性化外新增菜单已移至此电脑右键）

![](https://tvax4.sinaimg.cn/large/0073r2KBly1h4w0zdpfs6j31bq0pqzsj.jpg)

## 保留这些应用

![](https://tvax3.sinaimg.cn/large/0073r2KBly1h4w0zdtk22j31bq0pqaig.jpg)

## 正常的截图快捷键和暗影主题

![](https://tva4.sinaimg.cn/large/0073r2KBly1h4w0zdx778j30t10m7myw.jpg)

# 优化调整：

```
禁用 Microsoft 用于 Windows 更新保留的存储空间
关闭Windows 更新自动更新驱
禁用自动下载并安装第三方应用
禁用自动执行 Windows 升级，将Windows 自动更新调整为手动更新，排除驱动程序，排除恶意软件删除工具
禁用 Windows 防火墙
关闭 Exploit Protection
禁用运行监视器、错误报告服务、远程协助、远程修改注册表、程序兼容性助手服务、"Windows 跟踪应用启动"等一系列信息收集服务
干翻遥测、"客户体验改善计划"、"体验共享"等相关隐私收集（如果觉得过分或者不够完美可以使用wpd.app和dl5.oo-software.com/files/ooshutup10/OOSU10.exe调整）
关闭MPO并优化显卡设置，防止GPU拖前台后腿
关闭VBS，防止CPU拖后腿
注册表和更新补丁携手帮扶打印机
注册表法关闭驱动签名验证
禁用超级预读取服务
微软拼音默认为英语输入
禁止应用"后台运行"
关闭"写入调试信息"、"写入系统日志"、禁止"C盘创建DumpStack"文件
关闭打开程序"安全警告"
关闭存储感知
关闭Store"自动更新"
打开剪贴板历史记录
打开自动登录选项
APPX开发人员模式
文件打开方式添加“记事本”
MSI 文件增加“解包”菜单
HTML 右键增加“编辑”菜单
Shift 右键添加“复制路径”菜单
Shift 右键添加"隐藏"功能
未知文件添加"用记事本打开"菜单
Shift 右键添加"在此处打开命令窗口"
恢复照片查看器
关闭防病毒软件监控
不加载多余的DLL文件
关闭幽灵熔断防护
禁止在重新启动时覆盖内存
网络连接设置为按流量计费
IE浏览器优化
关彻WD遗孤Exploit Protection
关闭鼠标加速
关闭体验反馈
UAC不提示并开启Administrator账户批准模式
禁止登录后创建成功登录报告功能
开启TSX
开启硬件优化
其他调整详见注册表文件
```

# 精简列表

```
（仅无人值守版精简此条）简体中文之外的其他语言和无用字体、Windows Media Player
精简并禁用 Windows Defender、移除安全中心、关闭"启用安全中心"通知、安全中心监视服务、SmartScreen、注册表开除SmartScreen进程
干翻遥测（Asimov）、"客户体验改善计划（CEIP）"、"体验共享"等相关隐私收集（如果觉得过分或者不够完美可以使用wpd.app和dl5.oo-software.com/files/ooshutup10/OOSU10.exe调整）
删除系统基本无用菜单
传统记事本顶替UWP记事本
清理Adobe Flash组件残留
游戏浏览器
语音识别和小娜、轻松访问相关组件
Windows TIFF IFilter（OCR）
Windows 系统评估工具(WinSAT)
Windows 邮件
WiFi 感知
Windows 错误报告
Windows 会员中心
OneDrive 桌面客户端
轻松传送
安全中心
指定访问锁定应用 - Windows 展台模式
Async Text 服务 - 人脉和地图应用的消息扩展
CBSPreview - 相机条形码扫描仪应用
Content Delivery Manager - 自动安装赞助或推广的应用、建议和广告
ECApp - 用于眼球运动控制的 Modern UI 对话框应用
Edge 经典浏览器
Edge 开发者工具客户端
地图控件
内容传递管理器
OOBE Network Captive Portal -强制网络门户
OOBE 网络连接流
People Experience 主机 - 人脉栏（People Hub）
零售演示内容
Secure Assessment Browser（Take Test 应用）
Skype ORTC
Webcam Experience
Windows 混合现实
Windows 阅读器 (PDF)
3D 查看器
Advertising Xaml广告商
闹钟和时钟
相机应用
反馈中心
电影和电视
获取帮助
Groove 音乐、Zure两个应用
地图应用
消息应用
Microsoft Pay
移动套餐
我的 Office
混合现实门户
OneNote
手机连接
照片
画图 3D
Print 3D
Services Store Engagement
Windows 应用商店应用
应用商店体验主机
Skype
便笺
Solitaire Collection
人脉
使用技巧
录音机应用
天气应用
小组件
家庭应用
Xbox相关（核心保留，可正常使用游戏优化和Win+G等，可通过应用商店恢复，已发布恢复包。）
```

MSMG 大致列表在网盘，NTLite 见配方

优化主要是注册表

~~DISM++自己看~~

> 桌面壁纸来源：Pixiv 画师 banishment 作品

如果有更好的优化方案和建议或我做的哪里不好，请在此楼不吝指点，感谢各位支持！
