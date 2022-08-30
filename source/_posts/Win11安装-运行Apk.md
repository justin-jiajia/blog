title: Win11安装/运行Apk
categories: 小技巧
tags: [电脑,小技巧]
date: 2022-02-13 20:11:00
---
看标题觉得很不可思议，对吧？我们只要在Win11电脑上安装Windows Subsystem for Android子系统就可以实现这个功能。

<!-- more -->

废话不多说，Lets go！

# 安装Windows Subsystem for Android子系统

## 下载

在我的博客网盘里下载它：https://url.yanjiajia.cn/hVLgv
**网盘嗝屁了！！**

## 启动

在开始菜单中搜索功能，进入启用或关闭Windows功能，勾上虚拟机平台，如图：

![示范](https://blog.yanjiajia.cn/wp-content/uploads/2022/02/Xshot-0001-1.png)

## 安装

> 用**管理员权限**运行**Powershell**，输入：

一定要用**PowerShell**！

```
cd C:\\Users\\jia\\Desktop\\ // 换成你下载WSA的路径
Add-AppxPackage "wsa"
```

![正在安装...](/images/Xshot-0002-1024x110.png)

在开始菜单中看到Windows Subsystem for AndroidTM就安装成功了！

![](/images/image.png)

成功！

# 安装APK

## 安装“APK文件安装程序”

在Microsoft Store中搜索APK文件安装程序，安装。

## 设置WSA

打开Windows Subsystem for AndroidTM，将开发人员模式设为开，并确保有IP地址，如图：

![](/images/Xshot-0003-1024x161.png)

## 安装APK程序

以后如果要安装APK程序，可以打开APK文件安装程序，安装。