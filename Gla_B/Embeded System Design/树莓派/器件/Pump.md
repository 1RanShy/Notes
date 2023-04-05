- [ ] 是否完成
[3V DC Water Pump - 1 Meter Vertical Type ](https://www.adafruit.com/product/4547)
## Pump
- [ ] Pump
[3V DC Water Pump - 1 Meter Vertical Type ](https://www.adafruit.com/product/4547)

<font color="#ff0000">The pump is basically a DC motor that is powered with 3V and draws 100mA.</font> However, the maximum output current is 16mA. The operating voltage of the GPIO pins is 3.3v with a maximum current draw of **16mA**. 

这个不能直接用,需要自建外围电路.
实再不行用吸管戳进去,然后用舵机夹着.
## 三极管
[PNP与NPN三极管的原理与使用方法 - 知乎](https://zhuanlan.zhihu.com/p/404695172)
[tip126-d.pdf](https://www.onsemi.com/pdf/datasheet/tip120-d.pdf)

![](assets/Pasted%20image%2020230401144951.png)

![](assets/Pasted%20image%2020230401150133.png)

NPN的发射极(e)接地，集电极(c)接高电平，基极(b)接控制信号，用b-e的电流（Ib）控制c-e的电流（Ic），e极电位最低，且正常放大时通常c极电位最高，即Vc> Vb > Ve。三极管导通，电流从c极流向e极

三极管的用法特点，关键点在于 b 极（基极）和 e 级（发射极）之间的电压情况，对于**PNP 而言，e 极电压只要高于 b 级 0.7V 以上，这个三极管 e 级和 c 级之间就可以顺利导通**。也就是说，控制端在 b 和 e 之间，被控制端是 e 和 c 之间。同理，**NPN 型三极管的导通电压是 b 极比 e 极高 0.7V**，总之是箭头的始端比末端高 0.7V 就可以导通三极管的 e 极和 c 极。这就是关于“导通电压顺箭头过，电压导通”的解释。

## 测试

三极管导通是0.7V
树莓派引脚高电平是3.3V
3.3-0.7 = 2.6V
按照最小三极管的增益倍数40倍来算
3mA * 40 = 120mA

基级所需的电阻大小就应该是 2.6V除以3mA来算

![](assets/Pasted%20image%2020230401155514.png)