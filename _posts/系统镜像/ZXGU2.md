---
title: "[朝气蓬勃]Windows 11 22621.1825 Pro 22H2Beta"
tags: [中文, 实用资源, Windows, Windows镜像]
cover: /img/ZXGU2/1.jpg
date: 2022-08-15 12:44:00
updated: 2023-05-28 05:00:00
categories: [实用资源, Windows, 系统镜像]
urlname: w22h2rpzx
keywords: [实用资源, 破解, 去广告, 纯净, 绿色, 白嫖, 免费, Windows, Windows镜像]
---

##### 以原版集成更新为母盘，仅专业版，可自行挂载转换/修改或安装后转换为其他版本，**不过度优化**，尽力保证系统的稳定性和流畅度

##### 提供 ISO 镜像，带 RE 为非无人值守有 WinRE 版本，带 Administrator 为无人值守无 WinRE 版本，ESD 为极限精简无人值守版本

网盘提供镜像原始 winre.wim 和内置 Administrator/新建 IAdmin 账户无人值守应答文件、打印机共享修复、新旧右键菜单切换等

注册表开关及恢复见 Restore_Switch.zip，需要 MPO、幽灵熔断防护等都可在此恢复。**不希望看到~~多余~~的右键菜单，分享链接有提供右键菜单管理工具.Net3.5 版，可自行关闭或删除**

需要使用指纹、人脸解锁等**Windows Hello 功能请使用新建账户**，不建议在内置 Administrator 账户登录微软账号，安装时可根据需求选择无人值守应答文件，使用工具替换或自行重命名并替换 Windows/Panther/Unattend.xml 即可，也可在安装后自行新建

#### 不封装，保留原版驱动，保留绝大部分功能组件和附件，ISO 的版本**可更新**

# 资源直达：

## **系统镜像**与调整/恢复开关

