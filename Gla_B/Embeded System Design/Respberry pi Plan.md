[评分细则](assets/Continuous_Assessment_Work_Realtime_v16.pdf)
1. 首先得把代码写好, 调试好
2. 然后是得制作好模型,再把机器装到模型机上测试
	制作样机:需要延长线,因为本来的杜邦线是不够让样机的各个部位装到合适的位置的. 需要焊接实验室的电线用以延长杜邦线的长度,将器件装到合适的位置.

# 编程建议
- [ ] 所有的数组都用vector 而不是单纯的 int a[]
- [ ] ![](assets/Pasted%20image%2020230403102905.png)
那么每天次倒水计时器准时计时 几秒



# 可能会导致零分
1. program goes into wait state and becomes unresponsive

2. using wait statements to establish timing instead of switching threads or load balancing

3. <font color="#ff0000">not using callbacks to process events</font>

4. trivial work selling just with public relations but no substance

5. <font color="#ff0000">no indication of version control</font>

6. not using C++ as the main coding language (remember scripting is only allowed for web services and apps)

- [ ] 在最后清空main 主分支,然后使用merge 合并分支里的内容.
- [ ] 每次都push一下自己更改的代码然后commit的时候一定要写详细注释.


# Report should contains
- [ ] 确定引脚的电路图
- [ ] 一张使用altium design画的schematic 
- [ ] 最好还能有一份 ciurcuit网站的图
- [ ] 详细解释
	1. github分支
	2. ins的详细介绍
	3. 如何分工
	4. 以及上面的会导致零分几点都要在报告中提到.


# Plan
- [ ] 如何在树莓派中使用定时器来让小灯亮灭3s,并且是有开关的.