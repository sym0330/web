---
title: '[敛火成丹]Win11Dev-25236.1010专业工作站版-微调'
tags: [实用资源, Windows, 系统镜像]
cover: /img/w2004zx/1.jpg
date: 2022-11-15 08:56:44
updated: 2022-11-15 08:56:44
categories: [实用资源, Windows, 系统镜像]
urlname: w11dev
keywords: [实用资源, 破解, 去广告, 纯净, 绿色, 白嫖, 免费, Windows, 系统镜像]
---

_近来研究了下 Win11 的各个版本，发现 Dev 的调度相当激进，在 Server2025 上也有所体现，它和专工是孪生版本，于是乎整了这个镜像给老师_

###### 如果使用此系统发现任何问题请回帖留言，我将于放假时回应并尽力修复。

配方文件公开于网盘，也可根据自己需求进行修改，开学了也希望有人能够替我更新，用 MSMG（或其改版）和 NTLite（免费版）就好，DISM++可调
部分集成来源于 MSMG，部分优化来源于 MDL 和论坛，感谢各位坛友的支持！
以 UUP 为母盘微调优化制作，**仅专业工作站版**，可自行修改为其他版本
VM 虚拟机测试请使用单 U 单核，虽然性能如图所示的降低但是可以开机而不会蓝屏提示不支持的平台
此版本暂未发现官方 BUG 之外的问题，已经拆除时间限制和弹窗，但保留水印以明确版本，请自行测试各类软件，若异常可以回本帖探讨解决方案

##### 提供 ISO 镜像，带 UIA 为无人值守非内置管理员账户版本（即 UIA,无人值守版本无 WinRE

提供镜像原始 winre.wim 和常用注册表恢复、打印机共享修复、新旧右键菜单切换
网盘里有 Restore.zip，需要 MPO、幽灵熔断防护等都可在此恢复。**不希望看到~~多余~~的右键菜单，分享链接有提供右键菜单管理工具.Net3.5 版，可自行关闭或删除**

#### 不封装，保留原味驱动，保留绝大部分功能组件和附件，ISO 的版本可更新

# 资源直达：

