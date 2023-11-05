---
title: Xposed，EdXposed，LSPosed，Magisk都是什么？
tags: [冲浪技巧]
cover: /img/Xposed，Edxposed，Lsposed，Magisk都是什么/1.jpg
date: 2023-02-15 00:46:35
updated: 2023-02-15 00:46:35
categories: [冲浪技巧]
urlname: xelmdssm
keywords: [冲浪技巧]
---

> 本文只简单介绍，框架具体安装方法可以参考 [Magisk 中文网](https://magiskcn.com/)，[LSPosed Wiki](https://github.com/LSPosed/LSPosed/wiki/How-to-use-it)
> 如果你觉得安装框架太费事但想要使用模块，可以使用 [LSPatch](https://github.com/LSPosed/LSPatch)

如果您是喜欢自定义设备的 Android 用户，您可能听说过 Xposed、EdXposed 和 LSPosed。 这些框架允许您修改 Android 应用程序和系统组件而无需实际更改它们。 这意味着您可以添加新功能、更改外观、绕过限制等，而无需对设备进行 root 操作或刷入自定义 ROM。

# Xposed 是什么？

Xposed 是最初的框架，由 rovo89 于 2012 年开发。它的工作原理是挂接到 Android 运行时并拦截方法调用，允许您动态修改它们。Xposed 拥有大量的模块集合，这些模块能够使用框架实现修改各种应用程序的功能，Xposed 最后一个正式版最高支持 Android 8.1 Oreo。

# EdXposed 是什么？

EdXposed 是 Xposed 的一个分支，适用于 Android 8~11，由 solohsu 和 MlgmXyysd 开发。它使用一种不同的 hook 方法，基于 Riru 框架，将代码注入 Zygote 进程（负责启动应用的系统进程）。EdXposed 还使用了 Magisk 框架，它允许您将模块安装为 Magisk 模块，而无需修改系统分区。EdXposed 与大多数 Xposed 模块兼容，但它默认 hook 所有应用所以会导致性能问题。

# LSPosed 是什么？

LSPosed 是 EdXposed 的一个新分支，适用于 Android 8~13，它更简单、易用且高效。它还使用了 Riru/Zygisk 和 Magisk 框架。它比 EdXposed 有一些改进。它具有更友好的用户界面，可让您更轻松地管理模块及其范围。它还具有更加模块化的设计，允许您选择 hook 哪些应用程序和系统组件，从而减少对性能和稳定性的影响。LSPosed 兼容 EdXposed 模块，它有专门的管理应用可以让你更新和管理框架本身。

# Magisk 是什么？

Magisk 是一款开源的 Android 框架，支持 Android 5.0 以上的设备。正如上文所提到的，Magisk 框架被 EdXposed 和 LSPosed 依赖，它允许您对设备进行 root、修改只读分区，以及隐藏 root。Magisk 的工作原理是在您的设备上创建一个虚拟分区，称为 Magisk 分区，它存储所有修改。这样就不会影响原来的系统分区，Magisk 还有一个配套应用程序，可让您管理 Magisk 框架和模块。

# 总结

总之，Xposed、EdXposed 和 LSPosed 是允许您修改 Android 应用程序和系统组件而无需实际更改它们的框架。它们各有优缺点，需要不同水平的技术知识和技能才能使用。它们还会对您设备的性能、稳定性、安全性和合法性产生不同的影响。使用它们可以为您提供很大的自由度和灵活性来自定义您的 Android 设备，但它也伴随着一些风险和责任。在安装任何模块之前，您应该始终备份您的设备和数据，因为其中一些可能会导致引导循环、崩溃或其他问题。您还应该注意授予模块的权限和数据，因为其中一些可能是恶意的或有害的。如果您需要在它们中选择一个，最先考虑的是您的 Android 版本。就个人而言，我会推荐 LSPosed，因为它是最现代的框架，具有很多功能和灵活性。

> 文章由 New Bing 生成
