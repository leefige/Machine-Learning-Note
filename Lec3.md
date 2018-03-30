# Lecture 3 - 3/16 

## Topic 3: Bayesian Learning

### Inductive Learning Hypothesis 归纳机器学习

- 由树木建森林——只能保证在见到的数据下表现良好
- 在足够大的训练集下，也能在**未见实例**很好逼近

### Bayesian

- 因果关系，后验
- P(h|D) = P(D|h)*P(h)/P(D)
    - D: data数据
    - h: hypothesis假设
    - P(h|D)**后验**
    - P(h)先验——没有看到数据，但有一个概率，如根据历史规律
    - P(D|h)**似然概率**，在given h的情况下
- 先验P(h)
    - 互斥，组成H空间
- P(D|h)似然度，log(P(D|h))——log似然度，因为很多似然概率都是指数形式

### 选择假设

1. 一般不关心P(D)——MAP
    - MAP: **最大后验假设**——一定是最优的
    - h_MAP = argmax_h(P(h|D)) = argmax_h[P(D|h)*P(h)]
2. 极大似然假设ML
    - 在先验P(h)未知的情况下
    - h_ML = argmax_h(P(D|h))，即假设所有先验概率都是一样的，eg. 判断男女
    - 假设噪声为高斯分布(正态分布)，则h_ML其实就是最小二乘法拟合

### Naive Bayesian Classifier朴素贝叶斯

- c：语境/上下文，即句子
- s_i：输出的label，单词w的第i个意思
- 假设：P(c|s_k) = ΠP(w_i|s_k)
- s = argmax_s_k{logP(s_k) + ΣlogP(w_i|s_k)} ——MAP取log

### MDL: Minimum Description Length

- 奥卡姆剃刀：prefer shorter hypothesis
- h_MDL = argmin_h{L_c1(h) + L_c2(D|h)}
    - L：用c来表示的串的长度
- MDL和MAP是等价的
- 避免过拟合：不能使L_c2(D|h)为0，否则L_c1(h)会很大，也即过拟合

---

## Topic 4: Markov Model

### 应用
- 天气预报
- 输入法
- speech recognition —— 最近被NN替代

### MM
- 第n天天气w_n依赖于w_n-1, w_n-2, ..., w_1
- 一阶：w_n只依赖于w_n-1, 二/三/...同理
- 转移概率——一个矩阵
    - a_i,j = P(x_n=Sj|x_n-1=Si)
- 时间不变性：相对关系，与绝对时刻无关——平移
    - P(x_n=Sj|x_n-1=Si) = P(x_n+T=Sj|x_n-1+T=Si)
- 转移矩阵：横向和为1，纵向无必然联系
- 对于一阶，若已知今天天气，问后天天气，则需要对明天天气进行穷举

