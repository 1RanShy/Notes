25号把所有东西弄好

timer 初始画没开
|     |            |
| --- | ---------- |
| 1.  | 报告要求   |
| 2.  | Poster要求 |
| 3.  | 找房子     | 
- [ ] Spareroom找房子
- [ ] Risk Assessment 怎么办
	- [ ] 问问他们提交了吗?

2023年7月22日
____
到26号5天都搞这个
- [x] 手机进水
- [ ] 串口无法使用,重新解决一下
- [ ] ESP8266串口的使用
- [ ] 手机和手杖蓝牙通讯
---

Beacon
___
实在不行就随便写写算了


拐杖
___
1. 报警 
	1. 小于50 拐杖振动, 手机上也振动 1s发一次 一次振动 0.5s
	2. 语音按钮 设定报警的范围
2. 语音按钮得到距离

直接写语音按钮操作所有的

App要求
___
1. [ ] 每个界面要有明确的功能与责任
2. [ ] 每个界面的按键要尽可能少
3. [ ] 每个界面一定要在最底下留下大片的空白区域
4. [ ] 每个界面一进来要有 语音介绍这一页的功能!\
5. [ ] 改一下电话号码的语音 77-123411这样的电话


___
Risk Assessment:

Hi Professor:

Hello Professor, here is my revised risk assessment. I have made the changes according to your suggestions, and I have **bolded** the sections that I modified. Thank you very much for your assistance!

I sent you a copy last Wednesday. Just to make sure you didn't miss it, I feel it's necessary to send it to you again.

Best Regards
Shuai Ran


rssiRight
rssiRaw
rssiDifference


rssiRaw = rssiRight


80 - rssiRight
越大说明离哪边越近


___
功能简介:
___
1. 语言控制所有

障碍物现在多远

设置报警距离

timer 初始画没开

2023年7月24日
___
桌面的 Android Stuio才是改好的
1. [x] timer 初始画没开 在initstate中打开,不然的话没法自动刷新.
2. [x] 加一个 不安全振动
3. [x] 打开谷歌地图也加上 语言
4. [x] 调整一下界面的布局
5. [ ] 测试一下能否找到入口

口令 : 
set  设置距离报警
far  询问多远


![](assets/截图_20230724095548.png)
![](assets/截图_20230724095946.png)


