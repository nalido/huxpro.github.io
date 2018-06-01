---
layout:     post
title:      "[IOS] xcode9 开发过程踩坑纪录"
subtitle:   ""
date:       2018-05-29 17:04:00
author:     "Nalido"
header-img: "img/post-bg-2015.jpg"
catalog: true
tags:
    - 编程笔记
    - object-c
    - iOS
    - xcode
---

1. 添加第三方库或者代码时, import提示`.h file not fonud`. ** 1.project>clean. 2.删掉import重新写一遍 **
2. 报错 'apple mach-o linker error': 一般是framework加载错了, 查询报错的变量所属于的framework, 添加后重新build就可以了.
3. 将中文字符串由`char*`转为`NSString*`时会变成乱码. 转换时需要加上编码格式:
~~~~~~~~c
char *Message = "中文字符串";
NSString *nsMessage= [[NSStringalloc] initWithCString:Message encoding:NSUTF8StringEncoding]; //转换
~~~~~~~~
4. object-c 类的成员变量加上`@public` 后就可以对其直接赋值. (只要在第一个变量前加就可以作用到全部变量)

5. 使用ffmpeg时,很容易出现内存泄漏,要格外小心. xcode的内存泄漏检查工具`Instruments`很有用,可以轻松定位到泄漏的代码.<br/>
[使用Xcode Instruments Leak解决内存泄漏问题](https://blog.csdn.net/Zsk_Zane/article/details/52016411)
