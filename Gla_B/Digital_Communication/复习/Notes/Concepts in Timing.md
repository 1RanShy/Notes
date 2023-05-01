打印一下[Noise and Distortion slidesFile](https://moodle.gla.ac.uk/mod/resource/view.php?id=3312904) 

---
DSC-SC = Double Sideband Suppressed Carrier.
$$
\phi(t)cosw_ct = f(t)cos^2w_ct = \frac{1}{2}f(t)[1+cos2w_ct]
$$
![](assets/Pasted%20image%2020230501145030.png)

![](assets/Pasted%20image%2020230501145345.png)

![](assets/Pasted%20image%2020230501145547.png)


# Tutorial
## 2022
![](assets/Pasted%20image%2020230501210507.png)

占用带宽（OBW）限制为5 MHz，且信道需要实现至少9 Mbit/s的通信数据比特率。

(a)
使用香农-哈特利定理，这个通信信道中实现无误差传输所需的最小信噪比是多少？ 

根据香农-哈特利定理，$C = B * log_2(1 + SNR)$，其中C是通道容量（比特率），B是带宽，SNR是信噪比。在此问题中，$C = 9 Mbit/s，B = 5 MHz$。

(b)
在这个信道中，考虑使用带滚降的升余弦脉冲进行脉冲调制。请为滚降系数β选择一个值，以在限制占用带宽和抑制时域脉冲之间实现适当的折衷。 一个常见的折衷选择是β = 0.5，这会在带宽利用率和抑制脉冲之间达到适当的平衡。在频域中，信号的带宽将是(1+β)倍的符号速率。在本例中，滚降系数β = 0.5是一个合适的选择。关于脉冲谱的草图，您可以在网上查找“升余弦脉冲谱”找到相应的示例。

(c)


(d)
![](assets/Pasted%20image%2020230501212320.png)


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


## 2020_Q6
![](assets/Pasted%20image%2020230501222406.png)





## 2019
### Q2
![](assets/Pasted%20image%2020230501222252.png)






### Q5
![](assets/Pasted%20image%2020230501222321.png)