京服隧道：[pan.huang1111.cn/s/bmZ9hY](https://pan.huang1111.cn/s/bmZ9hY 'pan.huang1111.cn/s/bmZ9hY')
Cloudreve 公益盘：share.nite07.com/s/PKDtn
OneDrive 国际版：[liuxiane5-my.sharepoint.com/:f:/g/personal/zxgu183_e5_liuxianl_com/EkAlhcrW3b1PjQ0hdqlbCbQBFnEh46QFDLlAEKU3D2DQWg?e=PVtRhY](https://liuxiane5-my.sharepoint.com/:f:/g/personal/zxgu183_e5_liuxianl_com/EkAlhcrW3b1PjQ0hdqlbCbQBFnEh46QFDLlAEKU3D2DQWg?e=PVtRhY 'liuxiane5-my.sharepoint.com/:f:/g/personal/zxgu183_e5_liuxianl_com/EkAlhcrW3b1PjQ0hdqlbCbQBFnEh46QFDLlAEKU3D2DQWg?e=PVtRhY')

### 系统状态截图

[![38-0.7](https://tva4.sinaimg.cn/large/0073r2KBly1h82dqw1b73j30so0ls0uw.jpg '38-0.7')

## 集成与启用

- 集成.NET 3.5 框架
- 集成 WTG
- 集成常用 VC 运行库
- 启用 Windows 投影文件系统 (ProjFS)
- 启用 NFS 功能
- 允许 DirectPlay 安装
- 启用 LPD 与 LPR 打印服务
- 启用 SMB 1.0/CIFS 文件共享
- 启用 XPS 文档写入
- 启用 Telent 远程支持
- 启用虚拟机平台支持
- Win32 计算器顶替 UWP 计算器并替换来自 MDL 的 Metro 皮肤
- 照片查看器顶替 UWP 图片并替换来自 MDL 的 Metro 皮肤（非无人值守版 MediaPlayer 也为 Metro）
- IE 顶替 Edge 并在桌面显示图标
- Notepad2 顶替传统记事本并卸载 UWP 记事本（UIA 集成 Notepad3 并自动适配深色模式）
- 桌面右键新增传统个性化、一键息屏
- 此电脑右键添加编辑 Hosts
- 此电脑 Shift 右键添加上帝模式、系统配置、组策略、经典属性面板、注册表编辑器菜单
- DLL、OCX 右键菜单添加注册/反注册
- 右键菜单添加管理员取得所有权
- 回收站右键菜单清除 DNS 缓存
- Shift 右键添加“复制路径”和隐藏菜单
- UIA 非极限版集成静默安装 7z、MPC-BEx64UWP、Notepad3（适配深色模式）

### 保留这些应用

[![MetroMDL](https://tvax3.sinaimg.cn/large/0073r2KBly1h4w0zdtk22j31bq0pqaig.jpg 'MetroMDL')

### 正常的截图快捷键和暗影主题

[![正常的截图快捷键和暗影主题](https://tva4.sinaimg.cn/large/0073r2KBly1h4w0zdx778j30t10m7myw.jpg '截图快捷键+剪切板历史')

## 优化调整

- Edge 禁用 SmartScreen
- IE11 开启企业模式
- IE 不提示默认浏览器，不检查下载程序的签名
- IE 允许活动内容在我的电脑的文件运行
- IE 开启 ClearType
- IE 开启兼容显示并跳过首次引导关闭升级
- IE 禁用建议的网站
- Winlogin 自动重连
- 不主动检测联网，防止打开浏览器占用
- 不再请求我的反馈
- 不要上报感染信息
- 关联照片查看器
- 关闭 Edge 用户反馈
- 关闭 MPO，防止 GPU 拖前台后腿
- 关闭 RPC 隐私保护以解决打印机共享 11b
- 关闭 Smartscreen 应用筛选器
- 关闭 VBS，防止 CPU 拖后腿
- 关闭 WindowsInk 推荐应用
- 关闭 WindowsMessenger 客户体验改差计划
- 关闭上传用户活动
- 关闭仅限管理员安装驱动程序
- 关闭偶尔在开始菜单中显示建议
- 关闭写入调试信息
- 关闭在设置应用中为我显示建议的内容
- 关闭备胎共享
- 关闭小娜搜索、WD 记录
- 关闭幽灵(Spectre)与熔断(Meltdown)
- 关闭打开程序警告
- 关闭搜索框建议 (关闭 Bing 在线搜索和广告)
- 关闭数据采集遥测
- 关闭新版记事本提示
- 关闭显示受保护文件时警告提示
- 关闭更新后以及登录后显示 Windows 欢迎体验以显示新增功能和建议内容
- 关闭查找我的设备
- 关闭火狐数据上传
- 关闭系统推荐
- 关闭系统自动调试功能
- 关闭网络内容评估
- 关闭量身腚制的体验
- 关闭驱动签名验证
- 删除 SmartScreen 进程启动项
- 删除启用安全中心通知
- 去除 USB3 以上部分询问，常用于解决 USB3 刷机
- 去除 Win11 升级检测
- 去除硬件不符水印
- 启用 FMP3 专业解码器
- 启用 Resetbase
- 启用应用程序预读
- 屏蔽防病毒软件监控
- 应用使用广告 ID-关
- 强制关闭篡改防护
- 微软拼音候选词 9 个
- 忽略安装更新预定时间
- 我的电脑 Shift 右键组策略
- 打开开发人员模式
- 文件系统长路径显示
- 显示所有文件扩展名加快 UI 速度最高壁纸质量去除快捷方式副本后缀
- 查看诊断数据-关
- 禁止体验共享
- 禁止创建内存调试文件
- 禁止在重新启动时覆盖内存
- 禁止登录后创建成功登录报告功能
- 禁止网络搜索无关联文件方式
- 禁用 EdgeV9 钓鱼网站过滤
- 禁用 MSOffice 记录和遥测
- 禁用 VisualStudio 遥测
- 禁用 Windows 客户体验改差计划
- 禁用内容交付管理器订阅
- 禁用功能更新的保护措施
- 禁用在线提示
- 禁用提交数据样本和间谍报告
- 禁用组件堆栈和更新解压模块日志
- 禁用计划的系统维护
- 禁用诊断中心标准收集器服务
- 禁用诊断反馈相关
- 禁用诊断策略服务
- 禁用通用遥测客户端
- 禁用错误报告
- 禁用错误报告服务
- 经典系统属性添加接口
- 自动释放多余 DLL
- 解除驱动安装弹窗
- 设置默认保留带宽为 0
- 诊断数据-基本
- 跳 WindowsMediaPlayer 首次使用并设置本地策略
- 错误报告不再记录
- 阻止手写数据共享
- 阻止手写错误报告
- 驱动器 Shift 右键优化驱动器
- 驱动器 Shift 右键磁盘清理

---

## 精简列表

1. （仅无人值守版精简此条）简体中文之外的其他语言和无用字体、Windows Media Player
2. Windows 安全中心和 Defender
3. EdgeChromium
4. EdgeWebView
5. GameExplorer
6. SpeechRecognition
7. WinSAT
8. WindowsTIFFIFilter
9. WindowsMail
10. CEIP
11. KernelDebugging
12. UnifiedTelemetryClient
13. WindowsErrorReporting
14. WindowsInsiderHub
15. OneDrive
16. Cortana
17. EasyTransfer
18. Narrator
19. CBSPreview
20. ContentDeliveryManager
21. Edge
22. EdgeDevToolsClient
23. WindowsReaderPDF
24. ECApp
25. MapControl
26. NarratorQuickStart
27. ParentalControls
28. PeopleExperienceHost
29. RetailDemoContent
30. SkypeORTC
31. SmartScreen
32. WebcamExperience
33. WindowsMixedReality
34. MixedRealityPortal
35. 3DViewer
36. SkypeApp
37. 其他部分可卸载重装应用

---

_MSMG 的 pkg 列表如上，直接 ToolkitHelper 即可，NTLite 见网盘配方
优化主要是注册表
DISM++自己看_

>     桌面壁纸和锁屏壁纸来源：Pixiv画师banishment作品
>
> 如果有更好的优化方案和建议或我做的哪里不好，请在帖子下不吝指点，感谢各位坛友支持！
