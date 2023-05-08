频分复用（Frequency Division Multiplexing，FDM）是一种将多个信息信号同时传输到同一个信道的技术。在FDM中，不同的信息信号被调制到不同的载波频率上，然后这些载波信号通过同一个信道传输。接收端可以通过分离这些不同的载波信号并进行解调来还原出原始信息信号。FDM在广播电视、有线电视、卫星通信等领域得到了广泛应用，可以提高信道利用率，减少信道占用数量，实现信息的高效传输。

![](assets/Pasted%20image%2020230502152212.png)


# Tutorial
## 2021 Q4
![](assets/Pasted%20image%2020230507183719.png)

(f)

即使一些子载波不携带数据，拥有2的幂次方的总子载波数量仍然有优势，因为OFDM是在频域上实现的，其中频带被分成子载波，每个子载波用于传输信息。当使用2的幂次方的子载波时，可以更容易地实现快速傅里叶变换（FFT），从而提高OFDM的效率。此外，使用2的幂次方的子载波也可以更好地支持信道编码和解码。因此，OFDM系统通常使用2的幂次方的子载波数量。

Even if some subcarriers do not carry data, having a total number of subcarriers that is a power of 2 is still advantageous because OFDM is implemented in the frequency domain, where the frequency band is divided into subcarriers, with each subcarrier used for transmitting information. When using a power of 2 for the number of subcarriers, it is easier to implement the fast Fourier transform (FFT), which improves the efficiency of OFDM. Additionally, using a power of 2 for the number of subcarriers also better supports channel encoding and decoding. Therefore, OFDM systems typically use a number of subcarriers that is a power of 2.

(g)
对于基于双边带调制的数字通信系统的传输通道，其可用带宽为12 MHz。这个OFDM示例的子载波间距是多少？

OFDM系统的子载波间距可以使用以下公式进行计算：

子载波间距 = 可用带宽 / 子载波数

在OFDM系统中，每个子载波的带宽为子载波间距的倒数，因此子载波间距越小，可以容纳的子载波数量越多，从而提高系统的数据传输率。

根据上述公式，对于具有12 MHz可用带宽的OFDM系统，假设使用4096个子载波，则其子载波间距为：

子载波间距 = 12 MHz / 4096 = 2.93 kHz

因此，这个OFDM示例的子载波间距为2.93 kHz。

(h)

根据奈奎斯特采样定理，最小有效符号（时间）长度应为子载波间距的倒数的两倍。这是因为OFDM系统中的子载波之间存在相互干扰，因此需要使用周期性前缀（CP）来避免干扰。CP的长度通常设置为最小有效符号长度的一半。

因此，对于本例中的OFDM系统，最小有效符号长度为：

最小有效符号长度 = 2 × 子载波间距的倒数 = 2 × (1 / 2.93 kHz) = 684.6 纳秒

因此，本例中OFDM系统的最小有效符号长度为684.6纳秒。


(i)
在不考虑任何误码纠正或信道编码的情况下，OFDM系统的最大数据速率由其每个符号携带的比特数以及每秒钟发送的符号数量（也称为符号速率或每秒钟的符号数）决定。OFDM系统的每个符号可以传输多个比特，其数量由调制方案和调制阶数确定。

在本例中，OFDM系统使用QPSK星座图，因此每个符号可以携带2个比特。OFDM系统的符号速率等于子载波数量，因为在每个OFDM符号中，每个子载波携带一个调制符号。在本例中，OFDM系统使用4096个子载波，因此其符号速率为4096。

因此，OFDM系统的最大数据速率可以使用以下公式计算：

最大数据速率 = 每个符号携带的比特数 × 符号速率

在本例中，最大数据速率为：

最大数据速率 = 2 × 4096 = 8192 bps

因此，OFDM系统在这个例子中的最大数据速率为8192比特每秒。
(j)
实际应用中，OFDM系统的最大数据速率可能会低于理论最大速率，因为存在一些实际因素会影响其性能。以下是一些可能导致OFDM系统数据速率降低的实际考虑因素：

