protocol |ˈprəʊtəkɒ| 协议
超声波测距传感器 : Ultrasonic range sensor/Ultrasonic distance sensor

- [ ] 演讲流程,演示一遍
- [ ] 准备好演讲稿[其实也不是准备,就是看看有哪些不会讲的单词和句子]

演讲流程[按照海报来]
___
The phone will announce the announce 
目的 : 
___
GPS systems for blind people can provide useful guidance for most of the journey. However, currently available systems are not accurate enough to guide the user the last short distance (10 metres or so) to the entrance. Our goal is to help the blind people find the entrance in the last ten meters.



为了达成这个目标,我设计了一套可穿戴设备和一个移动应用程序.

可穿戴设备可以通过超声波测距传感器检测前方的障碍物并得到用户与障碍物之间的距离.他还可以与手机通过蓝牙交换信息.此外可穿戴设备的障碍物报警距离也可以由用户通过手机设置.
可穿戴设备使用usb-b接口,用户可以使用充电宝来为可穿戴设备供电.
[展示可穿戴设备]

这是我设计的手机应用.这个手机应用可以帮助盲人在最后十米找到入口.他同时还集成了手势输入,语音控制,语音播报,振动提示等功能.下面是功能演示

Page 1
___
语音播报
[Page1](assets/截图_20230815212058.png)
- 用户选中标题,手机就会播报本应用的功能.
- 一旦用户进入了这个界面,手机就会提示用户双击来连接可穿戴设备.一旦成功连接可穿戴设备应用就会自动跳转到第二页.
- 用户未开启蓝牙则会提醒用户打开蓝牙

Page 2
___
[Page2](assets/截图_20230815212409.png)
- 每隔八秒手机播报一次每个蓝牙信标的信号强度,依据此信号强度用户可以知道当前自身相对与入口的位置.关系是数值越大,则离此信标越近.
原理是这样的 :三个蓝牙信标分别被放在入口的周围.手机检测信标的信号强度并播报,用户推断自身现在相对入口的位置,然后判断往哪儿走.
- [ ] 当手机第一次检测到蓝牙信标的信号时会播报入口就在附近
- [ ] 当用户离入口非常近的时候会播报入口就在前方.

[如何放置信标](assets/截图_20230815213239.png)

- 现在默认的报警距离是50cm,你看当50cm内有障碍物时,手机会振动.
- 现在我们可以让手机播报前方多远处有障碍物.
- 现在我们将障碍物报警距离设置为1m

使用手势操作也能进行这些操作.

Page 3
___
在第三页你可以打电话,跳转到谷歌地图,保存电话等.一旦你保存了电话,下一次当你再次打开application时,你可以直接拨打上次保存的电话.



- 现在的缺点就是应用没有直接提供导航,反而需要用户依据当前位置,自己判断方向.
- 信标的信号强度在用户与信标之间的距离超过4m之后衰减的太快.最好能找到信号随距离呈现线性衰减的信号





我们知道一般盲人在使用手机时会打开手机的无障碍模式.
As usual, when the blind use the phone, they will turn on the accessibily mode.
In the acc



可穿戴设备有什么作用
___
提供障碍物预警.不一定非要等盲人用拐杖触碰到障碍物才知道前方有障碍物.例如静止不动的宠物等等.

Provide obstacle pre-warning. It's not necessary to wait for a blind person to touch the obstacle with a cane to know there is an obstacle ahead. For example, stationary pets, and so on






- [ ] Plan 先测试功能
- [ ] 再练习背诵口语