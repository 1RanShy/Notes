Hi Shuai

- [x] You do not need to resubmit the risk assessment.

Comments on your report below.

- [x] You have managed to produce a lot of material, but the structure needs to be improved.

- [x] I would suggest deleting section 1.2.

- [x] You need to add a literature review section which discusses existing devices and their advantages and limitations.
	你需要添加一个文献综述部分，讨论现有设备及其优缺点。

- [x] You should include an overview of your devic, its structure and main components.
- [x] 你应该包括你的设备概述，以及它的结构和主要组成部分。
本项目的设备包括三部分: 可穿戴设备,手机移动应用部分,以及蓝牙信标.

可穿戴设备主要是使用合理的传感器来帮助用户进行避障,以及与手机交换信息.其包括主控制板(Arduino Uno Plus),超声测距传感器(HC-SR04),蓝牙模块(HC06).

手机移动应用部分主要是检测蓝牙信标的信息,以及接收可穿戴设备传递的障碍物信息.并通过语音,振动等方式将信息传递给用户.用户也可通过移动应用来与可穿戴设备进行交互.

蓝牙信标由三个蓝牙模块(HC-06组成).他们被分别被放置在入口处,以入口为等腰三角形的顶点,等腰三角形的高为10m,一个信标被放在入口处,另外两个信标分别被放在底边的两个顶点处.

- [x] You should add a methodology section where you discuss device development and the reasons for the design choices you made.  It should also include details of the testing methodology you used.

- [x] The methodology section should be followed by a section which provides a detailed description of the different components of the device. Some of what you are calling the theory section should be moved to this section e.g. 

- [x] design of the user interface.   It should include some block diagrams showing the overall device structure.   

- [x] You need to distinguish what is underlying theory e.g. how different technologies work and what is a description of the device.


- [x] The remaining theory section should be shorter and better structured with an overview of what the higher level theory subsections contain.  ?

- [x] You have a section about RSSI support in the theory section, but you do not explain what RSSI support is.  You should also separate out the requirements of the smartphone from the theory section and explain why the phone needs these features.

- [x] What other team members have done is not part of future considerations.  Points you have not developed could go into future considerations.  You should relate what your device does to existiing systems. 

- [x] I disagree with you that white lettering on blue buttons on a grey background is necessarily a good colour contrast.  This is shown by figures 1 and 2.  I use black and white , so the contrast may be better in actual colour, but it seems poor to me and I find the lettering difficult to read.
不管这个了

- [x] The lettering in figure 16 and some of the other figures is small. Using italics makes it harder to read.

Regards

Marion



- [x] 文献综述没写
- [x] 看一下整体的编号
- [ ] 满足一下格式要求
- [x] Methodology没改
- [x] 引用编号还没改[?1]


Device Development

Reasons for the Design Choice

Test methodology used


这一部分首先介绍了产品的开发过程,为什么选择这样子设计产品,在本项目中使用的一些测试方法,最后介绍了在本项目中使用的相关理论和技术.


本部分主要介绍了移动应用中使用到的技术.例如如何使用蓝牙信标定位,如何合理设计用户界面,什么是RSSI,无障碍模式介绍,开发平台(Flutter)介绍等.


___
在针对



## 3.5 Testing Methodology

本部分描述用于验证和评估项目功能、性能和可靠性的方法。这个部分清楚说明了本项目如何进行测试，包括使用的工具、测试环境、测试用例等。具体的测试数据在result and discussion中体现.

This section describes the methods used to validate and assess project functionality, performance, and reliability. This section clearly outlines how the project is tested, including the tools utilized, testing environment, test cases, and so forth.

### 3.5.1 Wearable Device
本部分主要讲解了如何进行可穿戴设备的评估.

针对可穿戴设备上的测距传感器,使超声测距传感器测量一定距离的障碍物,记此距离为α.再使用测量工具得出实际的障碍物距离记此距离为β.改变障碍物的距离多次测量α和β,观察α与β的误差大小.若α与β的误差小则表明传感器的测量数据准确,避障的性能好.

针对可穿戴设备的蓝牙模块(HC-06),将HC-06通过串口线与电脑连接,通过手机端蓝牙调试助手软件与手机建立蓝牙连接,使HC-06充当帮助手机与电脑交换数据的角色.使用电脑通过HC-06向手机发送固定长度的数据,观察手机上接收到数据的准确率,使用手机通过HC-06向电脑发送固定长度的数据,观察电脑上接收到数据的准确率,准确率越高则使用HC-06传输数据的可靠性越高.
This section primarily explains how to assess wearable devices.

For the distance measurement sensor on the wearable device, an ultrasonic distance sensor is used to measure the distance to a certain obstacle, denoted as α. The actual distance to the obstacle is measured using a measuring tool and recorded as β. The obstacle's distance is changed multiple times, and measurements of both α and β are taken. The magnitude of the error between α and β is observed. If the error between α and β is small, it indicates accurate measurement data from the sensor and good obstacle avoidance performance.

Regarding the Bluetooth module (HC-06) on the wearable device, the HC-06 is connected to a computer via a serial cable. A Bluetooth debugging assistant software is used on the smartphone to establish a Bluetooth connection with the HC-06, making the HC-06 act as a bridge for exchanging data between the smartphone and the computer. The computer sends fixed-length data to the smartphone through the HC-06, and the accuracy of data reception on the smartphone is observed. Similarly, the smartphone sends fixed-length data to the computer through the HC-06, and the accuracy of data reception on the computer is observed. The higher the accuracy, the greater the reliability of data transmission using the HC-06.

### 3.5.2 Mobile Application
本部分主要讲解了如何进行可穿戴设备的评估.

针对导航,在一个空旷处(无遮挡与障碍物),按照Introduction中介绍的放置方法放好信标.使用者打开手机App,观察使用者能否在无人帮助的情况 : 
1. 知晓自己已经在入口附近
2. 依据手机语音提示靠近入口
3. 最终找到入口

针对语音交互,观察用户能否通过语音输入操作移动应用.询问用户语音输出的提示是否能够听清.

针对手势操作,观察用户能否使用手持操作操作移动应用.


在VIB（视力受损和盲人）人士旅行时，通常依赖其他人的帮助。已经开发出辅助设备来协助盲人导航，但许多技术需要用户购买更多设备，缺乏灵活性，从而对VIB用户不太方便。

在视力障碍的人旅行时,他们在大多数时间都需要其他人的帮助.现有的手机地图导航软件能够帮助他们到达目的地,但是由于手机可用的GPS精度不足[]以及在室内等环境下信号差等原因,大多数的应用都不能帮助他们找到目的地的入口.盲人往往需要别人的帮助才能找到入口.

此外现有的盲人避障可穿戴设备虽然功能较为齐全但存在价格昂贵的缺点,而许多盲人可能没有这么多钱来购买如此昂贵的设备,本项目的穿戴设备成本约40pounds.

本项目针对此问题开发了一款移动应用帮助用户在最后10m找到入口,和一款简易的避障可穿戴设备来帮助盲人识别障碍物.