1.  信道失真：在实际信道中，OFDM符号可能会受到多径效应和其他形式的失真影响，从而降低信号质量和符号解码的准确性。这可能会导致需要重传数据，从而降低数据速率。
    
2.  信道干扰：在同一频带上的其他无线电信号和电磁干扰可能会影响OFDM系统的性能，从而降低数据传输速率。
    
3.  带宽限制：在实际中，OFDM系统的实际带宽可能会受到限制，从而导致无法使用理论最大带宽，从而降低数据速率。
    
4.  调制方案和调制阶数： OFDM系统的数据速率也取决于所采用的调制方案和调制阶数。更高的调制阶数可以在单个符号中传输更多的比特，但也更容易受到信道失真和干扰的影响。
    

综上所述，OFDM系统在实际应用中的数据速率可能低于理论最大速率，这取决于信道条件、干扰、带宽限制和调制参数等多种实际因素。

In practical applications, the maximum data rate of an OFDM system may be lower than the theoretical maximum rate, because there are several practical considerations that can affect its performance. Some of the practical considerations that may result in a reduced data rate for an OFDM system include:

1.  Channel distortion: In real-world channels, OFDM symbols may be subject to multipath effects and other forms of distortion, which can degrade signal quality and reduce the accuracy of symbol decoding. This may result in the need to retransmit data, thereby reducing the data rate.
    
2.  Channel interference: Other radio signals and electromagnetic interference on the same frequency band can affect the performance of an OFDM system, leading to lower data transmission rates.
    
3.  Bandwidth limitations: In practice, the actual bandwidth of an OFDM system may be limited, which can prevent the use of the theoretical maximum bandwidth and thus reduce the data rate.
    
4.  Modulation scheme and order: The data rate of an OFDM system also depends on the modulation scheme and order used. Higher-order modulation can transmit more bits per symbol, but is also more susceptible to channel distortion and interference.
    

In summary, the data rate of an OFDM system in practical applications may be lower than the theoretical maximum rate, depending on various practical factors such as channel conditions, interference, bandwidth limitations, and modulation parameters.
(k)
OFDM系统的可达数据速率取决于多种因素，例如：

1.  信道带宽：实际信道的带宽会影响OFDM系统的数据传输速率，通常会受到一定的限制。
    
2.  调制方式和阶数：OFDM系统的数据速率还取决于所采用的调制方式和阶数。高阶调制能够在每个符号中传输更多的比特，但也更容易受到信道干扰和失真的影响。
    
3.  编码方式：OFDM系统采用的编码方式会对数据传输速率产生影响，采用更加高效的编码方式可以提高数据传输速率。
    
4.  信道条件：信道干扰、多径效应和其他失真因素也会影响OFDM系统的数据传输速率。
    

对于一个典型的OFDM系统，实际可达到的数据速率通常会受到上述因素的影响。因此，实际数据速率可能低于理论最大速率。一般而言，OFDM系统的数据传输速率可以在几十Mbps到数百Mbps之间，这取决于具体应用场景和系统配置。

The achievable data rate for a practical OFDM system depends on several factors such as:

1.  Channel bandwidth: The actual bandwidth of the channel can affect the data transmission rate of the OFDM system, which is usually limited.
    
2.  Modulation scheme and order: The data rate of an OFDM system also depends on the modulation scheme and order used. Higher-order modulation can transmit more bits per symbol, but is also more susceptible to channel interference and distortion.
    
3.  Coding scheme: The coding scheme used by the OFDM system can also affect the data transmission rate. More efficient coding schemes can improve the data transmission rate.
    
4.  Channel conditions: Channel interference, multipath effects, and other forms of distortion can also affect the data transmission rate of the OFDM system.
    

For a typical practical OFDM system, the achievable data rate can be in the range of tens of Mbps to several hundred Mbps, depending on the specific application and system configuration.