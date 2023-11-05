---
title: VMware Workstation 安装 MacOS 13
tags: [MacOS, VMware, Workstation]
cover: /img/VMware安装MacOS/1.jpg
date: 2023-01-03 00:43:38
updated: 2023-01-03 00:43:38
categories: [冲浪技巧]
urlname: vmim13
keywords: [MacOS, VMware, Workstation]
---

1. 下载[iso 格式系统](/macosdownload)
2. 安装[VMware Workstation](/vmware)，下文简称 VM
3. 下载 VM 的 MacOS[解锁工具](https://g.nite07.org/paolo-projects/auto-unlocker/releases)
4. 解压解锁工具并以管理员身份运行**Unlocker.exe**
5. 点击**Patch**按钮，等待完成（过程中需要下载文件，如果下载过慢可以开系统代理）
6. 运行 VM -> 文件 -> 新建虚拟机 -> 典型 -> 下一步 -> 安装程序光盘映像文 -> 选择下载好的系统文件 -> 下一步 -> 客户机操作系统选 **Apple Mac OS** -> 版本选择 **macOS 13** -> 下一步(其他信息自行设置并下一步到最后点击完成)
7. 编辑虚拟机目录(默认路径为`文档\Virtual Machines\<步骤6中设置的虚拟机名称>`)下的 **<步骤 6 中设置的虚拟机名称>.vmx** 文件
8. 将 **board-id.reflectHost** 的值改为 **FALSE**
   `board-id.reflectHost = "FALSE"`
9. 将 **ethernet0.virtualDev** 的值改为 **vmxnet3**
   `ethernet0.virtualDev = "vmxnet3"`
10. 在文件末尾添加
    ```
    board-id = "Mac-AA95B1DDAB278B95"
    hw.model.reflectHost = "FALSE"
    hw.model = "MacBookPro19,1"
    serialNumber.reflectHost = "FALSE"
    serialNumber = "C01234567890"
    ```
    注意: 如果你使用 AMD 处理器，需要额外添加下列内容
    ```
    smc.version = "0"
    cpuid.0.eax = "0000:0000:0000:0000:0000:0000:0000:1011"
    cpuid.0.ebx = "0111:0101:0110:1110:0110:0101:0100:0111"
    cpuid.0.ecx = "0110:1100:0110:0101:0111:0100:0110:1110"
    cpuid.0.edx = "0100:1001:0110:0101:0110:1110:0110:1001"
    cpuid.1.eax = "0000:0000:0000:0001:0000:0110:0111:0001"
    cpuid.1.ebx = "0000:0010:0000:0001:0000:1000:0000:0000"
    cpuid.1.ecx = "1000:0010:1001:1000:0010:0010:0000:0011"
    cpuid.1.edx = "0000:0111:1000:1011:1111:1011:1111:1111"
    smbios.reflectHost = "TRUE"
    ```
11. 编辑虚拟机设置 -> 网络适配器 -> 选择 NAT 模式：用于共享主机的 IP 地址 -> 确定
12. 启动虚拟机
13. 选择 语言
14. 点击 **磁盘工具**
15. 选择左侧列表中的 **VMware Virtual SATA Hard Drive Meida**
16. 点击右上角 **抹掉**
17. 配置默认即可
18. 抹掉后点击左上角红色按钮退出磁盘工具
19. 点击 **安装 macOS Ventura**
20. 点击 **继续**
21. 点击 **同意**
22. 选择磁盘后点继续
23. 剩下的安装过程自行完成
24. 安装完成后需要安装 **VMware Tools** 提升体验
25. 右键桌面上的 **Install MacOS disc**，点击 **推出**
26. 在 VM 中编辑虚拟机设置 -> 硬件 -> CD/DVD (SATA) -> 使用 ISO 映像文件 -> 选择 `<解锁工具文件夹>\tools\darwin.iso` -> 点击上方的 **已连接** -> 确定
27. 根据桌面上出现的 VMware Tools 安装窗口完成安装
