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

- “归纳学习假设” （见Lec3）
    - 足够大？
    - 很好地逼近？