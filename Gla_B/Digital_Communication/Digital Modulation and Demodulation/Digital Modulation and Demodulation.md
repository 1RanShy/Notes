---
title: Digital Modulation and Demodulation
date: 2023-01-31T21:38:12Z
lastmod: 2023-02-11T19:47:45Z
---

# Digital Modulation and Demodulation

# 2023年1月17日

# Lec A

[lect_A.pdf](assets/lect_A-20230116203755-mdcoxpu.pdf)

# Video: Introduction to Digital CommunicationURL

## Communication System

modulator 调制器

demodulator 解调器

source coding 信源编码

channel code 信道编码

![截图_20230117193552](assets/截图_20230117193552-20230117193611-vqato2l.png)

​![截图_20230117194314](assets/截图_20230117194314-20230117194317-yf5vou1.png)​

​![截图_20230117194543](assets/截图_20230117194543-20230117194545-44k9yri.png)​

S1 S2在这里指的不是symbol 而是spectrum

$$
T_{symbol} = =kT_{bit}  \\
baud \\
\frac{1}{T_{sym}} = \frac{1}{kTbit}
$$

## Symgbols with complex values

​![截图_20230117201232](assets/截图_20230117201232-20230117201234-olgily9.png)​

‍

‍

# Video: Amplitude Shift Keying 2URL

![截图_20230117225252](assets/截图_20230117225252-20230117225252-jloqa0d.png)

0.1 是cutoff frequency

这是一个低通滤波器

0.1 是scaled to nyquist frequency $\frac{f}{fc}$ 得在上学期课件查一下.  
也是 采样频率  
只不过是把cut off frequency除以采样频率 得到 0 ~ 1之间的数来表示频率

![截图_20230117231015](assets/截图_20230117231015-20230117231026-mlfki9y.png "如何用小数表示频率")

# Video: Amplitude Shift Keying 4URL

## Latency time  造成延迟

The filter is causing a delay, that half the number of taps

![截图_20230117232242](assets/截图_20230117232242-20230117232245-2ksqez1.png "11:40")

这两张图片并不一样,有2点的延迟.

往后大概就讲了怎么解决这个问题应该就是实验的内容.

---

# LecA_Open_AI

‍

​![截图_20230120100529](assets/截图_20230120100529-20230120100551-2n6snjh.png)​

## 产生旁边频带

​![image](assets/image-20230120114151-vhhy6u6.png)​

​![截图_20230120101403](assets/截图_20230120101403-20230120101406-zn0j6sr.png)​

例如，AM广播电台分配了9kHz的频道，但信号带宽最大仅为4.5kHz。

这是因为振幅调制会在载波频率的两侧产生旁边频带，上行旁边频带的频率比载波频率高，下行旁边频带的频率比载波频率低。这就会导致带宽增加，因此通常需要对信号进行带宽限制，以避免干扰其他频道。

```python
import matplotlib.pyplot as plt
import numpy as np

# Parameter
Ac = 1
fc = 5
fm = 1

# Time
t = np.linspace(0, 1, 1000)

# Modulating signal
mt = np.cos(2*np.pi*fm*t)

# Carrier signal
ct = Ac*np.cos(2*np.pi*fc*t)

# Modulated signal
st = Ac*(1+mt)*np.cos(2*np.pi*fc*t)

# Plot
plt.figure()
plt.plot(t, mt, label='Modulating signal')
plt.plot(t, ct, label='Carrier signal')
plt.plot(t, st, label='Modulated signal')
plt.xlabel('Time')
plt.ylabel('Amplitude')
plt.legend()
plt.show()
```

​![image](assets/image-20230120101823-ew9mehz.png)​

为什么9kHz 需要限制那

因为上行和下行旁边频带会导致载波频率的增加,从而影响其他的频道.

## BPSK QPSK

BPSK (Binary Phase Shift Keying)，是一种数字相位移相键控（PSK）技术，在信息传输过程中，只使用两种不同相位来表示“0”和“1”。

QPSK (Quadrature Phase Shift Keying) 是一种四相移相键控（PSK）技术，它使用四种不同相位来表示“00”,“01”,“10”和“11”。

DBPSK (Differential Binary Phase Shift Keying) 是一种差分相位移相键控（DPSK）技术，它只使用相位变化来传输信息，而不是相位本身。

​![image](assets/image-20230123161100-9lf02gu.png)​

## 什么是相位

```python
import numpy as np
import matplotlib.pyplot as plt

x = np.linspace(0, 2*np.pi, 100)
y1 = np.sin(x)
y2 = np.cos(x + np.pi/2)

plt.plot(x, y1, label='sin')
plt.plot(x, y2, label='cos')
plt.legend()
plt.show()

```

![image](assets/image-20230120114825-9fcgg8m.png)

这个例子绘制出了一个x轴为时间，y轴为幅值的图像，两个函数的相位之差是π/2，可以看到cos函数相对于sin函数比sin函数慢了π/2个单位。

​![image](assets/image-20230120125932-jm8myw6.png)​

# [Video: Phase Shift Keying 3](https://moodle.gla.ac.uk/mod/url/view.php?id=3312883)​**[URL](https://moodle.gla.ac.uk/mod/url/view.php?id=3312883)**

# QPSK的调制与解调

​![image](assets/image-20230123164431-v3ib1zo.png)​

## 调制与解调的具体步骤

### 调制

$$
S(t) * cos(w_ct) \quad调制信号 	\\
cos(w_ct) \quad 载波 \\
载波频率应该是 sampling \quad rate的1/2
$$

### 解调

调制信号 再乘以$cos(w_ct)$得到信号:

$$
S(t)cos^2w_ct = S(t)\frac{1}{2}(1+cos(2w_ct))
$$

现在要想得到原始信号就需要去除$cos(2w_c)$因为他是属于高频信号.只留下$\frac{1}{2}S(t)$

# Conclusion 

主要讲了QPSK和BPSK编码,可以查看openai的回答.

[QPSK解调原理—知乎](https://zhuanlan.zhihu.com/p/583722682)

由于QPSK信号可以产生同相和正交的2路BPSK叠加而成，因此在解调时，对2路信号分别进行BPSK信号的相干解调，将得到的数据最后经过**并串转换**，得到传输信息比特。

‍
