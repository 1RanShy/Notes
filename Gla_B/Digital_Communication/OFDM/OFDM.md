[Lec_D](assets/lect_D.pdf)
[【小白也能看懂】-聊聊OFDM，子载波，傅里叶变换\_哔哩哔哩\_bilibili](https://www.bilibili.com/video/BV12z411B7y9/?spm_id_from=333.337.search-card.all.click&vd_source=2f6e531d9d833ca7fdcd8c5bb99bd1bb)
OFDM是正交频分复用（Orthogonal Frequency Division Multiplexing)
# 什么是OFDM 正交频分复用
OFDM是一种基于频域的传输技术，通过将整个信号分成多个子信号，每个子信号具有相同的带宽，但在频域上是正交的（即没有互相干扰的频率）。这种技术使得OFDM信号具有很强的抗干扰能力，因为如果其中一个子信号受到干扰，其它子信号不会受到影响。
![](assets/Pasted%20image%2020230223153347.png)
##  关键字解释
正交 : 可区分的,两个频率正交就代表这两个频率我们是可以区分的.
频分: 分频
复用: 

多个子载波进行<mark style="background: #FFB86CA6;">并行</mark>的传输

# 什么是DFT
给定的表达式表示在时间间隔(0, NT)上的N个等间距采样x(kT)的离散傅里叶变换（DFT）。<mark style="background: #FFB8EBA6;">DFT是一种数学变换，它将时域中的离散序列转换为频域中的离散序列。换句话说，它用频率分量的形式表示信号。</mark>

DFT被定义为不同频率的复指数函数之和。每个复指数函数由项e^(-jΩTnk)定义，其中n是频率分量的索引，Ω是角频率，T是采样间隔，k是采样的索引。

DFT通常用于分析信号的频率内容，以及设计数字滤波器和其他信号处理算法。逆DFT可以用于从频率分量中恢复原始信号。
![](assets/Pasted%20image%2020230223155231.png)
DFT就是把一个信号分成多个不同的子信号
## 传统多载波
![](assets/Pasted%20image%2020230223152043.png)
子载波之间间隔过大
