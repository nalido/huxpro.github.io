---
layout:     post
title:      "[python3] 打开文件open函数的坑"
subtitle:   ""
date:       2018-04-27 18:04:00
author:     "Nalido"
header-img: "img/post-bg-2015.jpg"
catalog: true
tags:
    - 编程笔记
    - python3
---

Python3中打开文件的open函数和python2不同,经常会导致各种莫名其妙的错误.

例如读取json时,以下代码在Python2中可以正常运行.
~~~~~~~python
with open(jsFile, "a+") as f:
    try:
        dct = json.load(f)
    except ValueError as e:
        print('load json failed.', e)
        dct = {}
~~~~~~~

但是在python3中,上述代码就会报错.
~~~~~~~
Expecting value: line 1 column 1 (char 0)
~~~~~~~

官方文档中有提到,open的mode参数的一些限制,好像是某些参数不能同时使用,例如`a`和`+`不可以同时使用.(但是忘记官方文档里的具体内容了,待补充)

因为老是踩到这个坑,怒而记之.
