---
title: Mirai插件开发笔记(Java)
date: 2021-09-02 22:17:26
categories: 笔记
tags: [plugin, mirai, java]
urlname: miraiplugindev
cover: /img/Mirai插件开发/1.jpg
keywords: [plugin, mirai, java]
updated: 2022-05-20 12:21:00
---

# 创建项目（IntelliJ IDEA）

使用插件创建项目比较简单，IDEA 插件名：`Mirai Console`

# 使用外部库

## 方案一

将所有用到的外部库放到 `lib` 文件夹  
修改 `bulid.gradle.kts` ，在结尾添加

```kotlin
dependencies {
    implementation(fileTree(mapOf("dir" to "lib", "include" to listOf("*.jar"))))
}
```

## 方案二

修改 `bulid.gradle.kts` ，手动添加  
例如：

```kotlin
dependencies {
    implementation('org.jsoup:jsoup:1.14.2')
}
```

# 输出 log

```java
getLogger().info("Log内容");
```

# 事件监听

```java
// 创建监听
Listener listener = GlobalEventChannel.INSTANCE.subscribeAlways(GroupMessageEvent.class, event -> {
    event.getSubject().sendMessage("Hello!"); // 回复消息
})

listener.complete(); // 停止监听
```

[全部事件列表](https://docs.mirai.mamoe.net/EventList.html#%E4%BA%8B%E4%BB%B6%E5%88%97%E8%A1%A8%E4%B8%80%E8%A7%88)

# 被动发送消息

当别人发送消息时被动发送消息，需要监听 Message 事件，同上例  
`event.getSubject()` 的类型根据监听不同事件对应不同类型

例如：  
监听 `GroupMessageEvent` 则 `event.getSubject()` 是 `Group` 类型  
监听 `FriendMessageEvent` 则 `event.getSubject()` 是 `Friend` 类型

# 获取 Bot 实例

1. `Bot.getInstances()` 获取所有已登录的 Bot
2. `Bot.getInstance(id)` 获取指定 Bot，id 为 QQ 号

# 主动发送消息

需要先获取 Bot 实例

## 发送好友消息

```java
Bot bot = Bot.getInstance(Bot QQ号);
bot.getFriend(好友QQ号).sendMessage();
```

## 发送群消息

```java
Bot bot = Bot.getInstance(Bot QQ号);
bot.getGroup(QQ群号).sendMessage();
```

# 构建消息

## 常用类型

```java
PlainText p = new PlainText(消息内容); //普通文本消息
Face.DA_XIAO //QQ表情：大笑
At at = new At(QQ号); //@某人
```

## MessageChain

由多个 `SingleMessage` 组成的消息链，不同消息之间用 `plus()` 方法连接

```java
PlainText p = new PlainText("第一段消息");
MessageChain msg = p.plus(Face.DA_XIAO);
msg = msg.plus(new At(123456789));
```

需要注意的是 plus 方法是返回新的 MessageChain，而不是在原链基础上增加，所以要 `msg = msg.plus()`

## 图片消息

### 本地图片

```java
Image img = Contact.uploadImage(friend, new File(图片路径));
```

### 网络图片

```java
Image img = Contact.uploadImage(friend, new URL(图片链接).openConnection().getInputStream());
```

都使用 `msg = msg.plus(image)` 连入消息链