钛盘（香港-推荐）：[ttttt.link/room/6470a9961788c](https://ttttt.link/room/6470a9961788c "https://ttttt.link/room/6470a9961788c")

钛盘：[tmp.link/room/6470a9961788c](https://tmp.link/room/6470a9961788c "https://tmp.link/room/6470a9961788c")

OneDrive 国际版：[liuxiane5-my.sharepoint.com/:f:/g/personal/zxgu183_e5_liuxianl_com/Eti1b4PwRyBBqro67KTJPLcBNPAr-QBTo0jzFMDK2RGWyg?e=gAVZT9](https://liuxiane5-my.sharepoint.com/:f:/g/personal/zxgu183_e5_liuxianl_com/Eti1b4PwRyBBqro67KTJPLcBNPAr-QBTo0jzFMDK2RGWyg?e=gAVZT9 "https://liuxiane5-my.sharepoint.com/:f:/g/personal/zxgu183_e5_liuxianl_com/Eti1b4PwRyBBqro67KTJPLcBNPAr-QBTo0jzFMDK2RGWyg?e=gAVZT9")

**链接长期有效，没有文件就是在上传/制作**

**当前系统版本：Windows 11 Insider Preview 10.0.22621.1825 (ni_release) amd64**

**欢迎网快的网友分流！可跟帖点评/评论以发送链接**

### Store 恢复包和 Xbox 附属应用包

**Store 恢复包**：版本：22206.1401.6.0

[zxgu.lanzout.com/iS5lU0ahd2cf](https://zxgu.lanzout.com/iS5lU0ahd2cf "https://zxgu.lanzout.com/iS5lU0ahd2cf")

密码:`bzi6`

Xbox-Core：此包为 Xbox**附属应用**提供包，主体应用请前往 Store 下载

[zxgu.lanzout.com/iIcGz0ahd1pc](https://zxgu.lanzout.com/iIcGz0ahd1pc "https://zxgu.lanzout.com/iIcGz0ahd1pc")

密码:`6d0w`

\*运行**install.bat**即可恢复

理论上**支持 Win10x64/Win11 全部版本**（前提没禁用 APPX）

如果只需要 Win+G 功能，可在恢复 Store 后下载 Xbox Game Bar\*

###### 如果使用此系统发现任何问题请回帖留言，我将于放假时回应并尽力修复。

### 系统状态截图

![占用.jpg](https://s2.loli.net/2023/05/27/kWNJSzbvRFIlHu5.jpg)

## 集成与启用

**对所有版本**

-   集成.NET 3.5 框架
-   集成 WTG
-   照片查看器顶替 UWP 图片并替换来自 MDL 的 Metro 皮肤（RE 版 MediaPlayer 也为 Metro）
-   IE 顶替 Edge 并在桌面显示图标
-   Notepad2 顶替传统记事本并卸载 UWP 记事本

**以下是无人值守版添加的启用与集成**

-   启用 Windows 投影文件系统 (ProjFS)
-   允许 DirectPlay 安装
-   启用 LPD 与 LPR 打印服务
-   启用 SMB 1.0/CIFS 文件共享
-   启用 XPS 文档写入
-   启用 Telent 远程支持
-   Win32 计算器顶替 UWP 计算器并替换来自 MDL 的 Metro 皮肤
-   （仅**非 ESD**版）集成静默安装 Nanazip、MPC-BEx64UWP、Notepad3（适配深色模式）

## 优化与调整

**_调整自上而下分为三个版本，三个镜像先后制作，若调整项冲突则以后出现的为准_**

**对所有版本**

1. 禁用安全中心所有服务
2. 关彻 WD 遗孤 ExploitProtection
3. 删除启用安全中心通知
4. 关闭启用安全中心防火墙通知
5. 关机时清理页面文件
6. 关闭 RPC 隐私保护以解决打印机共享 11b
7. 关闭内核完整性与 SystemGuard 保护
8. 关闭基于虚拟化的安全(VBS)，防止 CPU 拖后腿
9. 关闭多平面覆盖(MPO_disable)，防止 GPU 拖前台后腿
10. 关闭幽灵(Spectre)与熔断(Meltdown)防护
11. 关闭幽灵熔断防护
12. 关闭打开程序安全警告
13. 关闭数据采集遥测
14. 关闭显示受保护文件时警告提示
15. 关闭资源管理器广告
16. 关闭量身腚制的体验
17. 关闭微软拼音云计算
18. 取消 7G 更新预留空间
19. 去除 USB3 以上部分询问，常用于解决 USB3 刷机
20. 不自动更新驱动
21. 启用 HTTP1.1 和 1.2
22. 启用 TLS1.0、1.1、1.2、1.3
23. 启用开发人员模式
24. 开启 TSX 英特尔事物扩展
25. 开启硬件加速 GPU 调度
26. 微软拼音开启自动拼音纠错
27. 忽略安装更新预定时间
28. 电源按钮不隐藏睡眠
29. 禁止 ModernApp 使用 smartscreen
30. 禁止云内容
31. 禁止遥测体验报告
32. 禁用 BitLocker 自动设备加密
33. 禁用 Windows 客户体验改差计划
34. 禁用传递推广建议
35. 不再请求我的反馈
36. 不要上报感染信息
37. 屏蔽本地账户数据出国处理
38. 使用 UTC 时间，防止多系统时间不同步
39. 禁用计划的系统维护
40. 禁用诊断反馈相关
41. 禁用运行监视器服务
42. 禁止错误报告
43. 错误报告不再记录
44. 禁用错误报告服务
45. 禁止自动播放
46. 禁用远程协助
47. 解除驱动安装弹窗
48. 去除硬件不符水印
49. 设置默认保留带宽为 0
50. 驱动器 Shift 右键菜单优化驱动器
51. 驱动器 Shift 右键菜单磁盘清理
52. DLL、OCX 文件添加注册和反注册右键菜单
53. 桌面右键菜单添加一键息屏
54. 桌面右键菜单切换深浅主题
55. 桌面右键菜单菜单传统个性化
56. 桌面 Shift 右键添加“重启资源管理器”菜单
57. 补充 notepad 注册表
58. 文件与目录 Shift 右键菜单管理员取得所有权
59. 文件与目录 Shift 右键菜单隐藏选项
60. 此电脑 Shift 右键菜单上帝模式
61. 此电脑 Shift 右键菜单注册表编辑器
62. 此电脑 Shift 右键系统配置
63. 此电脑 Shift 右键经典系统属性
64. 此电脑 Shift 右键菜单组策略
65. 此电脑右键菜单编辑 Hosts
66. 回收站右键菜单清除 DNS 缓存
67. MSI 文件增加“解包”菜单
68. HTML 右键增加“编辑”菜单
69. 未知文件添加“用记事本打开”菜单
70. 打开方式添加“记事本”
71. 创建桌面 IE 图标

**以下是无人值守版添加的优化调整**

1. IE11 开启企业模式
2. IE 不提示默认浏览器，不检查下载程序的签名
3. IE 允许活动内容在我的电脑的文件运行
4. IE 开启 ClearType
5. IE 开启兼容显示并跳过首次引导关闭升级
6. IE 禁用建议的网站
7. Winlogin 自动重连
8. 关闭 NCSI 联网主动检测，防止打开浏览器占用
9. 关机时不清理页面文件以加快速度
10. 关闭 sysmain 服务
11. 关闭 WindowsInk 推荐应用
12. 关闭 WindowsMessenger 客户体验改差计划
13. 关闭上传用户活动
14. 关闭仅限管理员安装驱动程序
15. 关闭偶尔在开始菜单中显示建议
16. 关闭全屏乱优化
17. 关闭写入调试信息
18. 关闭在设置应用中为我显示建议的内容
19. 关闭备胎共享
20. 关闭小娜搜索、WD 记录
21. 关闭搜索框建议 (关闭 Bing 在线搜索和广告)
22. 关闭更新后以及登录后显示 Windows 欢迎体验以显示新增功能和建议内容
23. 关闭查找我的设备
24. 关闭火狐数据上传
25. 关闭粘滞建
26. 关闭系统推荐
27. 关闭系统自动调试功能
28. 关闭网络内容评估
29. 关闭驱动签名验证
30. 加快 UI 速度最高壁纸质量去除快捷方式副本后缀
31. 允许驱动自动更新
32. 微软拼音候选词 9 个
33. 微软拼音关闭自动拼音纠错
34. 开启微软拼音云计算
35. 允许自动播放
36. 启动时不更新组策略
37. 启用 FMP3 专业解码器
38. 启用 Resetbase
39. 启用应用程序预读
40. 应用使用广告 ID-关
41. 查看诊断数据-关
42. 诊断数据仅基本
43. 允许远程协助
44. 禁止体验共享
45. 禁止创建内存调试文件
46. 禁止在重新启动时覆盖内存
47. 禁止显示搜索要点
48. 禁止登录后创建成功登录报告功能
49. 禁止网络搜索无关联文件方式
50. 禁用 MSOffice 记录和遥测
51. 禁用 VisualStudio 遥测
52. 禁用内容交付管理器订阅
53. 禁用在线提示
54. 禁用提交数据样本和间谍报告
55. 禁用组件堆栈和更新解压模块日志
56. 自动释放多余 DLL
57. 阻止手写数据共享
58. 阻止手写错误报告

**以下是极限精简版添加的调整**

1. 电源策略：平衡模式——频率硬件调频，调度硬件调度，核心休止也完全由硬件控制。最佳能效——只调度小核。最佳性能——平衡模式下不降频
2. 默认关闭透明
3. 关闭微软拼音云计算
4. 关闭虚拟内存
5. 开机快速加载桌面
6. 禁止应用后台运行
7. 禁用页面文件
8. 关闭休眠
9. 关闭自动维护计划
10. 不自动更新驱动
11. 禁用远程协助
12. 禁止自动播放

---

## 精简项目

-   **Windows Defender**
-   **Edge**Chromium
-   EdgeWebView
-   GameExplorer
-   SpeechRecognition
-   Wallpapers
-   WindowsTIFFIFilter
-   WinSAT
-   OpenSSH
-   WindowsMail
-   CEIP
-   KernelDebugging
-   UnifiedTelemetryClient
-   WiFiNetworkManager
-   WindowsErrorReporting
-   WindowsInsiderHub
-   OneDrive
-   EasyTransfer
-   Narrator
-   CBSPreview
-   ContentDeliveryManager
-   ECApp
-   Edge
-   EdgeDevToolsClient
-   WindowsReaderPDF
-   MapControl
-   NarratorQuickStart
-   NcsiUwpApp
-   OOBENetworkCaptivePortal
-   OOBENetworkConnectionFlow
-   ParentalControls
-   PeopleExperienceHost
-   RetailDemoContent
-   SecureAssessmentBrowser
-   SkypeORTC
-   SmartScreen
-   WebcamExperience
-   WindowsMixedReality
-   Alarms
-   BingNews
-   BingWeather
-   Camera
-   ClientWebExperience
-   Clipchamp
-   CommunicationsApps
-   Cortana
-   Family
-   FeedbackHub
-   GetHelp
-   Getstarted
-   Maps
-   NotepadApp
-   OfficeHub
-   People
-   Photos
-   PowerAutomateDesktop
-   SolitaireCollection
-   SoundRecorder
-   StickyNotes
-   StorePurchaseApp
-   Terminal
-   Todos
-   Windows**Store**App
-   YourPhone
-   ZuneMusic
-   ZuneVideo
-   其他部分可卸载重装应用（APPX**均可卸载重装**）

---

> 桌面壁纸和锁屏**壁纸来源**：Pixiv 画师**banishment**作品

如果有更好的优化方案和建议或我做的哪里不好，请在帖子下不吝指点，感谢支持！
