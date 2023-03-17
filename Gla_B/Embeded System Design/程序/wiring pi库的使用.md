---
title: wiring pi库的使用
date: 2023-02-10T18:12:08Z
lastmod: 2023-02-14T09:42:38Z
---

# wiring pi库的使用

[raspberry-pi-beginners-guide-zh-cn-v1.11.pdf](../树莓派/assets/raspberry-pi-beginners-guide-zh-cn-v1.1-20230204141719-ganwgss.pdf)

![截图_20230214094231](assets/截图_20230214094231-20230214094237-32xcx2t.png)

![截图_20230208134117](assets/截图_20230208134117-20230208134119-9mn1101.png)

‍

[安装](https://zhuanlan.zhihu.com/p/487729568)

[树莓派点亮一个小灯](https://blog.csdn.net/weixin_44612221/article/details/112759125)

gpio readall 查看所有引脚

gpio -v 查看版本信息

--

gcc -o led -l wiringPi main.cpp每一个参数的含义

这是一条用于编译C++代码的命令，其中：

* ​`gcc`​ 是GNU Compiler Collection的缩写，是一组用于编译C、C++和其他语言的编译器。
* ​`-o led`​ 是指定编译后的可执行文件的名称，这里是`led`​。
* ​`-lwiringPi`​ 是指链接 `wiringPi`​ 库，这是一个用于在Raspberry Pi等设备上控制GPIO的C语言库。
* ​`main.cpp`​ 是指要编译的C++源代码文件，这里是`main.cpp`​。

最后，该命令会编译指定的`main.cpp`​源代码文件，并链接`wiringPi`​库，最终生成一个叫`led`​的可执行文件。

./ led 执行这段代码
