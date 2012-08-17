---
layout: post
title: "Install QRcode static library in iOS"
description: ""
category: 
tags: []
---
{% include JB/setup %}

![hello shell](/assets/images/shell.png)

最近工作需要在一个iOS项目中使用qrcode扫描并识别的功能。搜索以后发现在sourceforge上有一个叫做zbar的项目,其包含了qrcode几乎大多数的算法实现，并提供丰富的语言和界面库的binding。官方也提供了一个iPhone App的演示代码，并且提供libzabr.a这样的静态库方便下载使用。事情到这里似乎很完满，借助开源社区的积木迅速搭建项目!

不幸的是，这个静态库似乎对中文的qrcode兼容性不是很好。浏览源码之后,看到作者考虑了东亚语系的问题,那么问题可能在于其官方提供的那个静态库了。既然这样，我就自己来一发吧。

编译iOS上的静态库其实和编译一般的c库程序没有什么不同.唯一需要知道的是，代码在X86架构的mac下需要使用交叉编译到arm结构上的iPhone设备。这里提供一个较为通用的静态编译脚本给大家。

<script src="https://gist.github.com/3371314.js?file=compile-static-library-on-ios.sh"></script>
