# Digital Modulation And deModulation
## 2022_Q1 2021_Q2
![](assets/Pasted%20image%2020230505091344.png)

(d)
(e)

## 2020 Q2?
根本没做


2022_Q1
判断到底是QAM还是APSK,还是两个都行. 

---

![](assets/Pasted%20image%2020230504204041.png)

6和21是怎么得到的

---

在一个包含n个比特的数据块中，有k个比特出现错误的概率由概率质量函数给出:
$$
\begin{equation} \begin{aligned}
Pr(X = k) = (^n_k)p^k(1-p)^{n-k}\\
p is bit error ration(BER), binomial coefficient (^n_k) = \frac{n!}{(n-k)!}
\end{aligned} \end{equation}
$$


# Hamming Distance
海明距离 : 在信息理论中，两个相等长度字符串之间的海明距离指的是对应位置上符号不同的数量。

最小海明距离 : 一个码的最小海明距离是任意两个不同码字之间的最小海明距离

侦测到e个错误: 最小汉明距离至少为e+1; 纠正e个错误,最小汉明距离至少为2e+1
![](assets/Pasted%20image%2020230504210316.png)

## 生成矩阵和奇偶校验矩阵?
还不太会