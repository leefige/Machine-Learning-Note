# Lecture 5 - 3/30

## Topic 4: Markov Model

### 编码问题：Viterbi Algorithm

- 给定输出序列o，计算隐状态序列，argmax{P(X|O)}
- δ_t(j) = max{P(x_1...x_j-1, o_1...o_t-1, x_t=j, o_t)}
- δ_t+1(j) = max_i{ δ_t(i) * a_ij * b_jo_t+1 }
    - 【注意】不是max_i{ δ_t(i) } * a_ij * b_jo_t+1
    - eg. zhe shi yi zhi hua 这是一支花
    - 若用正确方法，到zhi时可能还是“只”，但到hua时就变成了“支花”
    - 用错误方法，则就只会变成“只”

### 应用

- 诊断：打喷嚏=>流鼻涕=>发烧
- 词性标注POS

### 重点掌握

- 前向算法：estimation问题
- viterbi 算法：decoding问题

### 优点

- 数学背景强
- 结构性
- 训练简单

----

# Topic 6: 学习理论1 —— 假设评估

## “归纳学习假设” （见Lec3）
- 足够大？
- 很好地逼近？

## 数学回顾

- 伯努利分布——二项分布
- 期望 $E=np$
- 方差 $n*p*(1-p)$

## 评估准确率

- 样本错误率 期望值等于真实错误率

### 两个重要的估计量
1. estimation bias 估计偏差
    - 无偏估计
    - 独立同分布
    - 可以在测试集估计，**不能用训练集**，因为在训练集上不是独立同分布的（相互关联，有偏）
2. estimation variance 估计方差
    - 无偏估计仍然有方差
3. 一般选择无偏且方差最小的估计