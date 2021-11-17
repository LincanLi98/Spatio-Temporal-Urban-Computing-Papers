`Abstract`

Dynamic high resolution data on human population distribution is of great importance for a wide spectrum activities and real-life applications, but is too difficult and expensive to obtain directly. Therefore, generating fine-scaled population distributions from coarse population data is of great significance. However, there are three main challenges: (1) the complexity in spatial relations between high and low resolution population; (2) the dependence of population distributions on other external information; (3) the difficulty in retrieving temporal distribution patterns.  In DeepDPM, we utilize super-resolution convolutional neural network(SRCNN) based model to directly map coarse data into higher resolution data, and a time embedded long short-term memory model to effectively capture the periodicity nature to smooth the finer-scaled results from the previous static SRCNN model. We perform extensive experiments on a real-life mobile dataset collected from Shanghai. Our results demonstrate that DeepDPM outperforms previous state-of-the-art methods and a suite of frequent data-mining approaches. Moreover, DeepDPM breaks through the limitation from previous works in time dimension so that dynamic predictions in all-day time slots can be obtained.

`Contributions`

- 我们提出以一种scalable的方式去生成全时间序列上的动态人流分布，将静态分解数据集(static disaggregated dataset)分解为更加精细的尺度(finer-scale)。据我们所知，这是第一次在城市人流研究中同时分析空间和时间模式。
- 我们提出了DeepDPM模型，它是一个由静态预测和动态预测组合而成的增强架构。详细地讲，DeepDPM模型架构中分别使用超分辨率CNN(super-resolution CNN)和时间嵌入LSTM(time-embedded LSTM)，且在输入数据上使用了我们收集的真实数据集和城市的POI数据。
- 在一个真实数据集上进行实验(Shanghai mobility dataset).实验表明，所提出的DeepDPM在预测能力和几个评价指标上超过了以往的SOTA方法和一系列机器学习领域常用的方法。

Preliminaries:

Definition1: Grid Region

**Definition 2: Population Distribution**

在本文中，我们用 $X_i$来代表不同精度级别的grid region的人流分布，其中 $i \in \{1,2,3\}$. $X_1$代表district level的population distribution(最粗粒度的级别);$X_2$代表稍精细一些的street-level级别的population distribution;$X_3$代表最为细粒度的fine-grained level级别的population distribution.由粗粒度population distribution生成细粒度population distribution可以由公式(1)表示，其中$X_q$和$X_p$是一个pair(同一个区域)，且p<q，即$X_q$比$X_p$更细粒度。
$$
\sum_{i=x_{start}}^{x_{end}} \sum_{j=y_{start}}^{y_{end}} X_p(i,j)=\sum_{i=x_{start}}^{x_{end}} \sum_{j=y_{start}}^{y_{end}} X_q(i,j)
$$


**Problem Formulation:** Given the static aggregated population data $X_i$ and the regularity pattern of population, generate the dynamic finer-scaled grid region population distribution $X_j=X_j^1,X_j^2,...,X_j^{24}$ by a certain mapping function $F$ in a day.



### Methodology.




### Experimental settings

`Datasets.` We collect our representative real-life mobility dataset from ISP, which contains cellular network access records in 9685 different base stations in Shanghai for 4464 different time slots, from $1^{st}$ July, 2017 to $31^{st}$ July, 2017. 

`Preprocessing.` One obstacle in using mobility records to represent population distribution is that stations lose the track when devices are turned off, or are disconnected due to other various factors, like weak signal strength. Therefore, an augmented algorithm is needed to recover the missing fingerprints. 











