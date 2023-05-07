打印一下[Noise and Distortion slidesFile](https://moodle.gla.ac.uk/mod/resource/view.php?id=3312904) 

---


DSC-SC = Double Sideband Suppressed Carrier.
$$
\phi(t)cosw_ct = f(t)cos^2w_ct = \frac{1}{2}f(t)[1+cos2w_ct]
$$
![](assets/Pasted%20image%2020230501145030.png)

![](assets/Pasted%20image%2020230501145345.png)

左边是BPSK,右边是QPSK
![](assets/Pasted%20image%2020230501145547.png)

# Costa Loop
$S(t)*cos(2 \pi f_0)$
$S(t)$ -> symbols
$cos(2 \pi f_0)$ -> carrier

Costas环是一种用于同步数字调制信号的电路。它通过对输入信号进行相位解调和相位比较，产生一个误差信号，并将该信号通过反馈回路调节本地振荡器的频率和相位，以实现对输入信号的同步。

Costas环可以应用于多种数字调制方案，包括二进制相移键控（BPSK）、四进制相移键控（QPSK）和八进制相移键控（8PSK）等。Costas环通常采用两个正交振荡器的输出作为相位解调器的输入，通过低通滤波器和相位比较器来消除相位偏差，并通过反馈回路来调整本地振荡器的频率和相位，以实现同步。

使用Costas环可以有效地恢复数字调制信号中的载波信号，这对于正确解码数字信号非常重要。

# Tutorial
## 2022
![](assets/Pasted%20image%2020230501210507.png)

占用带宽（OBW）限制为5 MHz，且信道需要实现至少9 Mbit/s的通信数据比特率。
### 香农定理
[香农定理](https://blog.csdn.net/shulianghan/article/details/108002782)
$$
C_{max} = Blog_2(1+\frac{S}{N})
$$

$\frac{S}{N}$ 表示的就是SNR,信噪比.不是简单的SIgnal 除以 Noise.
$\frac{S}{N}$的单位为dB.    与简单的S除以N的换算关系为 $SNR = \frac{S}{N} = 10lg(\frac{P_S}{P_N}) [以功率]$,注意是以10为底
用电压就是$SNR = \frac{S}{N} = 20lg(\frac{V_S}{V_N}) [以电压]$
![](assets/Pasted%20image%2020230507121014.png)
(a)
使用香农-哈特利定理，这个通信信道中实现无误差传输所需的最小信噪比是多少？ 

根据香农-哈特利定理，$C = B * log_2(1 + SNR)$，其中C是通道容量（比特率），B是带宽，SNR是信噪比。在此问题中，$C = 9 Mbit/s，B = 5 MHz$。

(b)
在这个信道中，考虑使用带滚降的升余弦脉冲进行脉冲调制。请为滚降系数β选择一个值，以在限制占用带宽和抑制时域脉冲之间实现适当的折衷。 一个常见的折衷选择是β = 0.5，这会在带宽利用率和抑制脉冲之间达到适当的平衡。在频域中，信号的带宽将是(1+β)倍的符号速率。在本例中，滚降系数β = 0.5是一个合适的选择。关于脉冲谱的草图，您可以在网上查找“升余弦脉冲谱”找到相应的示例。

(c)
因此，允许抑制符号间干扰的最小符号周期是多少？ 首先，我们需要计算符号速率Rs。由于滚降系数β = 0.5，信号带宽为(1+β) * Rs = 1.5 * Rs，因此 Rs = OBW / (1+β) = 5 MHz / 1.5 ≈ 3.33 Msymbols/s。符号周期Ts为1/Rs，即： Ts = 1 / 3.33 Msymbols/s ≈ 0.3 μs 所以最小符号周期约为0.3 μs。

(d)
因此，确定一种调制键控形式，以满足所需的通信比特率。 要实现9 Mbit/s的通信速率，我们可以选择QPSK（四相相移键控），每个符号携带2比特信息。因此，比特速率Rb = 3 * Rs = 3 * 3.33 Msymbols/s = 9.9 Mbit/s，满足所需的通信速率。所以选择16QAM, 一个symbol表示4个bit就是12M,这样才对.

(e)
16QAM
(e)


## 2021_Q4
![](assets/Pasted%20image%2020230501214827.png)
(a)?
根据香农-哈特利定理，信道容量C（即最大信息传输速率）可以通过以下公式计算：
$C = B * log_2(1 + SNR)$，其中B是信道带宽，SNR是信噪比。

(b)
匹配滤波器是一种线性滤波器，其目的是在接收端最大限度地提高信号与噪声的比值。匹配滤波器的脉冲响应是传输脉冲信号的时间反转和共轭，以便在滤波器的输出处实现最佳信噪比。

Matched filter is a type of linear filter, whose purpose is to maximize the signal-to-noise ratio at the receiver. The impulse response of the matched filter is the time-reversal and complex conjugate of the transmitted pulse signal, in order to achieve the best signal-to-noise ratio at the output of the filter.
(c)?
![](assets/Pasted%20image%2020230501214857.png)
(d)

如果脉冲谱的带宽等于可用带宽，则脉冲谱的带宽为12 MHz。对于升余弦脉冲，符号间隔时间Ts可以通过以下公式计算： $\frac{1}{T_{sym}} = \frac{B_{DSB}}{1+\beta}$，其中B是信道带宽，β是滚降因子。

(e) 对于QPSK调制格式，每个符号表示2比特的数据。因此，数据速率（比特率）可以通过以下公式计算： 数据速率 = (1 / Ts) * 每个符号的比特数。

因此，这个通信链路的数据速率约为 x Mbps。 

## 2020_Q6?
![](assets/Pasted%20image%2020230501222406.png)





## 2019
### Q2
![](assets/Pasted%20image%2020230501222252.png)

(a)
10100111
cos
0 下面
180 上面的尖
sin相反
看与开始相反的


(b)
![BPSK的costa环路](assets/Pasted%20image%2020230502134633.png)

这是老师的图,但是这两张图都没错,都对.
![](assets/Pasted%20image%2020230502135819.png)
To use both sine and cosine from the VCO and create the voltage by combining them.

![](assets/Pasted%20image%2020230502135122.png)

![](assets/Pasted%20image%2020230502135158.png)
### Q5
![](assets/Pasted%20image%2020230501222321.png)
