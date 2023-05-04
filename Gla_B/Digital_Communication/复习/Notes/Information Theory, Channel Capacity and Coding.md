# 信息量 
$$
I_A = log\frac{1}{P_A} \quad = -logP_A
$$
对于一个概率为 $P_A$ 的事件 $A$，其信息量可以用公式 $I_A = log\frac{1}{P_A}$ 或 $I_A = -logP_A$ 来表示。这里的信息量表示的是事件 $A$ 发生所提供的信息量的大小。当 $P_A$ 越小（即事件发生的可能性越小），$I_A$ 的值就越大，表示该事件的发生提供的信息量越多。
For a binary (digital) system we use base 2, i.e. log2, giving information in bits

# 平均信息熵
$$
H = \Sigma^{N-1}_{i = 0}P_ilog_2\frac{1}{p_i}
$$
该公式是离散无记忆源的平均信息熵的计算公式。在离散无记忆源中，有N个可能的事件，每个事件发生的概率为$P_i$，该公式计算了每个事件发生时所传递的平均信息量，其单位为比特（bit）。
其中:
$log_2$表示以2为底的对数，
$P_i$表示事件i发生的概率，
$1/P_i$表示发生事件i所传递的信息量，
H表示所有事件所传递的平均信息量。
该公式中求和符号表示对所有可能的事件的信息量进行求和。
![](assets/Pasted%20image%2020230503160757.png)
# Source Entropy
源熵是指离散随机变量的不确定性度量，表示一个信息源（信息发射器）所提供的信息量的平均值。源熵越大，意味着源提供的信息越不确定，即每个符号携带的信息量越多，需要更多的信息才能准确描述该源的行为。源熵的单位是比特（bit）或香农（Shannon，缩写为Sh），表示对该离散随机变量进行编码时，需要多少比特的信息量来表示每个符号。
![](assets/Pasted%20image%2020230503160740.png)


# 编码 
## Huffman Code
这个可能会考需要掌握
[Huffman Coding](https://www.youtube.com/watch?v=dM6us854Jk0)
![](assets/Pasted%20image%2020230503163338.png)

*记住,先加上最小的!*
![](assets/Pasted%20image%2020230503164442.png)

## Lempel-Ziv-Welch (LZW) coding
[LZW压缩编码](https://search.bilibili.com/all?vt=31338967&keyword=LZW%E5%8E%8B%E7%BC%A9%E7%AE%97%E6%B3%95&from_source=webtop_search&spm_id_from=333.1007&search_source=5)
这个可能会考需要掌握
![](assets/Pasted%20image%2020230503164600.png)


# Lec2

$$
M = \frac{\sqrt{S+N}}{\sqrt{N}} = \sqrt{1+\frac{S}{N}}
$$

在公式 $M = \sqrt{1 + \frac{S}{N}}$ 中，$M$ 表示在存在噪声的情况下，量化器可以分辨的不同电平的数量，也可以理解为量化器的分辨率。其中，$S$ 表示信号功率，$N$ 表示噪声功率。
![](assets/Pasted%20image%2020230503165407.png)
# Tutorial
![](assets/Pasted%20image%2020230503211858.png)

$$
log_2x = (log_{10}x)/(log_{10}2)
$$
1(a)
要计算给定消息的信息量（以比特为单位），我们可以使用以下公式：

信息量 = $- log_2(P)$

其中，P是字符出现的概率。假设字母出现的概率是相等的，英文字母有26个，所以每个字母出现的概率是1/26。

给定的消息是：“the quick brown fox jumps over the lazy dog”。忽略空格，该消息包含35个字符。要计算整个消息的信息量，我们需要将每个字符的信息量相加。
$$
\begin{equation} \begin{aligned}
I_A = log_2\frac{1}{P_A} \quad = -log_2P_A \\
每个字符 消息量 log_2(\frac{1}{26}) \\
整个 消息的信息量就是: 字符数 * 每个字符携带的信息量 \\
35*log_2(\frac{1}{26}) 

\end{aligned} \end{equation}

$$
1(b)
这些值是通过对英文文本的统计分析获得的。可以通过对大量英文文本进行扫描，统计每个字母在文本中出现的频率来计算这些值。然后，这些频率可以归一化，得到每个字母的概率分布。这种方法是一种常见的语言模型建立方法，

These values are obtained through statistical analysis of English text. By scanning a large amount of English text and counting the frequency of each letter appearing in the text, these values can be calculated. Then, these frequencies can be normalized to obtain the probability distribution of each letter. 

(c)
和a一样,只不过每个字母的概率变了.
以字母x为例子:
先统计x出现的次数为3,然后3*$- log_2(P)$,然后每个字母都这么做,再加起来.

(d)
计算字母表的熵
$H = \Sigma^{N-1}_{i = 0}P_ilog_2\frac{1}{p_i}$,用这个公式把字母表过一遍就行了.

(e)
不是。离散无记忆源（DMS）指的是一个符号的出现与之前的符号无关。然而，在自然语言（如英语）中，字母并非独立出现。它们通常以特定的组合（如单词）出现，而某些字母组合的概率要高于其他组合。因此，英语并不是一个真正的离散无记忆源。


$8.323\%*2$

---
2
![](assets/2023-05-04_162217.png)
构建哈夫曼树的顺序而有所不同。但是，不同的哈夫曼编码应具有相同的平均码长，这是由于其构建原理决定的。
通过使用这个哈夫曼编码对由两个六面骰子总和组成的符号集进行编码，我们可以获得接近熵的平均编码长度，从而实现高效的数据压缩。请注意，实际应用中，哈夫曼编码通常应用于更大的数据集，以便充分利用概率分布特征以实现更高的压缩效果。